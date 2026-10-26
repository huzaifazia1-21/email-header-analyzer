# Email Header Analyzer

> **Demonstration project.** Built with sample data to show how I approach email troubleshooting. Not client work.

Paste the raw headers of an email that bounced, arrived late or landed in spam, and the tool shows what went wrong and what to fix.

## The problem it addresses

When a business moves to a new mail host or sending service, invoices and customer emails often start landing in spam. The cause is usually in the headers: SPF, DKIM or DMARC records that still point at the old setup. Reading headers by hand is slow and hard to explain to a non-technical customer.

## What it does

- Reads SPF, DKIM and DMARC results from the `Authentication-Results` header
- Checks whether the From, Return-Path and DKIM domains align (needed for DMARC)
- Builds a timeline of every server hop and flags slow hops (possible greylisting or filtering)
- Lists plain-language findings marked **FIX**, **CHECK** or **OK**

## Try it

No install needed. Open `index.html` in any browser. A realistic sample (a migrated domain with a broken DKIM selector and an SPF softfail) loads automatically. Replace it with your own headers and click **Analyze**.

## Notes

- Runs entirely in the browser. Nothing is uploaded.
- Sample headers use reserved example domains (`example.com`, `example.org`, `example.net`).
- It is a diagnostic aid, not a replacement for checking the live DNS records.

## Skills shown

Email troubleshooting · SPF / DKIM / DMARC · technical support diagnosis · JavaScript
