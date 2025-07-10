# Notes for buttons block

## Registration & Files
- Parent metadata: `includes/blocks/buttons/block.php`
- Parent attributes: `includes/blocks/buttons/attributes.php`
- Dynamic CSS: `includes/blocks/buttons/frontend.css.php`
- Child block registered in `blocks-config/buttons-child/class-uagb-buttons-child.php`
- Child attributes: `includes/blocks/buttons-child/attributes.php`
- Child dynamic JS: `includes/blocks/buttons-child/frontend.js.php`

## Important attributes
- `btn_count` – number of child buttons (default `1`).
- `buttons` – array of child button objects with label, link, padding and color options.
- Layout settings: `align`, `gap`, `stack`, `flexWrap`.
- Typography: `fontFamily`, `fontSize`, `lineHeight`, `fontWeight`.
- Each child button has its own `block_id` and styling properties.
- To include an icon in a button set `"showIcon": true` and provide an `"icon"` name like `"rocket"`. The icon position and spacing fields control placement.

## Valid markup example
Spectra expects matching identifiers between JSON `block_id` and the `uagb-block-` class, but IDs may be omitted. Use empty strings to let Spectra generate them automatically:

```html
<!-- wp:uagb/buttons {"block_id":"","classMigrate":true,"childMigrate":true} -->
<div class="wp-block-uagb-buttons uagb-buttons__outer-wrap uagb-btn__default-btn uagb-btn-tablet__default-btn uagb-btn-mobile__default-btn uagb-block-"><div class="uagb-buttons__wrap uagb-buttons-layout-wrap "><!-- wp:uagb/buttons-child {"block_id":"","label":"button1","link":"#","hColor":"","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderStyle":"solid","btnBorderColor":"#333","btnBorderHColor":"#333"} -->
<div class="wp-block-uagb-buttons-child uagb-buttons__outer-wrap uagb-block- wp-block-button"><div class="uagb-button__wrapper"><a class="uagb-buttons-repeater wp-block-button__link" aria-label="" href="#" rel="follow noopener" target="_self" role="button"><div class="uagb-button__link">button1</div></a></div></div>
<!-- /wp:uagb/buttons-child -->

<!-- wp:uagb/buttons-child {"block_id":"","label":"button2","link":"#","hColor":"","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderStyle":"solid","btnBorderColor":"#333","btnBorderHColor":"#333","showIcon":true,"icon":"rocket"} -->
<div class="wp-block-uagb-buttons-child uagb-buttons__outer-wrap uagb-block- wp-block-button"><div class="uagb-button__wrapper"><a class="uagb-buttons-repeater wp-block-button__link" aria-label="" href="#" rel="follow noopener" target="_self" role="button"><span class="uagb-button__icon uagb-button__icon-position-before"><svg xmlns="https://www.w3.org/2000/svg" viewBox="0 0 512 512" aria-hidden="true" focussable="false"><path d="M156.6 384.9L125.7 353.1C117.2 345.5 114.2 333.1 117.1 321.8C120.1 312.9 124.1 301.3 129.8 288H24C15.38 288 7.414 283.4 3.146 275.9C-1.123 268.4-1.042 259.2 3.357 251.8L55.83 163.3C68.79 141.4 92.33 127.1 117.8 127.1H200C202.4 124 204.8 120.3 207.2 116.7C289.1-4.07 411.1-8.142 483.9 5.275C495.6 7.414 504.6 16.43 506.7 28.06C520.1 100.9 516.1 222.9 395.3 304.8C391.8 307.2 387.1 309.6 384 311.1V394.2C384 419.7 370.6 443.2 348.7 456.2L260.2 508.6C252.8 513 243.6 513.1 236.1 508.9C228.6 504.6 224 496.6 224 488V380.8C209.9 385.6 197.6 389.7 188.3 392.7C177.1 396.3 164.9 393.2 156.6 384.9V384.9zM384 167.1C406.1 167.1 424 150.1 424 127.1C424 105.9 406.1 87.1 384 87.1C361.9 87.1 344 105.9 344 127.1C344 150.1 361.9 167.1 384 167.1z"></path></svg></span><div class="uagb-button__link">button2</div></a></div></div>
<!-- /wp:uagb/buttons-child --></div></div>
<!-- /wp:uagb/buttons -->
```

Keep `block_id` and the trailing class empty when generating new blocks.
