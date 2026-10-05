# Haffenden-Creative
Landing page for Haffenden Creative - Creative Artworker

A responsive, dependency-free static page with portfolio, about and experience,
and contact sections.

## Preview

With Python 3 installed, run `npm start` (or `python3 -m http.server 8000`)
from the `public` directory, then open http://localhost:8000.
No install or build step is needed. Deploy `index.html` and `styles.css`
to any static web host.

## Cloudflare Workers deployment

In Cloudflare Workers Builds, set the root directory to `public`, leave the
build command empty, and use `npx wrangler deploy` as the deploy command.
The committed `wrangler.jsonc` configures this as a static-assets Worker.

The `.assetsignore` file allows only `index.html` and `styles.css` to be uploaded.
This prevents Wrangler's installed dependencies, including the large `workerd`
binary, from being treated as website assets. When adding local images, fonts,
or other assets, add matching allowlist entries to `.assetsignore` as well.

To validate without publishing, run `npx wrangler deploy --dry-run` from `public`.
From the repository root, use
`npx wrangler deploy --dry-run --config public/wrangler.jsonc` instead.

The header and footer use the supplied Haffenden Creative logo hosted on GitHub.
Loading it requires internet access; to self-host it, download the original image
and update both image URLs in `index.html`. The site palette uses cyan and blue
to complement the logo, while concept project previews retain their own colours.

## Add your content

- Replace the four clearly labelled concept previews in `index.html` with
  previous projects and their images. Update each image description too.
- Add your biography, previous roles, and client experience in the about section.
- Replace the contact placeholder with your email address and social links before
  publishing. No invented contact details or client credits are included.

There is no existing automated test or lint setup. Check navigation, keyboard
focus, and layouts at mobile and desktop widths when updating the page.
