# MY TANK site

Static, responsive site using the existing `.htm` production URLs. Upload the
five `.htm` files, `assets/`, `robots.txt` and `sitemap.xml` together.

- `tools/build_site.py` is the source for the five pages and their shared header/footer.
- `tools/prepare_assets.py` converts preserved legacy photographs to named WebP files.
- `legacy-backup/` contains the complete original site; do not publish this directory.
- `docs/asset-inventory.csv` maps each legacy asset to its old page references.
- `docs/content-review.md` lists original wording requiring owner confirmation.

Published photography comes from the original MY TANK files; no generated
concept imagery is used on the site.

Build with the bundled Python runtime or any Python 3 installation. Pillow is
required only to regenerate images:

```text
python tools/prepare_assets.py
python tools/build_site.py
python tools/check_site.py
```

The contact form currently prepares a `mailto:` draft and explicitly tells the
visitor to send it in their email app. Set `FORM_ENDPOINT` in `assets/js/site.js`
to an MY TANK-controlled HTTPS form endpoint to enable online submission.

The 3D scene is illustrative because the source site has no GLB model. See
`assets/models/README.md` for the model replacement hook. GSAP, ScrollTrigger,
Lenis and Three.js are pinned locally under `assets/vendor/` so the site does
not depend on a runtime CDN.
