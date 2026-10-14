# hevilleandrick.com

The site of House of Heville & Rick: seasonal limited editions by working artists, sold through the Shopify store.

- `public/index.html` is the whole site (hash-routed: `#artists`, `#house`, `#prints`, `#objets`, `#p-<product handle>`). Products, prices and the bag come live from Shopify's Storefront API; the token in the page is the public storefront token.
- **The artists** are listed in the `ARTISTS` array in `index.html`. `SKELETON = true` draws stand-in cards while the store is empty; set it to `false` at launch, and remove the sample artist Ines Valtorre and the `noindex` line in the `<head>` when the first real season is listed.
- **The Orangery** is its own site at theorangery.hevilleandrick.com (repository `the-orangery`). The menu link, the home door and the old `#orangery` address all go there.
- **Saved text edits** made with the editor on liorsollyshachar.com (Supabase table `site_texts`, key `heville`) are read when the page loads.
- `public/_headers` sets the security headers.

## Publishing
Cloudflare Workers project `heville-and-rick` connected to this repository (Workers and Pages, Workers Builds). The site files are in `public/`; `wrangler.jsonc` tells Cloudflare to serve them as static assets. Build command: none. Deploy command: `npx wrangler deploy`. Every push to `main` goes live. Custom domains: `hevilleandrick.com` and `www.hevilleandrick.com`.

© 2026 House of Heville & Rick, a house of Ontokinesis Applied Systems LLC.
