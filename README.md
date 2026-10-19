# Advanced DMARC Record Generator 2026 Against the New RFC 9989 Requirements

**Build a clearer DMARC policy, understand the available record options, and inspect published email-authentication DNS records.**

The Advanced DMARC Record Generator is a browser-based tool for people who need to create, review, and better understand DMARC DNS records in the context of the updated DMARC standard, **RFC 9989**.

👉 **[Open the live tool on syedraiyan.uk](https://syedraiyan.uk/Advanced-DMARC-Record-Generator-2026-Against-the-New-RFC-9989-Requirements)**

> *Built to eliminate [Vibe Mailing](https://syedraiyan.uk/blog/vibe-mailing-email-deliverability) and replace guesswork with deterministic deliverability telemetry.*

This repository is a **public project overview and documentation page**. It introduces the tool and links to the live application; it is not the source-code repository for the website implementation.

---

## What is DMARC?

DMARC (Domain-based Message Authentication, Reporting, and Conformance) is an email-authentication policy mechanism that builds on SPF and DKIM. It lets a domain owner publish instructions for how receiving mail systems should handle messages that fail DMARC evaluation, and it provides a mechanism for receiving reports when reporting destinations are configured.

A properly planned DMARC deployment can help domain owners monitor authentication alignment, identify legitimate sending sources, and move toward an enforcement policy when they are ready. DMARC is one part of email security; it does not, by itself, guarantee inbox placement or prevent every form of spoofing.

## Why use this generator?

DMARC records are published as DNS TXT records. Their tags and policy values can be confusing, particularly when a domain is moving from monitoring to enforcement or needs to account for subdomains and reporting.

This tool is designed to make the process more understandable by helping users:

- Build a DMARC record from configurable policy options.
- Review important DMARC tags and understand their purpose.
- Explore policy choices for a domain and its subdomains.
- Consider reporting configuration and alignment settings.
- Review relevant newer DMARC-standard concepts, including options such as `np`, where applicable.
- Inspect published DMARC DNS information and the domain's root SPF record using live DNS lookups supported by the tool.
- Read deterministic findings based on the DNS information returned, rather than treating a generated record as proof that an entire email system is correctly configured.

The exact options and checks available are presented in the live application. Always review the generated record and your sending environment before publishing a policy.

## Key capabilities

### 1. Interactive DMARC record generation

Create a DMARC TXT-record value by choosing supported policy and configuration options. The generated value updates as options change, making it easier to understand how the selected settings affect the resulting record.

### 2. Awareness of RFC 9989

The tool is designed with the updated DMARC specification, **RFC 9989**, in mind. It helps users consider modern DMARC configuration concepts while building or reviewing a policy.

Standards evolve, and a tool cannot replace reading the relevant specification or evaluating the requirements of a particular mail environment. Use the live tool's available options as the source of truth for what is currently implemented.

### 3. Live DNS inspection

The tool can inspect published DMARC information and the root-domain SPF record through DNS-over-HTTPS lookups supported by the application. This can help identify configuration details and potential issues in the records visible at the time of the check.

DNS results can be affected by propagation, caching, resolver behavior, and the domain queried. A DNS check is a snapshot, not a guarantee of message-level authentication or deliverability.

### 4. Understand before publishing

A DMARC record should reflect the domain owner's actual sending setup and rollout plan. Use the generator to understand the configuration, then publish the resulting TXT record through your DNS provider and verify it independently.

**The tool does not make DNS changes on your behalf.** You remain in control of what is published for your domain.

## How to use it

1. **Open the tool:** Visit the live [Advanced DMARC Record Generator](https://syedraiyan.uk/Advanced-DMARC-Record-Generator-2026-Against-the-New-RFC-9989-Requirements).
2. **Choose your settings:** Select the supported policy and record options that fit your requirements.
3. **Review the generated record:** Check the resulting TXT-record value and make sure reporting addresses and policy choices are intentional.
4. **Publish through your DNS provider:** Add or update the DMARC TXT record yourself. Do not publish an enforcement policy until you understand its impact on legitimate mail.
5. **Verify and monitor:** Check the published DNS record and monitor authentication results and reports as part of your ongoing email-authentication process.

## Who is this for?

- Domain owners setting up DMARC for the first time.
- Email administrators managing SPF, DKIM, and DMARC.
- Deliverability specialists auditing domain authentication.
- Developers and technical consultants helping clients configure email security.
- Organizations planning a careful move from DMARC monitoring toward enforcement.

## Important limitations

- **Not a complete deliverability audit:** A DMARC record generator or DNS lookup cannot establish whether every message will pass authentication or reach the inbox.
- **DNS visibility is not message testing:** A published record does not prove that every sending service is configured correctly, that DKIM signatures align, or that SPF passes for each message.
- **Review before enforcement:** Policies such as `quarantine` and `reject` can affect legitimate messages if sending sources have not been identified and configured properly.
- **No automatic DNS publishing:** Copy the record and publish it through your DNS provider only after reviewing it.
- **Standards are the authority:** This project is a practical aid, not a replacement for RFC 9989 or other applicable email standards. Do not interpret the presence of an option or a successful DNS lookup as certification of full standards compliance.

## Live application

**[Use the Advanced DMARC Record Generator on syedraiyan.uk →](https://syedraiyan.uk/Advanced-DMARC-Record-Generator-2026-Against-the-New-RFC-9989-Requirements)**

For the broader email-authentication checking tool, visit the [Email Authentication Checker, Tester & Validator](https://syedraiyan.uk/email-authentication-checker-dkim-dmarc-spf).

## About the project

Created by **Syed Raiyan**, an email marketing and email-authentication specialist.

- Website: [https://syedraiyan.uk](https://syedraiyan.uk)
- Live tool: [Advanced DMARC Record Generator](https://syedraiyan.uk/Advanced-DMARC-Record-Generator-2026-Against-the-New-RFC-9989-Requirements)
- Related tool: [Email Authentication Checker, Tester & Validator](https://syedraiyan.uk/email-authentication-checker-dkim-dmarc-spf)

## Standards and further reading

- [RFC 9989 — Domain-based Message Authentication, Reporting, and Conformance (DMARC)](https://www.rfc-editor.org/rfc/rfc9989)
- [RFC 7208 — Sender Policy Framework (SPF)](https://www.rfc-editor.org/rfc/rfc7208)
- [RFC 6376 — DomainKeys Identified Mail (DKIM) Signatures](https://www.rfc-editor.org/rfc/rfc6376)

---

**Note:** This repository documents and introduces the online tool. The live application is hosted on [syedraiyan.uk](https://syedraiyan.uk); this repository does not publish the application's source code.
