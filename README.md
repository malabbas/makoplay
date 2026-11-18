# Makoplay — Playable Marketing Concept

A product concept and interactive landing page exploring a simple question: **what if a brand offer became a game people wanted to play?**

Makoplay imagines a campaign builder for brands, small businesses, and marketers. A marketer describes an offer, chooses a prize, and shares a branded mini-game. Players participate through a short game experience, while a future campaign dashboard would help the marketer understand engagement.

[Explore the source](./index.html) · [Play Pizza Rush](https://demogame1.pages.dev/) · [Companion game repository](https://github.com/malabbas/demogame1)

## What this project demonstrates

- Product storytelling: a clear audience, value proposition, four-step product journey, campaign mockups, and a playable example.
- Front-end implementation with semantic HTML, custom CSS, and vanilla JavaScript in a single page.
- A consistent visual language: monochrome borders, offset shadows, pixel illustrations, a handheld-console motif, and a green accent.
- Responsive sections and an interactive signup modal with native form validation, keyboard focus containment, Escape to close, and focus restoration.
- An explicit distinction between a working prototype and future product capabilities.

## The idea

1. **Describe an offer.** A marketer supplies the campaign details, branding, prize, and winner limit.
2. **Build a game.** A proposed AI-assisted builder adapts a short game to the campaign.
3. **Share and participate.** Players open a game link and can opt into a campaign signup.
4. **Review engagement and rewards.** A future dashboard manages participation, winner limits, and reward workflows.

The hypothesis is that playful interaction could improve brand recall and provide useful engagement signals. Retries and completion are possible signals to investigate, rather than proof of purchase intent. The sample metrics on the page are illustrative values, not campaign results.

## Working demo and proposed features

| Available here | Proposed product capabilities |
| --- | --- |
| Responsive landing page and campaign examples | AI-assisted game generation |
| Signup modal, validation, and local confirmation | Consent-based lead storage and campaign dashboard |
| Link to the standalone Pizza Rush browser game | Server-enforced winner limits and reward fulfillment |
| CSS animation and reduced-motion support | Measured engagement analytics and validated lead scoring |

**The signup is a local demonstration.** Use fictional details such as `Alex Demo`, `alex@example.com`, and `Example Studio`. Submission clears the fields and shows a confirmation preview. Nothing is transmitted or stored, and no waitlist membership is created. The examples and game offer no real prizes.

## Run locally

No build step, package installation, API key, or backend is required.

```bash
git clone https://github.com/malabbas/makoplay.git
cd makoplay
python3 -m http.server 8080 --bind 127.0.0.1
```

Open [http://localhost:8080](http://localhost:8080). Stop the server with `Ctrl+C`. You can also open `index.html` directly in a browser.

## Explore the implementation

| File | Purpose |
| --- | --- |
| `index.html` | Page content, responsive styles, inline pixel artwork, and modal interaction |
| `favicon.svg` | Local vector mark; no external asset service required |
| `.gitignore` | Excludes local configuration, keys, and generated browser artifacts |

The page has no runtime CDN, editor SDK, external font, or database dependency. The game link opens a separate deployment. Content and layout can be edited directly in `index.html`; the modal script is near the end of that file.

## Publish a static preview

Deploy the repository root to any static host. No build command is needed; `index.html` is the entry point. For GitHub Pages, enable **Settings → Pages → Deploy from a branch**, choose the branch containing these files, and select `/ (root)`. Share the URL supplied by the host after the deployment succeeds.

The repository name can remain `makoplay` while the public-facing project title is **Makoplay — Playable Marketing Concept**. Keeping the repository slug preserves existing clone links.

## Data and credentials

An earlier version submitted signup details directly to Supabase with a browser publishable key. This showcase removes that integration and embedded key. A Supabase publishable key is designed to be public; it does not provide the privileges of a secret or service-role key. Older commits still contain the earlier client integration.

For any future live signup, configure a dedicated backend with consent text, validation, abuse controls, and appropriate database access policies. Keep privileged service keys on the server and outside Git. Moving a privileged key into browser JavaScript or a client-side environment variable would still expose it.
