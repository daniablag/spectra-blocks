# Spectra Blocks Knowledge

This repository contains the Spectra (Ultimate Addons for Gutenberg) plugin source under `ultimate-addons-for-gutenberg/`.
Blocks are registered server‑side with PHP. Each block usually has a folder inside `includes/blocks/<block>/` containing:

- `block.php` – general metadata used during registration.
- `attributes.php` – default attributes for the block.
- `frontend.css.php` and `frontend.js.php` – generate dynamic assets based on attributes.

JavaScript defaults are aggregated in `blocks-config/blocks-attributes/getBlocksDefaultAttributes.js` which imports each block’s attribute file. A helper file `dist/blocks-placeholder.js` lists all block names and calls `registerBlockType` for WordPress detection.

### Used Files for container
- ultimate-addons-for-gutenberg/includes/blocks/container/block.php
- ultimate-addons-for-gutenberg/includes/blocks/container/attributes.php
- ultimate-addons-for-gutenberg/includes/blocks/container/frontend.css.php
- ultimate-addons-for-gutenberg/includes/blocks/container/frontend.js.php

### Used Files for info-box
- ultimate-addons-for-gutenberg/includes/blocks/info-box/block.php
- ultimate-addons-for-gutenberg/includes/blocks/info-box/attributes.php
- ultimate-addons-for-gutenberg/includes/blocks/info-box/frontend.css.php
