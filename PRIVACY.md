# Privacy Policy

_Last updated: June 1, 2026_

Quire is an Obsidian plugin operated by Dromena. This policy explains what
data Quire handles, why, and who it is shared with. It covers the Quire
plugin and the license service at `quire.dromena.xyz`.

The short version: Quire does not read, collect, or transmit anything you
write. Your manuscript never leaves your computer. The only data we handle is
what we need to sell you a license and confirm that it is valid.

## What the plugin sends

When you activate your license, the plugin contacts our license server at
`quire.dromena.xyz` once to confirm it. After that, the plugin does not re-check
a one-time license on its own. It reaches the server again only if you activate
on another device or use the Check now button in settings. A monthly
subscription re-checks at most about once a week while you are using Quire, until
it converts to a permanent license, which then stops re-checking on its own too.
Each of these checks sends:

- Your license key.
- A random per-install identifier that the plugin generates on your device.
  It is stored in your operating system's secure storage (the OS keychain),
  not in your vault, so sharing a vault does not share your activation.
- An automatically generated device label, such as "Obsidian on macOS",
  derived from your operating system family. You do not type this in, and it
  does not include your computer's name or any other personal detail.

That is the entire contents of the request. Quire never sends your scene text,
file names, folder names, or any other vault or document data.

## Checking for updates

Because Quire installs from GitHub rather than from Obsidian's plugin directory,
it asks GitHub's public API for the number of the latest release so it can tell
you when an update is available. This is the same public information anyone can
see on the releases page. The request sends no personal data, and Quire reads
only the version number from the reply.

## What the plugin does not do

- It does not read or transmit the contents of your vault.
- It does not collect analytics, usage statistics, or telemetry.
- It does not track you across the web or use advertising networks.
- It does not load remote code or fonts.

## What we store

To run the license service we keep:

- Your email address, provided through checkout, so we can send your license
  key and answer support requests.
- Your license and subscription status (for example active, expired, or
  permanent) and how many activations are in use.
- For each activated device, the per-install identifier and device label
  described above, plus the dates we first saw and last validated it.

We may also keep internal notes related to your purchase or support history.

## Payments

Payments run through Stripe, with its Link checkout as the merchant of record
for Quire, so the charge comes from Link rather than Quire, shown on your
receipt as Sold through Link, LLC. Stripe handles
your card details directly, and we never see or store your full card number. We
receive only what we need to issue and manage your license, such as your email
and payment status. Stripe's handling of your data is governed by its own
privacy policy.

## Network and security data

To keep the service available and protect it from abuse, our servers process
the IP address that each request comes from, and our hosting providers keep
standard request logs for a short period. We use this only for operating and
securing the service, not to build a profile of you.

## Email

We send transactional email only: your license key, payment-related notices,
and replies to messages you send us. We do not send marketing email, and there
is no mailing list to unsubscribe from.

## Data retention

We keep your license and account data for as long as your license is active,
and for as long afterward as we need it for support, accounting, and legal
obligations. You can ask us to delete your data at any time, subject to any
records we are required to keep by law.

## Your choices

You can ask us what data we hold about you, ask us to correct it, or ask us to
delete it. Email hello@quire.dromena.xyz and we will help.

## Changes to this policy

If we change this policy we will update the date at the top of this page.
Material changes will appear here before they take effect.

## Contact

Questions about this policy or your data: hello@quire.dromena.xyz.
