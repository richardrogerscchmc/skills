## What it does

`site-accessibility-check` reviews a live URL for accessibility risks and turns the findings into a short, actionable report. It is meant for a quick scan of a public page or a small set of representative pages, not a full legal audit.

The skill starts by checking the actual page as a user would. It looks for keyboard issues, focus visibility, labels, heading structure, contrast, meaningful images, and other high-signal accessibility blockers. It then sorts findings into red flags and green flags, and wraps the result in a brief report with likely WCAG references and next steps.

## When to reach for it

Type `/site-accessibility-check <url>`, or use it when someone asks for a practical accessibility snapshot of a site from a URL.

This is a good fit when:

- a stakeholder wants a fast check on a public website
- a marketing or service page has been changed and needs a quick accessibility pass
- the team wants to know whether a site has obvious blockers before a deeper remediation effort
- the work needs a quick signal without a full WCAG certification exercise

This is not the right tool for a legal audit, a full-site crawl, or a remediation sprint. It is a rapid signal skill.

## Common questions

**Does this check every page on the site?**
No. It starts with the provided URL and a small set of representative pages, because a broad crawl produces too much noise and too little signal for a fast pass.

**Is this a WCAG certification?**
No. It is a practical check that points to likely issues and likely WCAG criteria, not a legal or formal compliance assessment.

**What kinds of things does it flag?**
Keyboard traps, missing labels, poor focus states, heading problems, contrast problems, broken semantics, missing alt text on meaningful content, and other issues that affect real user flows.

**Can it be used on a site like cincinnatichildrens.org?**
Yes. It is designed for that exact kind of public site. The best pattern is to test the homepage and one or two high-value service pages before summarising the result.

## It's working if

- The user can give a URL and immediately get a focused accessibility review.
- The output separates real blockers from healthy patterns.
- The findings are prioritised by likely user impact, not by raw issue count.
- The report is short enough to be acted on quickly and specific enough to guide a follow-up fix pass.
- The user leaves with a clear sense of what should happen next, and what to ignore for now.
