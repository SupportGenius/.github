<p align="center">
  <img src="https://raw.githubusercontent.com/SupportGenius/.github/main/assets/org-banner.png" alt="SupportGenius. Support that answers. When it can't, it routes the issue to the right people. In design, nothing is built yet." width="100%">
</p>

<p align="center">
  <a href="https://supportgeni.us"><img src="https://img.shields.io/badge/THE%20SITE-SHIPPING-E7EAEF?style=for-the-badge&labelColor=0A0C10" alt="The site: shipping"></a>
  <img src="https://img.shields.io/badge/THE%20PRODUCT-PLANNED-FFC85C?style=for-the-badge&labelColor=0A0C10" alt="The product: planned">
  <a href="https://github.com/SupportGenius/website/blob/main/LICENSE"><img src="https://img.shields.io/badge/LICENSE-MIT-5B9DFF?style=for-the-badge&labelColor=0A0C10" alt="License: MIT"></a>
</p>

<p align="center">
  <sub>
    <a href="https://supportgeni.us">Site</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/#pipeline">Escalations</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/llms.txt">llms.txt</a> &nbsp;·&nbsp;
    <a href="https://github.com/SupportGenius/website/issues/13">Backlog</a> &nbsp;·&nbsp;
    <a href="#what-this-does-not-do">What it does not do</a>
  </sub>
</p>

---

## Support that answers.

When it can't, it routes the issue to the right people, where they already work.

An AI support agent that would answer from a company's own docs, tickets and files, by text or voice,
and turn what it cannot answer into the thing each team works from: a GitHub issue with reproduction
steps for engineering, a ticket for support, a lead for sales. One model would write the ticket and a
second would check it, and the customer would hear back until it is closed.

---

## Two things, and which is which

This matters more than anything else on this page, so it is first.

| | What it is | Status |
| :--- | :--- | :--- |
| **The site** | [supportgeni.us](https://supportgeni.us), in [`SupportGenius/website`](https://github.com/SupportGenius/website): one page, one stylesheet, one script, no build step, on Cloudflare Pages. MIT. | `SHIPPING` |
| **SupportGenius** | The product: the agent, its surfaces, its integrations, the escalation pipeline and the open-source Rust core. Also the waitlist, which opens when its Worker exists. | `PLANNED` |

Nothing beyond the site is built. Not a line of the product. There is no price, published or
estimated, and no vendor named on the site has a partnership with this project.

Two labels are used everywhere, and they govern the tense of the sentence around them:

- `SHIPPING`: built, deployed, usable now. Present tense is allowed only here.
- `PLANNED`: named, not built. Conditional tense, and a chip wherever it appears on the site.

---

## An escalation, as it is designed

The design, drawn. Nothing in this diagram runs yet.

```mermaid
%%{init: {"theme":"base","themeVariables":{
  "background":"transparent",
  "fontFamily":"ui-monospace, SFMono-Regular, Menlo, monospace",
  "fontSize":"13px",
  "primaryColor":"#0F1216","primaryTextColor":"#E7EAEF","primaryBorderColor":"#3A3F47",
  "lineColor":"#6B7382","textColor":"#9AA3B2",
  "clusterBkg":"transparent","clusterBorder":"#3A3F47",
  "edgeLabelBackground":"#0D1015"
}} }%%
flowchart LR
  C(["customer<br/>widget · SDK · phone · API · MCP"]):::req --> A

  subgraph E["THE ENGINE"]
    A["<b>agent</b><br/>retrieval · citations"]:::core
    D["drafting model<br/>title · steps · severity"]:::mod
    J["<b>judge model</b><br/>defect? repro? duplicate?<br/>severity? PII?"]:::port
    A -- "not sure" --> D --> J
  end

  A -- "sure: answer with its source" --> C
  J -- "unsure: one more question" --> C
  J -. "duplicate: link, file nothing" .-> DUP["existing issue"]:::ghost
  J == "file" ==> R["router"]:::core
  R --> ENG["engineering<br/>GitHub · Jira · Linear"]:::vendor
  R --> SUP["support<br/>Zendesk · Intercom"]:::vendor
  R --> SAL["sales<br/>Salesforce · HubSpot"]:::vendor
  R --> H["a person<br/>mobile app · API"]:::vendor
  ENG & SUP & SAL & H -.-> L["lifecycle updates<br/>on each status change"]:::mod
  L -. "until it is closed" .-> C

  classDef req fill:#0D1015,stroke:#5B9DFF,stroke-width:1.5px,color:#E7EAEF
  classDef core fill:#0F1216,stroke:#5B9DFF,stroke-width:1.5px,color:#E7EAEF
  classDef mod fill:#0D1015,stroke:#3A3F47,color:#E7EAEF
  classDef port fill:#0F1216,stroke:#E7EAEF,stroke-width:1.5px,color:#E7EAEF
  classDef vendor fill:#0D1015,stroke:#3A3F47,color:#AEB6C3
  classDef ghost fill:transparent,stroke:#55595F,stroke-dasharray:4 3,color:#9AA3B2
```

---

## The argument, in five points

**1. Answer only when sure, and show where it came from.** Every reply would cite the doc, ticket or
file behind it. Below a confidence threshold the agent would ask a question or hand off, not guess.

**2. Nothing is filed on one model's say-so.** A drafting model would turn the conversation into a
structured ticket. An independent judge would decide whether it is a real defect, reproducible, a
duplicate, correctly graded, and free of customer data, before anything reaches a team's tools.

**3. Escalations land where each team already works.** Bugs in GitHub, Jira or Linear with
reproduction steps. Support cases in Zendesk. Leads in Salesforce. No new inbox for anyone.

**4. The customer hears back.** The ticket would stay linked to the conversation, and status changes
in those tools would become plain-language updates to the customer until the issue is closed.

**5. A person can step in, and the correction stays.** Someone on call could watch, approve, take over
and hand back from their phone, and their answer would be kept as a reviewed source for the next
customer who asks.

---

## Where it would sit

| Kind | Planned | Status |
| :--- | :--- | :--- |
| `sources` | Docs URL, help center, uploaded files, past tickets | `PLANNED` |
| `surfaces` | Web widget (one script tag, text and voice), iOS and Android SDKs, phone line, REST API, MCP server | `PLANNED` |
| `engineering` | GitHub Issues, Jira, Linear | `PLANNED` |
| `support` | Zendesk, Intercom, Freshdesk | `PLANNED` |
| `sales` | Salesforce, HubSpot | `PLANNED` |
| `people` | Mobile app for whoever is on call, Slack, signed webhooks | `PLANNED` |
| `core` | Ticketing and routing in Rust, one static binary, MIT | `PLANNED` |

---

## What this does not do

Stated here rather than buried, because trust is the whole point.

- **Anything, yet.** There is no agent, no widget, no SDK, no phone line, no API and no MCP server.
- **No integrations.** Every vendor above is a planned destination. None is a partner, and none has
  been asked.
- **No waitlist yet.** It opens when its Worker exists
  ([#2](https://github.com/SupportGenius/website/issues/2)). Until then, write to
  [hello@supportgeni.us](mailto:hello@supportgeni.us).
- **No prices.** Not published, not estimated.
- **No real conversations on the site.** Its illustration, its judge scores and its SLA table are sample
  data, and each is labelled as such.

---

## Roadmap, in public

| Capability | Status | Where |
| :--- | :--- | :--- |
| The site, its `llms.txt`, social card and this profile | `SHIPPING` | [website](https://github.com/SupportGenius/website) |
| Waitlist Worker on the Cratefield harness | `PLANNED` | [#2](https://github.com/SupportGenius/website/issues/2) |
| Privacy notice, then opening the waitlist | `PLANNED` | [#3](https://github.com/SupportGenius/website/issues/3), [#4](https://github.com/SupportGenius/website/issues/4) |
| Self-hosted fonts, CI, an accessibility pass | `PLANNED` | [#6](https://github.com/SupportGenius/website/issues/6), [#8](https://github.com/SupportGenius/website/issues/8), [#9](https://github.com/SupportGenius/website/issues/9) |
| A readable illustration on phones | `PLANNED` | [#7](https://github.com/SupportGenius/website/issues/7) |
| The agent, its surfaces and the Rust core | `PLANNED` | not started |
| A live demo on the site | `PLANNED` | [#12](https://github.com/SupportGenius/website/issues/12), after the agent |

The roadmap is the issue tracker. There is no private version of it. The backlog is written for a
[Colonizer](https://colonizer.dev) colony, or anyone, to take one issue at a time; start at
[#13](https://github.com/SupportGenius/website/issues/13).

---

## Repositories

| Repo | What it is |
| :--- | :--- |
| [**website**](https://github.com/SupportGenius/website) | supportgeni.us: the page, its checks, its images and its deploy script. MIT |
| **.github** | This page, the banner and the mark |

<p align="center">
  <br>
  <a href="https://supportgeni.us"><b>supportgeni.us</b></a>
  &nbsp;·&nbsp;
  <a href="mailto:hello@supportgeni.us">hello@supportgeni.us</a>
  &nbsp;·&nbsp;
  a <a href="https://factory0.ventures">Factory Zero</a> venture
</p>

<p align="center">
  <sub>No cookies · no analytics · Support that answers.</sub>
</p>
