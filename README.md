# lexztna/pages — lexztna.com

Landing site for **LexZTNA** — Zero-Trust Network Access for legal workloads,
the network layer of the [Parselex](https://parselex.app) platform.

- **Live**: https://lexztna.com (GitHub Pages, custom domain via Cloudflare DNS)
- **Stack**: static, fully self-contained HTML (inline CSS/JS, zero external resources, zero images)
- **Deploy**: push to `main` → GitHub Actions workflow (`.github/workflows/deploy.yml`)
  verifies integrity (self-contained check, canonical/SEO checks, political-neutrality check)
  and deploys via `actions/deploy-pages`

## DNS wiring (Cloudflare, zone `lexztna.com`)

| Record | Name | Target | Proxy |
|---|---|---|---|
| A ×4 | `@` | `185.199.108–111.153` | DNS only |
| AAAA ×4 | `@` | `2606:50c0:8000–8003::153` | DNS only |
| CNAME | `www` | `lexztna.github.io` | DNS only |

`lexztna.net` (zone `68f5db49…`) is a defensive registration: 301 redirect → `lexztna.com`.

## Editing content

Edit `index.html` / `404.html` directly and push. CI re-verifies on every push.
