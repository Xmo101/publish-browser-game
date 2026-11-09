# Publish your browser game

A short checklist for shipping an HTML5 or WebGL game to the web and getting its first players. It comes as a plain checklist, a Claude Code skill, a Cursor rule and a block for your `AGENTS.md`, so a coding agent can walk you through it.

Made by [Foundplay](https://foundplay.io), a free discovery platform for browser games. Foundplay is one of the places this checklist suggests. The rest of the list works without it.

## The checklist

### 1. Make it load fast

- Show something on screen within a few seconds, even if it's only a title and a loading bar.
- Compress images and audio. Load big assets after the first screen, not before it.
- Test on a slow connection (your browser's dev tools can throttle the network).
- [web.dev on Largest Contentful Paint](https://web.dev/articles/optimize-lcp) explains what makes a page feel slow.

### 2. Make it work on phones

- Add touch controls, or say plainly on the page that the game needs a keyboard.
- [Pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events) handle mouse, touch and pen with one set of handlers.
- Add `<meta name="viewport" content="width=device-width, initial-scale=1">` and stop the page from scrolling while people play.
- Try it on a real phone, in portrait and landscape.

### 3. Give it a title and a share image

Links to your game get shared in chats and posts. Without these tags they show as a bare URL.

```html
<title>Your Game: a one line pitch</title>
<meta name="description" content="What the player does, in one sentence.">
<meta property="og:title" content="Your Game">
<meta property="og:description" content="What the player does, in one sentence.">
<meta property="og:image" content="https://example.com/share.png">
<meta name="twitter:card" content="summary_large_image">
```

Use an absolute URL for `og:image`, about 1200 by 630 pixels. The [Open Graph protocol](https://ogp.me/) lists every tag.

### 4. Put it online for free

Any of these gives you a public link at no cost:

- [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages): free for public repositories.
- [Netlify](https://www.netlify.com/pricing/): a free plan. [Netlify Drop](https://app.netlify.com/drop) publishes a folder or zip you drag in, with no account needed to start.
- [Vercel](https://vercel.com/docs/plans/hobby): a free Hobby plan. Vercel's docs limit Hobby to non-commercial, personal use, so pick another host if your game earns money.
- [itch.io](https://itch.io/docs/creators/html5): upload a zip with an `index.html`, or a single HTML file, and it plays on your itch.io page.

### 5. Get players

A game on its own site gets few visitors until it is listed somewhere players already look. You can list the same game in several places.

**itch.io.** Hosts the game on its page and has a large community of players and jams. Uploading is [free](https://itch.io/docs/creators/faq). You keep ownership and give itch.io a non-exclusive license ([terms](https://itch.io/docs/legal/terms)). If you sell the game, you choose itch.io's share, 10% by default ([payments](https://itch.io/docs/creators/payments)).

**Newgrounds.** Hosts the game in its Portal, with a long running community. New games go [Under Judgment](https://newgrounds.wiki.gg/wiki/Under_Judgment) first: players vote on whether a game stays. You keep ownership and give Newgrounds a non-exclusive license ([terms of use](https://www.newgrounds.com/wiki/help-information/terms-of-use)).

**Foundplay.** A free discovery platform that links to your game where it already lives. [List it here](https://foundplay.io/submit). What you get:

- Free to list.
- The game stays on your site, and you keep any ads or purchases there.
- No exclusivity and no SDK.
- It goes live right away and joins the next drop (6 AM or 6 PM Pacific).
- A share link that earns bonus plays.
- Claim, edit or take down anytime.
- Boost from $15 for guaranteed plays, if you want paid promotion.

Portals such as CrazyGames and Poki host the games they accept and share ad revenue. As of October 2026, CrazyGames asks for its SDK and Poki's revenue share deals are web exclusive by default, so read their developer terms first.

[Where to post your browser game](https://foundplay.io/where-to-post-your-browser-game) compares these sites side by side, with links to each site's own terms. [How to get players for your browser game](https://foundplay.io/get-players) covers the free ways to find players.

## Use it with a coding agent

- **Claude Code:** copy `skills/publish-browser-game` into `.claude/skills/` in your project, or into `~/.claude/skills/` to use it everywhere. Then ask "help me publish my browser game".
- **Cursor:** copy `.cursor/rules/publish-browser-game.mdc` into your project's `.cursor/rules/`.
- **Any agent that reads `AGENTS.md`:** paste the block from `AGENTS-snippet.md` into it.

### Optional: Foundplay's creators MCP server

`mcp.json` adds Foundplay's creators server to an agent that supports remote MCP servers. It checks whether a game is listed, gives the free link that lists it, and shows Boost plans with checkout links. It only reads and returns links: you sign in, list and pay on foundplay.io yourself. No key is needed.

In Claude Code:

```bash
claude mcp add --transport http foundplay-creators https://foundplay.io/mcp/creators
```

More on [Foundplay's connect page](https://foundplay.io/connect).

## Corrections

Facts about other sites were checked on their own pages on October 16, 2026. Sites change their terms, so check before you rely on one. If something here is wrong or out of date, open an issue or a pull request.

## License

MIT. See [LICENSE](LICENSE).
