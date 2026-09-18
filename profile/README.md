<p align="center">
  <img src="https://raw.githubusercontent.com/SupportGenius/.github/main/assets/org-banner.png" alt="SupportGenius. Support that answers. When it can't, it routes the issue to the right people. In design, nothing is built yet." width="100%">
</p>

<p align="center">
  <a href="https://supportgeni.us"><img src="https://img.shields.io/badge/SUPPORTGENI.US-LIVE-5B9DFF?style=for-the-badge&labelColor=0A0C10" alt="supportgeni.us: live"></a>
  <img src="https://img.shields.io/badge/THE%20SITE-SHIPPING-E7EAEF?style=for-the-badge&labelColor=0A0C10" alt="The site: shipping">
  <img src="https://img.shields.io/badge/THE%20PRODUCT-PLANNED-FFC85C?style=for-the-badge&labelColor=0A0C10" alt="The product: planned">
</p>

<p align="center">
  <sub>
    <a href="https://supportgeni.us">Site</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/#how">How it would work</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/#pipeline">Escalations</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/#integrations">Integrations</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/llms.txt">llms.txt</a> &nbsp;·&nbsp;
    <a href="https://factory0.ventures">Factory Zero</a>
  </sub>
</p>

---

## Support that answers. When it can't, it routes the issue.

Most support bots are judged on how many conversations they close. The ones
they can't close are where the cost is: a bug report that becomes "we've passed
this on", a sales question that becomes a form, a customer who never hears back.

SupportGenius is being designed around that second half. It would answer from
a company's own docs, tickets and files, by text or voice, and turn what it
cannot answer into the thing each team actually works from: a GitHub issue with
reproduction steps for engineering, a ticket for support, a lead for sales. A
drafting model would write the ticket, an independent judge model would check it
before anything is filed, and the customer would hear back until it is closed.

---

## Nothing is built yet, and this organisation says so

This matters more than anything else on this page, so it comes first.

| | What it is | Status |
| :--- | :--- | :--- |
| **The site** | [`website`](https://github.com/SupportGenius/website): one page, one stylesheet, one script, no build step, on Cloudflare Pages. | `SHIPPING` |
| **The waitlist** | A Cloudflare Worker on the [Cratefield](https://cratefield.com) harness `waitlist` module ([#2](https://github.com/SupportGenius/website/issues/2)). Until it exists, the site offers `hello@supportgeni.us`. | `PLANNED` |
| **The product** | The agent, the widget, the iOS and Android SDKs, the phone line, the API, the MCP server, the integrations, the open-source Rust core. | `PLANNED` |

Everything on the site that describes the product carries a `planned` chip, the
conversations and scores in its illustration are labelled as sample data, no
price is quoted for anything, and [`llms.txt`](https://supportgeni.us/llms.txt)
repeats all of it in plain text so an answer engine cannot describe a planned
feature as available.

Two labels are used everywhere, and they govern the tense of the sentence around
them:

- `SHIPPING`: built, deployed, usable now. Present tense is allowed only here.
- `PLANNED`: named, unbuilt. Conditional tense, and a chip wherever it appears.

---

## The one idea

Nothing reaches a team's tools on a single model's say-so. One model drafts the
escalation; a second one decides whether it is a real defect, whether it is
reproducible, whether it duplicates an existing issue, whether the severity is
justified and whether any customer data is leaking, and only then is anything
filed. Unsure means one more question to the customer; a duplicate means a link
to the existing issue, and nothing new.

---

## Working here

The backlog lives in [`website`'s issues](https://github.com/SupportGenius/website/issues).
It is written for a [Colonizer](https://colonizer.dev) colony, or any agent, to
take one issue at a time; start at the pinned
[tracking issue](https://github.com/SupportGenius/website/issues/13).

---

<p align="center">
  <sub>
    <a href="mailto:hello@supportgeni.us">hello@supportgeni.us</a> &nbsp;·&nbsp;
    <a href="https://supportgeni.us/.well-known/security.txt">security</a> &nbsp;·&nbsp;
    a <a href="https://factory0.ventures">Factory Zero</a> venture &nbsp;·&nbsp;
    no cookies, no analytics
  </sub>
</p>
