---
name: site-accessibility-check
description: Review a live website from a provided URL for accessibility risks, prioritise the problems, and give the user a concise action list.
disable-model-invocation: true
---

# Site accessibility check

Use this when a user gives you a URL and wants a fast, practical accessibility review of the page or site. It is designed for live site checks, especially for public marketing pages like `cincinnatichildrens.org`, and it is not a legal audit or full WCAG certification.

## What to do

1. Confirm the URL
   - If the user did not give one, ask for it.
   - If the URL is a site root, start with the home page and one or two representative pages.
   - If a page requires login, call that out and ask for a public page instead.

2. Review the page like a real user
   - Open the page in a browser.
   - Tab through the page with the keyboard.
   - Check the focus order, focus visibility, skip links, and form controls.
   - Inspect headings, landmarks, labels, alt text, button text, and contrast.
   - Use browser accessibility tooling and Lighthouse or Axe if available.

3. Sort the issues into red flags and green flags
   - **Red flags**: keyboard traps, missing labels, invisible focus state, empty links or buttons, poor contrast, headings out of order, missing alt text on meaningful images, inaccessible forms, confusing dynamic content.
   - **Green flags**: visible focus styles, good heading structure, semantic landmarks, clear labels, usable keyboard flow, sensible alt text, forgiving navigation patterns.

4. Prioritise the findings
   - **Blocker**: prevents a user from completing a task or makes a core flow unusable.
   - **Important**: likely to create friction for real users, but not a full blocker.
   - **Low**: minor clarity or polish issues that should be fixed later.

5. Produce a concise report
   - URL reviewed
   - Summary judgement: likely good, mixed, or high risk
   - Top red flags with likely impact
   - Green flags worth keeping
   - Likely WCAG references for the biggest issues
   - Recommended next steps for remediation

## Useful checks

Check for:

- keyboard-only navigation
- visible focus states
- form labels and error states
- heading hierarchy and landmark structure
- alt text for meaningful images
- button and link names
- color contrast for text and UI states
- motion and animation that may affect users
- tables and lists used for layout, not structure
- repeated controls without unique labels

## Output format

Use this shape:

```md
## URL
<provided URL>

## Summary
<overall impression and risk level>

## Top red flags
- <issue>: <why it matters> ([WCAG 1.1.1](https://www.w3.org/WAI/WCAG22/Understanding/non-text-content))
- <issue>: <why it matters> ([WCAG 2.4.4](https://www.w3.org/WAI/WCAG22/Understanding/link-purpose-in-context))

## Green flags
- <good pattern>
- <good pattern>

## Likely WCAG references
- [1.1.1 Non-text Content](https://www.w3.org/WAI/WCAG22/Understanding/non-text-content)
- [1.3.1 Info and Relationships](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships)
- [2.1.1 Keyboard](https://www.w3.org/WAI/WCAG22/Understanding/keyboard)
- [2.4.3 Focus Order](https://www.w3.org/WAI/WCAG22/Understanding/focus-order)
- [2.4.4 Link Purpose](https://www.w3.org/WAI/WCAG22/Understanding/link-purpose-in-context)
- [2.4.7 Focus Visible](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible)
- [3.3.2 Labels or Instructions](https://www.w3.org/WAI/WCAG22/Understanding/labels-or-instructions)
- [4.1.2 Name, Role, Value](https://www.w3.org/WAI/WCAG22/Understanding/name-role-value)

## Recommended next steps
1. <highest priority fix>
2. <next fix>
3. <follow-up check>
```

When a red flag is present, include the relevant WCAG link directly in that bullet so the user can open the guidance immediately.

## Rules

- Start with a handful of representative pages, not a whole-site crawl.
- Do not claim compliance. Say **likely** or **observed**.
- Report only what you actually tested.
- Keep the output actionable and short.
- If a page is blocked by a modal, login, or tracking gate, say so clearly.
- When the issue is not obvious from the URL alone, say what still needs verification.

## Example

For a public page from `https://www.cincinnatichildrens.org`, start with:

- homepage
- a high-traffic service page or doctor search page
- a key form or appointment flow
- one information-heavy content page

Then report the highest-signal accessibility problems and the current strengths. The user wants a quick decision, not a legal audit.

## It is working if

- The user gets a clear judgement about the site from a real URL.
- The result focuses on actual user-facing issues, not theoretical ones.
- The report identifies blockers, not just every possible edge case.
- The user can tell what to fix first and what looks healthy already.
