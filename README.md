# EXCAVATOR: A Search Engine Built for Tor

```
http://excavatorhmccf33hkrallqhaixykvepc7zthh4bfrx46pqtfesd7nyd.onion
```

## Introduction

The dark web has long had a discovery problem. Unlike the clearnet, where Google, Bing, and a handful of other giants index nearly everything, Tor hidden services — the sites ending in `.onion` — exist in a fragmented landscape with no dominant search provider. **EXCAVATOR** is an independent project that aims to fill that gap: a keyword search engine that crawls `.onion` sites, indexes their content, and lets users search the results the way they would search the regular web.

What sets EXCAVATOR apart isn't just that it indexes Tor. It's that the project's entire architecture is designed around the values of the network it serves: no tracking, no profiling, no client-side scripts, and no dependence on third-party infrastructure.

---

## How It Works

### An Independent Crawler

EXCAVATOR runs its own crawler that visits `.onion` services and indexes:

- Page **titles**
- Meta **descriptions**
- Full **page text**

Nothing is pulled from Google, Bing, or any outside API. The index is built and maintained on hardware the project controls, and nothing is outsourced to a cloud provider. This matters: on Tor, outsourcing to a third-party cloud would mean trusting that provider with a map of what the dark web looks like — exactly the kind of metadata that could undermine the privacy Tor users expect.

### Plain HTML, No JavaScript

Every page is rendered on the server as static HTML. There are:

- **0 cookies set**
- **0 lines of JavaScript**
- No CDN assets
- No fonts loaded from third-party servers

This isn't just a design preference — it's a privacy decision. Client-side scripts are the foundation of browser fingerprinting, the technique that identifies users even when they're behind Tor. By emitting plain HTML and nothing else, EXCAVATOR ensures that the page you receive is the page they sent, with no room for your browser to leak identifying information.

It also means the site works perfectly in **Tor Browser on its Safest setting**, which disables JavaScript by default.

### Server-Side PHP

The entire stack is server-side PHP. That's an unusual choice in 2026, when most search projects lean on JavaScript-heavy front-ends and distributed cloud infrastructure. EXCAVATOR's choice is deliberate: a single, simple, auditable codebase that renders pages on the server and sends them to the user as-is.

---

## Privacy Model

Mainstream search engines fund themselves by learning who you are. They track queries, build profiles, and sell targeted advertising. On Tor, that model is fundamentally broken — people are on the network precisely because they don't want to be identified.

EXCAVATOR's privacy stance is simple and explicit:

| Practice | EXCAVATOR |
|---|---|
| Cookies | None |
| Third-party analytics | None |
| Fingerprinting | None |
| User profiles | None |
| Data sold to third parties | None |
| Query tied to a person | No |

The project does keep **server-side counts of page views and search terms** to monitor load and identify popular topics. This is operational logging, not user tracking — there's no session ID, no IP retention for profiling, and no way to tie a query to the person who made it.

---

## Accessing EXCAVATOR

One of the more thoughtful design decisions is the **clearnet entry points**. You don't need Tor Browser to *search* — only to *open the `.onion` results*. This lowers the barrier to entry for people who are curious about Tor's content but haven't set up a browser yet.

### The EXCAVATOR Network

EXCAVATOR is spread across several domains, each serving a specific purpose:

| Domain | Purpose |
|---|---|
| **excavatorsearch.direct** | The main search page. Type a keyword, get `.onion` results. |
| **excavatorsearch.link** | A second clearnet address for search, backed by the same index. |
| **excavatorsearch.wiki** | A hand-checked directory of `.onion` sites sorted by category: search, email, news, tools, and more. |
| **excavatorsearch.info** | Plain-language guides on Tor, hidden services, and staying safe. |
| **excavatorsearch.click** | A link shortener that turns a 56-character `.onion` address into something shareable. |
| **excavatorsearch.website** | The project home page — what the project is and how it works. |

### The .onion Address

For maximum privacy, EXCAVATOR is also accessible directly as a Tor hidden service:

```
http://excavatorhmccf33hkrallqhaixykvepc7zthh4bfrx46pqtfesd7nyd.onion
```

This is the most private way to use the search engine: your traffic never leaves the Tor network, and there's no clearnet hop between you and the index.

---

## Getting Listed

Site operators who want their `.onion` service to appear in results can submit it through the **Add URL** page. Every submission is **reviewed by a person** before it appears in the index — a manual curation step that helps keep spam and malicious listings out of search results.

Sites that are already linked from indexed pages are typically picked up by the crawler automatically, so submission isn't always necessary.

---

## Ranking and Advertising

### How Ranking Works

Queries are matched against titles, descriptions, URLs, and page text in the local index, then ordered by relevance. There is **no paid ranking** — promoted listings are clearly labeled and shown separately from organic results. This is a notable contrast with mainstream search engines, where the line between paid and organic placement has steadily blurred.

### Advertising

EXCAVATOR does accept advertising in two forms:

- **Homepage banners**
- **Clearly labeled promoted listings**

Both are visually distinguished from organic search results. Pricing and placement details are available on the project's Advertise page. The advertising model is worth noting: it's the traditional "pay for placement" model, not the surveillance-based "pay for targeting" model that dominates the clearnet.

---

## Why It Matters

The dark web's reputation often overshadows its legitimate uses: whistleblowers, journalists in oppressive regimes, people seeking information without surveillance, and communities that need anonymity for safety. All of these users need to *find* things, and finding things requires a search engine.

EXCAVATOR's contribution is that it takes the privacy assumptions of Tor seriously and builds a search tool that doesn't undermine them. No tracking, no scripts, no cloud dependencies, no data sales. It's a search engine that fits the network it serves.

Whether it scales remains an open question — indexing the dark web is hard, and the network is vast, slow, and full of dead links. But as an architectural statement and a working tool, EXCAVATOR is one of the more interesting independent search projects operating today.

---

*For more information, visit the [project home page](https://excavatorsearch.website/) or start searching at [excavatorsearch.direct](https://excavatorsearch.direct/).*
