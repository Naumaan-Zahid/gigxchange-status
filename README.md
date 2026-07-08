# GigXchange - Off-Stack Status Page

Emergency status page for GigXchange, served on GitHub Pages at
https://status.gigxchange.app - deliberately OFF the main stack (no Cloudflare
Workers, no Supabase) so it stays reachable when the main platform is down.

`index.html` is a single self-contained file (CSS inlined, fonts + hero photo
base64, SvelteKit JS stripped, plus a browser-side "smart links" outage probe).

## Do NOT hand-edit index.html
It is generated from the live /status route in the main (private) repo:

    node gigxchange-website/scripts/build-status-artifact.mjs

Copy the resulting `status-offline/index.html` here as `index.html` and push.
Source of truth: `gigxchange-website/src/routes/status/+page.svelte`.
Config record: main repo tech-debt register 3.23 + docs/INCIDENT-RUNBOOK.md.
