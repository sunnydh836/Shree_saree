# shree — The Saree House

A complete static storefront concept adapting the provided 26.58-second fashion portfolio recording to Indian sarees. The homepage preserves the reference's visual sequence: perspective image ribbon, expanding editorial spread, vertically layered portrait reveal, full-screen campaign with separating typography, quiet statement, scattered image archive, asymmetric editorial, fabric immersion, final product spread, and oversized wordmark footer.

## Run or deploy

Serve `dist/` with any static web server. No dependency installation or build is required. All images, fonts, styles and JavaScript are local. ES modules require HTTP serving rather than opening `index.html` using `file://`.

On a local machine: `python3 -m http.server 8080 --directory dist`

Run `npm run check` for JavaScript syntax checks. `node scripts/verify-motion.mjs` checks that the motion engine runs with finite transforms at representative desktop/mobile scroll positions. This simulated DOM check is not a visual browser test.

## Architecture

- `dist/index.html` — semantic homepage, collection, product, bag, information and navigation dialogs.
- `dist/styles.css` — reusable editorial layout system, tablet/mobile adaptations, focus and reduced-motion rules.
- `dist/catalog.js` — eight illustrative products and collection taxonomy.
- `dist/app.js` — collection/search/sort, product details, image zoom, quantity controls, wishlist and bag.
- `dist/motion.js` — reusable scroll ranges, smooth interpolation, image masks, title splitting, parallax and atmosphere interpolation.
- `dist/ribbon-geometry.js` — projective image panels sharing a curved envelope; convex eye → concave bend → flat ribbon sequence.
- `dist/assets/` — nine original 1024 × 1536 WebP images, local fonts and font license notices.

No third-party scripts, CDNs, trackers or network calls are required by the page. Bag and wishlist persist in the visitor's own local storage. Native dialogs provide focus containment and Escape-to-close. Ambient motion has a pause control; reduced-motion preference suppresses ambient animation, parallax and entrance transitions.

Revision 2 follows the user's colour correction: opened products and collection views use visibly coloured environments rather than near-white panels. A clicked photograph moves from its actual on-screen position into a layered vertical stack and then into a full-screen, three-column editorial spread. The introductory heading has been removed from view to preserve the sparse reference composition. Four corner letters disperse during the opening, while the photographic ribbon unfolds from a thin aperture.

## Scope and handoff

VĀRA is an invented brand concept. Catalogue imagery is AI-generated, prices are illustrative, and weave/material labels describe creative direction. This is not an authenticity or provenance claim. Read `ASSET_PROVENANCE.md` for exact image prompts and dimensions.

The storefront supports exploration through product selection and bag review. It does not take payment, place orders, authenticate customers or connect real inventory. The interface explicitly discloses that purchases are not enabled. Empty subcategories are handled honestly rather than showing unrelated products.

To launch a real store: replace the illustrative catalogue with verified product data and licensed real product photography, connect inventory and checkout, and supply real fulfilment and returns policies.

## Verification

JavaScript syntax, catalogue/asset consistency, local resource references, section anchors, unique IDs, and motion-engine runtime checks were run. The supported browser-preview capability was unavailable in the build environment; visual rendering, touch gestures and interactive browser behavior remain unverified.

Reference motion timings are estimates from a camera recording of a display. Scroll animation is linked to visitor progress, so real duration depends on scroll speed. Exact original easing, hover behaviors and off-screen interactions cannot be recovered from the recording alone.

live link:https://shreesaree-gules.vercel.app/
