# FreeDrops
Track free game giveaways from Reddit — no account, no install, no ads, and absolutely zero "please subscribe to my newsletter" pop-ups.

Let's be honest: checking 50 different subreddits for free games is exhausting. FreeDrops is a lightweight, single-file web app that aggressively interrogates Reddit's top free game subreddits for you. It surfaces only the real, 100% free games, violently filtering out "deals," 10% discounts on asset flips, and expired posts.

## Features
* **Smart filtering** — Only shows genuinely free games. We don't care about your $0.50 discount, Todd.
* **Platform tabs** — Browse by Steam, Epic, Itch.io, GOG, Others, or the graveyard of Expired drops.
* **Game thumbnails** — Preview images pulled directly from Reddit so you know exactly what you're hoarding.
* **Expired detection** — Too slow? Expired giveaways are automatically dimmed out to mock your lack of speed.
* **Instant load** — Caches results locally for 15 minutes. It loads faster than your dad leaving to get milk.
* **Manual refresh** — Force a fresh fetch anytime you feel the RNG gods smiling upon you.
* **No backend** — It's a single HTML file. Backend? Where we're going, we don't need backends.

## How to Use

### Option 1 — Live (GitHub Pages)
Just open the link: [thehollowww.github.io/FreeDrops](https://thehollowww.github.io/FreeDrops/)

### Option 2 — Local
1. Download `index.html`
2. Double-click it to open in your browser

That's literally it. No server, no dependencies, no install wizard. It is so foolproof that you couldn't break it even if you handed your keyboard to an average Geoemetry Dash player.

## Sources
FreeDrops pulls from these subreddits:

| Subreddit | Why |
| :--- | :--- |
| **r/FreeGameFindings** | Dedicated to 100% free PC games (the holy grail). |
| **r/GameGiveaways** | Community-run game giveaways and keys. |
| **r/FreeGamesOnSteam** | Steam-specific free game alerts (for the GabeN loyalists). |

## Customization
Ah, you're one of *those* people. The tinkerers. I respect it. All the config you'd want to mess with is clearly labeled at the top of `index.html` so you don't have to go digging:

```javascript
// How long to cache results before fetching fresh data
const CACHE_TTL_MS = 15 * 60 * 1000; // 15 minutes

// How old a post can be before it's hidden
const MAX_AGE_HOURS = 72;

// Subreddits to pull from
const SUBREDDITS = [
  { name: 'FreeGameFindings', endpoint: 'new', trustAll: true  },
  { name: 'GameGiveaways',    endpoint: 'new', trustAll: false },
  { name: 'FreeGamesOnSteam', endpoint: 'new', trustAll: false },
];
```
Want to add a subreddit? Add a new line to `SUBREDDITS`. Set `trustAll: true` if the entire subreddit is actually dedicated to free games (skips keyword filtering), or `false` to apply the strict include/exclude keyword filter so you don't accidentally fetch garbage.

## Contributing
Contributions are welcome! Some ideas if you want to help:
* Add more subreddits
* Improve keyword filtering accuracy
* Add a search bar
* Improve platform detection
* Rewrite the entire thing in Rust *(Please don't).*

Just fork the repo, make your changes, and open a pull request.

## License
MIT — free to use, modify, and share.

*Built with vanilla HTML, CSS, and JavaScript. No frameworks, no dependencies, no `npm install` taking 84 years, and absolutely no nonsense.*