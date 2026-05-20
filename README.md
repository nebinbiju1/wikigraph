# Six Degrees of Wikipedia

Find the chain of Wikipedia links between any two articles and watch it draw itself, live.

**[Try it →](https://nebinbiju.com/wikigraph/)**

## What it does

Type any two Wikipedia article titles. The app runs a bidirectional breadth-first search across Wikipedia's link graph — expanding outward from the source via outgoing links and inward from the target via incoming links — until the two frontiers meet. The route between them is then animated in as a red path drawn one segment at a time.

- **Bidirectional BFS** with up to 4 hops per side
- **Live Wikipedia API** queries (`prop=links` and `prop=linkshere`)
- **D3 force-directed layout** that radiates each cloud outward from its anchor
- **Animated path reveal** using stroke-dashoffset

## Running locally

It's a single static HTML file with no build step:

```bash
open index.html
```

Or serve from any directory:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Tech

- Vanilla JavaScript
- [D3.js v7](https://d3js.org) for the force simulation, zoom, and transitions
- [Wikipedia REST API](https://en.wikipedia.org/w/api.php) (no key required)

## Tips

- Some pairs are easy (most things link to **Philosophy** in a few hops)
- Some are hard — the search caps at 4 hops per direction
- Click any node in the graph to open its Wikipedia article
