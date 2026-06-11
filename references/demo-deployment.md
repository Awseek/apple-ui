# Apple UI Demo Site Deployment

## What We Built

A showcase website demonstrating the apple-ui design system, deployed to Tokyo cloud (43.133.12.249).

**Domain**: apple-ui.we29.cn  
**Path**: /opt/apple-ui-demo/  
**Stack**: Static HTML/CSS/JS (no framework)

## Files

- `index.html` — Full showcase page (colors, typography, components, patterns, key numbers)
- `style.css` — All CSS using apple-ui design tokens (CSS variables)
- `script.js` — Theme toggle, toggle switches, segmented controls, toast, scroll animations

## nginx Config

```nginx
server {
    listen 80;
    server_name apple-ui.we29.cn;

    location /.well-known/acme-challenge/ {
        root /var/www/acme;
    }

    location / {
        return 301 https://$host$request_uri;
    }
}

server {
    listen 8443 ssl http2;
    server_name apple-ui.we29.cn;

    ssl_certificate /etc/nginx/ssl/apple-ui.we29.cn/fullchain.pem;
    ssl_certificate_key /etc/nginx/ssl/apple-ui.we29.cn/privkey.pem;

    root /opt/apple-ui-demo;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location ~* \.(css|js|png|jpg|jpeg|gif|ico|svg)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }
}
```

**NOTE**: SSL nginx listens on port **8443**, not 443. The cloud proxy handles port 443 and forwards to 8443.

## Deployment Steps

1. Create directory: `ssh volc "mkdir -p /opt/apple-ui-demo"`
2. Copy files: `scp -r /tmp/apple-ui-demo/* volc:/opt/apple-ui-demo/`
3. Create nginx config in `/etc/nginx/sites-available/apple-ui`
4. Symlink: `ln -sf /etc/nginx/sites-available/apple-ui /etc/nginx/sites-enabled/`
5. Test & reload: `nginx -t && systemctl reload nginx`
6. DNS: `*.we29.cn` wildcard already points to Tokyo (43.133.12.249)
7. SSL: Issue cert with acme.sh (see below)

## SSL Certificate Setup

The Tokyo server (43.133.12.249) has a **cloud reverse proxy (nginx/1.18.0)** in front of the actual nginx (1.22.1). This proxy intercepts all HTTP traffic on port 80, making ACME HTTP/webroot/standalone validation impossible.

**Use acme.sh with DNSPod API for automatic DNS validation:**

```bash
# Install acme.sh (if not already installed)
curl -s https://get.acme.sh | sh -s email=jiuhe29@163.com

# Set DNSPod API credentials (get from DNSPod console → API密钥)
export DP_Id="YOUR_DNSPOD_ID"
export DP_Key="YOUR_DNSPOD_API_TOKEN"

# Save credentials permanently
echo "export DP_Id='YOUR_DNSPOD_ID'" >> /root/.acme.sh/account.conf
echo "export DP_Key='YOUR_DNSPOD_API_TOKEN'" >> /root/.acme.sh/account.conf

# Issue cert (DNS validation — no manual TXT record needed)
/root/.acme.sh/acme.sh --issue -d apple-ui.we29.cn --dns dns_dp

# Install cert to nginx ssl directory
mkdir -p /etc/nginx/ssl/apple-ui.we29.cn
/root/.acme.sh/acme.sh --install-cert -d apple-ui.we29.cn \
  --key-file /etc/nginx/ssl/apple-ui.we29.cn/privkey.pem \
  --fullchain-file /etc/nginx/ssl/apple-ui.we29.cn/fullchain.pem \
  --reloadcmd "systemctl reload nginx"
```

**Why acme.sh and not certbot:**
- Previous Hermes sessions used acme.sh successfully
- acme.sh has native DNSPod DNS plugin (`--dns dns_dp`)
- certbot requires manual DNS TXT records for DNS validation
- HTTP validation is blocked by the cloud proxy

## Deployment Pitfalls

- **Cloud proxy blocks HTTP ACME** — Tokyo server has nginx/1.18.0 proxy in front. ALL HTTP requests go through it. ACME HTTP/webroot/standalone validation will fail with 404. Must use DNS validation.
- **SSL port is 8443, not 443** — The cloud proxy handles port 443. nginx SSL should listen on 8443. The proxy forwards HTTPS traffic to 8443.
- **DNS points to wrong server** — Always verify with `nslookup`. `*.jiuhe29.cn` → 火山云 (115.190.59.212), `*.we29.cn` → 东京 (43.133.12.249).
- **SSL certificate domain mismatch** — `*.jiuhe29.cn` cert does NOT cover `we29.cn` subdomains. Each domain family needs its own cert.
- **nginx default_server** — Add catch-all `default_server` block to return 404 for unknown domains.
- **Don't use certbot for Tokyo server** — Use acme.sh with DNSPod API. Certbot manual mode requires user to add TXT records manually.
- **Check session history before guessing** — Previous Hermes sessions may have already solved the same problem. Use `session_search` before making claims about infrastructure.
