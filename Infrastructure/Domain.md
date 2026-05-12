# Domain Setup for `infrazz.com`

Platform: Cloudflare DNS + GitHub Pages

## Purpose

This page is the central domain runbook for `infrazz.com`.

Use it for:

- DNS ownership and conventions
- GitHub Pages records for the public website
- shared domain notes that apply across Infrazz projects

For repo-specific website deployment details, see the `webui` repo documentation:

- `github/webui/domain-setup.md`

## Current Website Target

Primary website:

- `https://www.infrazz.com`

Alternate hostname:

- `https://infrazz.com`

Expected behavior:

- `www.infrazz.com` serves the website
- `infrazz.com` redirects to `https://www.infrazz.com`

## DNS Provider

Authoritative DNS provider:

- Cloudflare

Operational guidance:

- Keep GitHub Pages website records set to `DNS only` during setup and validation
- Avoid Cloudflare redirect rules between apex and `www` when GitHub Pages is handling the redirect
- Treat Cloudflare as the source of truth for DNS records

## GitHub Pages Records

For the current website hosted from `infrazz/webui`, use these DNS records.

### Apex Domain

```txt
Type   Name   Value
A      @      185.199.108.153
A      @      185.199.109.153
A      @      185.199.110.153
A      @      185.199.111.153
```

Optional IPv6:

```txt
Type   Name   Value
AAAA   @      2606:50c0:8000::153
AAAA   @      2606:50c0:8001::153
AAAA   @      2606:50c0:8002::153
AAAA   @      2606:50c0:8003::153
```

### WWW Subdomain

```txt
Type    Name   Value
CNAME   www    infrazz.github.io
```

Cloudflare mode for these records:

- `DNS only`

## GitHub Pages Configuration

Current website repository:

- `infrazz/webui`

Pages guidance:

- Enable GitHub Pages in the repository
- Set the Pages source to `GitHub Actions`
- Set the custom domain to `www.infrazz.com`
- Do not set `infrazz.com` as a separate custom domain in GitHub

Notes:

- With a custom GitHub Actions Pages workflow, the repository `CNAME` file is not the source of truth
- GitHub Pages uses the custom domain configured in repository `Settings -> Pages`
- Apex-to-`www` redirect behavior depends on both correct DNS and the custom domain being set to `www.infrazz.com`

## Domain Verification

GitHub domain verification is recommended.

Steps:

1. Open GitHub account or organization `Settings`
2. Open `Pages`
3. Add `infrazz.com`
4. Create the TXT record GitHub provides
5. Keep the TXT record in DNS

Why:

- Reduces takeover risk
- Helps avoid domain conflict issues across repositories

## Standard Checks

Expected checks after configuration:

- `www.infrazz.com` resolves to `infrazz.github.io`
- `infrazz.com` resolves to GitHub Pages apex IPs
- GitHub Pages shows DNS as valid
- `https://www.infrazz.com` loads the site
- `https://infrazz.com` redirects to `https://www.infrazz.com`

## Troubleshooting

### GitHub says the domain is improperly configured

Check:

- `www` is a real `CNAME` to `infrazz.github.io`
- apex `A` records point to GitHub Pages IPs
- Cloudflare proxy is disabled for website DNS records during validation
- the custom domain in GitHub Pages is exactly `www.infrazz.com`

### Apex redirects or `www` redirects are wrong

Check:

- only `www.infrazz.com` is set as the GitHub Pages custom domain
- `infrazz.com` is not separately configured in another repository
- there are no Cloudflare redirect rules overriding GitHub behavior

### HTTPS is unavailable

Check:

- DNS is fully propagated
- GitHub Pages DNS validation has passed
- `Enforce HTTPS` is enabled after certificate provisioning

## Related Pages

- `Infrastructure/Email Setup`
- `github/webui/domain-setup.md`

## References

- GitHub Docs: About custom domains and GitHub Pages
  https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages
- GitHub Docs: Managing a custom domain for your GitHub Pages site
  https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub Docs: Troubleshooting custom domains and GitHub Pages
  https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages
- GitHub Docs: Verifying your custom domain for GitHub Pages
  https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
