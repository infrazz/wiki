# Package delivery checklists

One checklist per package so every job runs the same way (finding 5). Time estimates are first guesses: time the first three jobs and update them, then revisit prices at the marketing review.

Rules for every job:

- The client creates every account in their own name and pays providers directly. Infrazz is added as an admin, never the owner.
- Export the client's DNS zone (and note the registrar login owner) before changing anything.
- Credentials are never sent by email or WhatsApp. Use the client's password manager or a one-time share link.
- Finish with the one-page handover guide: what's where, what renews when, who to call.

---

## Before any job (all packages)

- [ ] Call: team size, laptops (Windows/Mac), current email and domain, Google or Microsoft preference
- [ ] Recommend the package and the licence plan; tell the client the provider costs they'll pay (licences, domain renewal)
- [ ] Written scope and price by email; client confirms
- [ ] Collect: registrar access (or new registrar choice), company UEN if they want a .com.sg, staff list with names and roles
- [ ] Book the handover call date

## Starter: S$290, up to 5 people

Estimate: 3 to 4 hours of work over 1 to 3 days (DNS propagation).

- [ ] Domain registered or transferred in the client's name; auto-renew on; registrar 2FA on
- [ ] DNS zone exported (if existing)
- [ ] Google Workspace or Microsoft 365 tenant created by the client; Infrazz added as admin
- [ ] Domain verified; mailboxes created for up to 5 people; aliases (hello@, accounts@) as needed
- [ ] MX records switched at an agreed quiet time
- [ ] SPF: exactly one record including the provider
- [ ] DKIM: generated in the admin console, DNS record added, signing turned on
- [ ] DMARC: `p=none` with reports to an admin address; calendar reminder to move to `quarantine` after 2 weeks
- [ ] Old mail migrated (Gmail, web host IMAP or old tenant); spot-check 3 mailboxes
- [ ] Phones and laptops signed in for each person
- [ ] Email Health Check shows no Problems; screenshot for the handover guide
- [ ] Handover call (30 minutes) and one-page guide sent

## Business: S$1,290, up to 5 people

Estimate: 10 to 14 hours over 1 to 2 weeks. Everything in Starter, plus:

- [ ] Website: 3 to 5 pages, content from the client (text, photos, logo); hosting plan agreed and in the client's name
- [ ] Contact form or WhatsApp button working; privacy notice page (PDPA)
- [ ] Google Business Profile created or claimed, verified, hours and photos added
- [ ] Stripe account opened by the client (Singapore business, SGD); Infrazz invited as a team member
- [ ] Card and PayNow turned on; a Payment Link or invoice template made; test payment of S$0.50 refunded
- [ ] Explained to the client: PayNow is for one-off payments and sent invoices (no automatic charging); statements show "STRIPE PAYMENTS SINGAPORE PTE. LTD."; payouts arrive one day after payment, then on the payout schedule
- [ ] WhatsApp Business on a company number (SIM or eSIM the client owns); business profile, greeting and away messages, quick replies
- [ ] Team access: the phone plus up to 4 linked devices
- [ ] Handover covers website edits, Stripe dashboard basics and WhatsApp etiquette

## Secure Team: S$2,290, up to 10 people and 10 laptops

Estimate: 20 to 30 hours over 2 to 3 weeks. Everything in Business, plus:

Licences (client pays, confirm before starting):
- Microsoft: Microsoft 365 Business Premium for everyone (device management with Intune is not in Basic or Standard)
- Google: any Business edition; Windows 10/11 laptops enrolled in Windows device management. Macs: agree the approach before quoting.

- [ ] Two-step sign-in enforced for every account; admin accounts separate from daily accounts
- [ ] Password manager for the team (client's subscription); shared vaults by role; staff onboarded
- [ ] Shared folders (Shared Drives or SharePoint) with permissions by role; external sharing restricted
- [ ] Backup of mail and files: approach agreed and tested with one restore
- [ ] Laptops enrolled in management; disk encryption on (BitLocker or FileVault); automatic updates; remote wipe tested on a spare or reset laptop
- [ ] Lost-laptop procedure written into the handover guide
- [ ] Gemini or Copilot: confirm data-protection status in the admin console (Copilot Chat shows the green shield); explain that it only reaches files each person can already open
- [ ] Joiner and leaver steps written for the client
- [ ] Handover call (60 minutes)

## Care Plan: S$49 a month

- [ ] Monthly: check renewals (domain, licences), DMARC reports, admin alerts
- [ ] Staff changes and DNS changes on request, within 1 working day
- [ ] Log every change in the client's handover guide

## Care Plan Plus: S$15 per person a month

Everything in Care Plan, plus:
- [ ] Monthly security check: device compliance, encryption, update status, risky sign-ins
- [ ] Joiners: account, laptop enrolment, password manager, two-step sign-in
- [ ] Leavers: account suspended, mail handed over, laptop wiped or reassigned, shared passwords rotated

## Cyber Essentials Ready: S$990

Estimate: 8 to 12 hours.

- [ ] Gap check against CSA's Cyber Essentials requirements
- [ ] Fix list agreed; fixes done (or quoted separately if outside a package)
- [ ] Self-assessment evidence pack prepared
- [ ] Client chooses a CSA-appointed certification body and books the assessment; remind them of CSA's fee funding (up to S$250 for 1 to 10 devices, S$350 for 11 to 20)
- [ ] Certification valid 2 years: reminder set for renewal
