# Email Forwarding for `@infrazz.com`

Platform: Cloudflare Email Routing

## Purpose

This page documents how Infrazz handles inbound email for `@infrazz.com`.

Current approach:

- free inbound forwarding through Cloudflare Email Routing
- no hosted mailbox in Cloudflare
- outbound sending handled separately if needed

## What This Supports

Examples:

- `hello@infrazz.com`
- `admin@infrazz.com`
- `support@infrazz.com`
- `billing@infrazz.com`

Supported behavior:

- receive mail sent to custom `@infrazz.com` addresses
- forward mail to an existing destination inbox such as Gmail or Outlook
- optionally create a catch-all rule

Not supported by Cloudflare Email Routing alone:

- IMAP inbox hosting
- POP mailbox hosting
- SMTP sending
- full send-and-receive business mailboxes

## Prerequisites

- `infrazz.com` is on Cloudflare DNS
- destination inbox exists and can receive email
- destination inbox has been verified in Cloudflare

## Recommended Addresses

Suggested starting aliases:

- `hello@infrazz.com`
- `admin@infrazz.com`
- `support@infrazz.com`
- `billing@infrazz.com`

## Setup Steps

### 1. Open Email Routing in Cloudflare

In Cloudflare dashboard:

1. Select the `infrazz.com` zone
2. Open `Email`
3. Open `Email Routing`
4. Start onboarding if it has not been enabled yet

### 2. Add and Verify the Destination Inbox

Example destination:

```txt
yourname@gmail.com
```

Cloudflare will send a verification email.

Complete the verification before creating forwarding rules.

### 3. Enable Cloudflare Email Routing Records

When onboarding Email Routing, let Cloudflare add the required mail records.

Cloudflare typically adds:

- MX records for inbound routing
- TXT helper records where needed

Use the values Cloudflare generates as the source of truth.

Important:

- Do not proxy mail records
- Remove conflicting MX records from unused mail providers

### 4. Create Forwarding Rules

Examples:

```txt
hello@infrazz.com   -> destination inbox
support@infrazz.com -> destination inbox
billing@infrazz.com -> destination inbox
```

Guidance:

- Start with explicit addresses first
- Add a catch-all only if there is a clear reason to receive all unmatched mail

### 5. Test Delivery

Send a test message from a different external email account to:

- `hello@infrazz.com`
- `support@infrazz.com`

Use a different sender than the destination inbox when testing to avoid duplicate-message filtering by some providers.

## Sending Mail as `@infrazz.com`

Cloudflare Email Routing handles forwarding only.

If Infrazz needs to send mail as `hello@infrazz.com`, use a separate sending option such as:

- Gmail `Send mail as` with an SMTP provider
- Outlook with an SMTP provider
- a dedicated email provider later
- Cloudflare Email Service or Workers-based sending if Infrazz adopts that later

## Recommended DNS Hygiene

Keep these email basics in mind:

- Keep only one SPF record for the domain
- Add DKIM when a sending provider is introduced
- Add DMARC for spoofing protection
- Remove old MX records from providers that are no longer used

## Operational Notes

- Cloudflare Email Routing is the current inbound email solution for Infrazz
- It is appropriate for lightweight aliases and early-stage operations
- If Infrazz later needs shared inboxes, mailbox hosting, or reliable outbound mail, revisit the architecture

## Related Pages

- `Infrastructure/Domain`

## References

- Cloudflare Email Routing overview
  https://developers.cloudflare.com/email-routing/
- Cloudflare Email Routing get started
  https://developers.cloudflare.com/email-routing/get-started/
- Cloudflare Enable Email Routing
  https://developers.cloudflare.com/email-routing/get-started/enable-email-routing/
- Cloudflare Test Email Routing
  https://developers.cloudflare.com/email-routing/get-started/test-email-routing/
- Cloudflare DNS email records
  https://developers.cloudflare.com/dns/manage-dns-records/how-to/email-records/
