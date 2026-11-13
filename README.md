# AppSec Lab

Hands-on application security labs that run in your browser. Each lab works the same way: **break it, then fix it**. First you exploit a piece of vulnerable code yourself. Then you edit that code until every attack fails and normal use still works.

The blue-team labs flip this around: you investigate an incident, then build the detection or data pipeline that would have caught it.

**Open the lab:** https://fatemehheidari.github.io/appsec-lab/

## The 28 labs

| Area | Labs |
|---|---|
| Browser attacks | Stored XSS · Reflected XSS · DOM-based XSS · CSRF |
| Server attacks | SSRF · SQL injection: login · SQL injection: data theft · Command injection · Path traversal |
| Access control | IDOR · Mass assignment · JWT tampering |
| Deserialization & crypto | Prototype pollution · Length bomb · Predictable reset codes · Signature replay · Timing leak |
| Supply chain | Workflow injection · Hijacked action · Malicious npm update |
| Security operations | Hunt a stolen token · Incident drill |
| Data engineering | Normalize logs · Duplicates and late events |
| AI for AppSec | Prompt injection · Measure a scanner |
| Senior layer | Threat model a wallet · Scale AppSec |

## How a lab works

1. **The story.** A short scenario at a fictional company, Acme. It tells you what you're attacking, or what you're investigating.
2. **Hack it** (or **Investigate**). Run the attack against the vulnerable code and see exactly what leaks.
3. **Fix it** (or **Build it**). Edit the code in the page, then run the checks. Every attack must fail, and normal use must still work.
4. **What to remember.** The takeaways in a few lines, including how to detect the bug class.

Hints are there when you're stuck, along with a reference solution. Your progress is saved in your browser.

## How it runs

- It's one static HTML file, with no backend and no build step.
- Your code runs in a Web Worker sandbox, against simulated services: a file system, a network with DNS, a shell, a SQLite database ([sql.js](https://github.com/sql-js/sql.js)), a GitHub Actions runner and an npm registry.
- Nothing you type is sent to a real server. The page only loads its libraries (sql.js and [js-yaml](https://github.com/nodeca/js-yaml) from jsDelivr) and its fonts (from Google Fonts).

To run it locally, serve the folder with any static web server:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## A note on the content

- The payloads only work against the simulation inside the page.
- Every company, person and domain in the scenarios is fictional (`.example` domains).
- A few real, public incidents are mentioned for context, such as the tj-actions and chalk/debug compromises.
- The prompt-injection lab uses a recorded model answer, because this page has no live AI model.

## About

I made this to learn application security the way I learn best: by breaking things and then fixing them. I built it with Claude (Anthropic) as a coding partner.

## License

[MIT](LICENSE). sql.js and js-yaml are MIT-licensed and loaded from their CDN.
