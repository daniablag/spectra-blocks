# Notes for buttons block

## Registration & Files
- Parent metadata: `includes/blocks/buttons/block.php`
- Parent attributes: `includes/blocks/buttons/attributes.php`
- Dynamic CSS: `includes/blocks/buttons/frontend.css.php`
- Child block registered in `blocks-config/buttons-child/class-uagb-buttons-child.php`
- Child attributes: `includes/blocks/buttons-child/attributes.php`

## Important attributes
- `btn_count` – number of child buttons (default `1`).
- `buttons` – array of child button objects with label, link, padding and color options.
- Layout settings: `align`, `gap`, `stack`, `flexWrap`.
- Typography: `fontFamily`, `fontSize`, `lineHeight`, `fontWeight`.
- Each child button has its own `block_id` and styling properties.

## Valid markup example
Spectra expects matching identifiers between JSON `block_id` and the `uagb-block-` class, but IDs may be omitted. Use empty strings to let Spectra generate them automatically:

```html
<!-- wp:uagb/buttons {"block_id":"","classMigrate":true,"childMigrate":true} -->
<div class="wp-block-uagb-buttons uagb-buttons__outer-wrap uagb-btn__default-btn uagb-btn-tablet__default-btn uagb-btn-mobile__default-btn uagb-block-"><div class="uagb-buttons__wrap uagb-buttons-layout-wrap "><!-- wp:uagb/buttons-child {"block_id":"","label":"button1","link":"#","hColor":"","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderStyle":"solid","btnBorderColor":"#333","btnBorderHColor":"#333"} -->
<div class="wp-block-uagb-buttons-child uagb-buttons__outer-wrap uagb-block- wp-block-button"><div class="uagb-button__wrapper"><a class="uagb-buttons-repeater wp-block-button__link" aria-label="" href="#" rel="follow noopener" target="_self" role="button"><div class="uagb-button__link">button1</div></a></div></div>
<!-- /wp:uagb/buttons-child -->

<!-- wp:uagb/buttons-child {"block_id":"","label":"button2","link":"#","hColor":"","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderStyle":"solid","btnBorderColor":"#333","btnBorderHColor":"#333"} -->
<div class="wp-block-uagb-buttons-child uagb-buttons__outer-wrap uagb-block- wp-block-button"><div class="uagb-button__wrapper"><a class="uagb-buttons-repeater wp-block-button__link" aria-label="" href="#" rel="follow noopener" target="_self" role="button"><div class="uagb-button__link">button2</div></a></div></div>
<!-- /wp:uagb/buttons-child --></div></div>
<!-- /wp:uagb/buttons -->
```

Keep `block_id` and the trailing class empty when generating new blocks.
