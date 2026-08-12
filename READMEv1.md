# CARF & DAC8 Classifier

A free, public, self-assessment tool for the OECD's Crypto-Asset Reporting Framework (CARF) and the EU's DAC8 Directive (2023/2226). Built to help any crypto exchange, broker, or wallet provider work out whether they're a Reporting Crypto-Asset Service Provider (RCASP), which jurisdiction(s) they owe reporting to, and which of their crypto-assets are actually in scope.

**Live beta:** https://carf-compliance.base44.app/

**Independent personal project.** This is not affiliated with, endorsed by, or representative of eToro or any other employer. It's built and maintained by one individual in a personal capacity, using publicly available OECD and EU texts.

## Status: public beta

This is a beta. It's built from the OECD's published CARF Model Rules, Commentary, and FAQs, and the EU DAC8 Directive — but it hasn't been reviewed by outside counsel, and CARF/DAC8 implementation is still rolling out unevenly across jurisdictions. Treat every output as a starting point for your own analysis, not a finished answer.

**Feedback is genuinely wanted.** If something is wrong, unclear, missing, or you hit a bug, please [open an issue](../../issues) — or a pull request if you want to fix it yourself.

## What's inside

A single self-contained HTML file (`carf-dac8-classification-tool.html`) — no build step, no external dependencies, no framework. Everything (HTML, CSS, JS) is in one file so it's trivial to self-host or fork.

Ten sections:

- **A · Service Provider** — the core RCASP test
- **B · Effectuation of Transactions** — the deep-dive on the grey-area "does this entity actually effectuate transactions" question
- **C · Nexus Determination** — which jurisdiction(s) you owe reporting to, including the anti-duplication relief hierarchy
- **D · Crypto-Asset** — is a given token a Relevant Crypto-Asset, or excluded (CBDC, e-money, low-value NFT, tokenised security)?
- **E · Counterparty** — Excluded Person / Active Entity screening
- **F · Self-Certification** — fillable, printable, downloadable individual and entity self-certification templates
- **G · Jurisdiction Library** — add and share local-law notes as your own jurisdiction's rules are finalised
- **H · Use-Case Patterns** — worked examples for common archetypes (exchange, wallet, DAO-governed protocol)
- **I · Sources** — full citation list
- **J · Ask a Question** — free-form Q&A (see limitation below)

## Known limitation

The **Ask a Question** tab calls the Anthropic API directly from the browser. Inside Claude.ai's artifact preview that authenticates automatically; on any other host (including this beta's current Base44 deployment) it will fail without your own backend and API key wired in. If you fork this and want that tab working, you'll need to point it at your own proxy/backend instead of the raw client-side `fetch` call currently in the code.

## Self-hosting

Download `carf-dac8-classification-tool.html` and open it in a browser, or serve it from literally anything that can serve a static file — GitHub Pages, S3, your own server. No build step required.

## Not legal or tax advice

This tool and its contents are an educational decision-support aid, not legal, tax, or regulatory advice. Confirm any classification with qualified counsel and your competent tax authority before relying on it.

## License

MIT — see [LICENSE](LICENSE). Fork it, adapt it, put your own jurisdiction's rules in it.

## Built from

- OECD (2023), *International Standards for Automatic Exchange of Information in Tax Matters* — CARF Model Rules and Commentary
- OECD, *Crypto-Asset Reporting Framework: Frequently Asked Questions* (December 2025 edition)
- OECD (2024), *Delivering Tax Transparency to Crypto-Assets: A Step-by-Step Guide*
- Council Directive (EU) 2023/2226 (DAC8)
- HMRC, *Implementation of the Cryptoasset Reporting Framework (CARF)* (25 June 2025)
