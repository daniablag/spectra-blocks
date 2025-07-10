# ЗАДАЧА

Твоя задача — научиться формировать валидные Gutenberg JSON-блоки Spectra (`uagb/*`) по текстовому описанию пользователя.

Для этого:

1. Изучи, как код плагина Spectra в папке `/ultimate-addons-for-gutenberg/` формирует блоки: container, info-box и другие.
2. Проанализируй структуру валидного блока в формате Gutenberg — пример я указал ниже (блок container с вложенными инфобоксами).
3. Пойми, какие поля обязательны, какие повторяются, как они связаны с блоками внутри плагина.
4. Пойми как формируется код блока, его настройки, стили, стили планшетной и мобильной версии.
5. Папки и файлы, которые участвуют в анализе конкретного блока, обязательно фиксируй в файле `/base-knowledge.md` в отдельном разделе "Used Files". Это поможет тебе в будущем ограничивать область поиска и не тратить ресурсы на лишнее.

Пример:
### Used Files for info-box
- ultimate-addons-for-gutenberg/blocks-config/info-box/block.json
- ultimate-addons-for-gutenberg/blocks-config/info-box/edit.js
- ultimate-addons-for-gutenberg/blocks-config/info-box/save.js

### Пример валидного Gutenberg JSON-блока (с контейнерами и вложениями)
Данный код содержит Родительски контейнер, в котором вертикально распологаются блоки: icon list с дочерним с дочерним блоком в котором иконка и текст. Далее заголовок блока. Далее контейнер, который является родительским
для 3 других контейнеров. Что в этом контейнере:
3 дочерних контейнера расположенных по горизонтали (raw ставится в их родительском контейнере). Каждый дочерний контейнер содержит инфобокс. В инфобоксе есть иконка, заголовок и описание.

<!-- wp:uagb/container {"block_id":"dff6f46a","backgroundType":"color","backgroundColor":"var(\u002d\u002dast-global-color-3)","topPaddingDesktop":100,"bottomPaddingDesktop":100,"leftPaddingDesktop":40,"rightPaddingDesktop":40,"topPaddingMobile":80,"bottomPaddingMobile":80,"leftPaddingMobile":24,"rightPaddingMobile":24,"paddingLink":false,"variationSelected":true,"rowGapDesktop":8,"columnGapDesktop":8,"isBlockRootParent":true,"className":"cards"} -->
<div class="wp-block-uagb-container cards uagb-block-dff6f46a alignfull uagb-is-root-container"><div class="uagb-container-inner-blocks-wrap"><!-- wp:uagb/icon-list {"block_id":"b32066c4","classMigrate":true,"childMigrate":true,"gap":0,"fontTransform":"uppercase","iconColor":"var(\u002d\u002dast-global-color-0)","blockTopMargin":0,"blockRightMargin":0,"blockLeftMargin":0,"blockBottomMargin":0,"blockTopPadding":0,"blockRightPadding":0,"blockLeftPadding":0,"blockBottomPadding":0} -->
<div class="wp-block-uagb-icon-list uagb-block-b32066c4"><div class="uagb-icon-list__wrap"><!-- wp:uagb/icon-list-child {"block_id":"fe4ff1c2","label":"What we do?","icon":"circle","label_color":"","className":"pref"} -->
<div class="wp-block-uagb-icon-list-child uagb-block-fe4ff1c2 pref"><span class="uagb-icon-list__source-wrap"><svg xmlns="https://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M512 256C512 397.4 397.4 512 256 512C114.6 512 0 397.4 0 256C0 114.6 114.6 0 256 0C397.4 0 512 114.6 512 256z"></path></svg></span><span class="uagb-icon-list__label">What we do?</span></div>
<!-- /wp:uagb/icon-list-child --></div></div>
<!-- /wp:uagb/icon-list -->

<!-- wp:uagb/advanced-heading {"block_id":"3990293d","classMigrate":true,"headingDescToggle":false,"headingColor":"var(\u002d\u002dast-global-color-7)","blockBottomPadding":50,"blockBottomPaddingMobile":30} -->
<div class="wp-block-uagb-advanced-heading uagb-block-3990293d"><h2 class="uagb-heading-text">We Help Businesses Like Yours</h2></div>
<!-- /wp:uagb/advanced-heading -->

<!-- wp:uagb/container {"block_id":"8a15f04d","directionDesktop":"row","directionTablet":"column","alignItemsDesktop":"stretch","alignItemsTablet":"stretch","alignItemsMobile":"stretch","equalHeight":true} -->
<div class="wp-block-uagb-container uagb-block-8a15f04d"><!-- wp:uagb/container {"block_id":"89245f40","backgroundType":"color","backgroundColor":"var(\u002d\u002dast-global-color-2)","boxShadowColor":"rgba(47,47,47,0.06)","boxShadowVOffset":12,"boxShadowBlur":42,"boxShadowSpread":0,"boxShadowColorHover":"rgba(132,255,31,0.74)","boxShadowBlurHover":24,"boxShadowSpreadHover":0,"topPaddingDesktop":40,"bottomPaddingDesktop":40,"leftPaddingDesktop":40,"rightPaddingDesktop":40,"topPaddingMobile":24,"bottomPaddingMobile":24,"leftPaddingMobile":24,"rightPaddingMobile":24,"containerBorderTopLeftRadius":20,"containerBorderTopRightRadius":20,"containerBorderBottomLeftRadius":20,"containerBorderBottomRightRadius":20} -->
<div class="wp-block-uagb-container uagb-block-89245f40"><!-- wp:uagb/info-box {"classMigrate":true,"tempHeadingDesc":"From MVP to launch — we help startups design, develop, and grow their digital products.","headingAlign":"left","headingColor":"var(\u002d\u002dast-global-color-4)","subHeadingColor":"var(\u002d\u002dast-global-color-4)","icon":"rocket","iconSize":24,"iconColor":"var(\u002d\u002dast-global-color-0)","headSpace":12,"block_id":"cc0a7bef","iconLeftMargin":12,"iconRightMargin":12,"iconTopMargin":12,"iconBottomMargin":12,"imageWidth":205,"spacingLink":true,"headTopMargin":20,"headRightMargin":0,"headLeftMargin":0,"iconView":"Stacked","iconBackgroundColor":"var(\u002d\u002dast-global-color-7)","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderTopLeftRadius":0,"btnBorderTopRightRadius":0,"btnBorderBottomLeftRadius":0,"btnBorderBottomRightRadius":0,"btnBorderStyle":"solid","btnBorderColor":"#333"} -->
<div class="wp-block-uagb-info-box uagb-block-cc0a7bef uagb-infobox__content-wrap  uagb-infobox-icon-above-title uagb-infobox-image-valign-top"><div class="uagb-ifb-content"><div class="uagb-ifb-icon-wrap"><div class="uagb-iconbox-icon-wrap uagb-infobox-shape-circle"><svg xmlns="https://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M156.6 384.9L125.7 353.1C117.2 345.5 114.2 333.1 117.1 321.8C120.1 312.9 124.1 301.3 129.8 288H24C15.38 288 7.414 283.4 3.146 275.9C-1.123 268.4-1.042 259.2 3.357 251.8L55.83 163.3C68.79 141.4 92.33 127.1 117.8 127.1H200C202.4 124 204.8 120.3 207.2 116.7C289.1-4.07 411.1-8.142 483.9 5.275C495.6 7.414 504.6 16.43 506.7 28.06C520.1 100.9 516.1 222.9 395.3 304.8C391.8 307.2 387.1 309.6 384 311.1V394.2C384 419.7 370.6 443.2 348.7 456.2L260.2 508.6C252.8 513 243.6 513.1 236.1 508.9C228.6 504.6 224 496.6 224 488V380.8C209.9 385.6 197.6 389.7 188.3 392.7C177.1 396.3 164.9 393.2 156.6 384.9V384.9zM384 167.1C406.1 167.1 424 150.1 424 127.1C424 105.9 406.1 87.1 384 87.1C361.9 87.1 344 105.9 344 127.1C344 150.1 361.9 167.1 384 167.1z"></path></svg></div></div><div class="uagb-ifb-title-wrap"><h3 class="uagb-ifb-title">Startups &amp; SaaS</h3></div><p class="uagb-ifb-desc">From MVP to launch — we help startups design, develop, and grow their digital products.</p></div></div>
<!-- /wp:uagb/info-box --></div>
<!-- /wp:uagb/container -->

<!-- wp:uagb/container {"block_id":"8dfbc791","backgroundType":"color","backgroundColor":"var(\u002d\u002dast-global-color-2)","boxShadowColor":"rgba(47,47,47,0.06)","boxShadowVOffset":12,"boxShadowBlur":42,"boxShadowSpread":0,"boxShadowColorHover":"rgba(132,255,31,0.74)","boxShadowBlurHover":24,"boxShadowSpreadHover":0,"topPaddingDesktop":40,"bottomPaddingDesktop":40,"leftPaddingDesktop":40,"rightPaddingDesktop":40,"topPaddingMobile":24,"bottomPaddingMobile":24,"leftPaddingMobile":24,"rightPaddingMobile":24,"containerBorderTopLeftRadius":20,"containerBorderTopRightRadius":20,"containerBorderBottomLeftRadius":20,"containerBorderBottomRightRadius":20} -->
<div class="wp-block-uagb-container uagb-block-8dfbc791"><!-- wp:uagb/info-box {"classMigrate":true,"tempHeadingDesc":"Websites that bring you more calls, bookings, and foot traffic — optimized for local SEO and mobile.","headingAlign":"left","headingColor":"var(\u002d\u002dast-global-color-4)","subHeadingColor":"var(\u002d\u002dast-global-color-4)","icon":"house-laptop","iconSize":24,"iconColor":"var(\u002d\u002dast-global-color-0)","headSpace":12,"block_id":"b48510ca","iconLeftMargin":12,"iconRightMargin":12,"iconTopMargin":12,"iconBottomMargin":12,"imageWidth":205,"spacingLink":true,"headTopMargin":20,"headRightMargin":0,"headLeftMargin":0,"iconView":"Stacked","iconBackgroundColor":"var(\u002d\u002dast-global-color-7)","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderTopLeftRadius":0,"btnBorderTopRightRadius":0,"btnBorderBottomLeftRadius":0,"btnBorderBottomRightRadius":0,"btnBorderStyle":"solid","btnBorderColor":"#333"} -->
<div class="wp-block-uagb-info-box uagb-block-b48510ca uagb-infobox__content-wrap  uagb-infobox-icon-above-title uagb-infobox-image-valign-top"><div class="uagb-ifb-content"><div class="uagb-ifb-icon-wrap"><div class="uagb-iconbox-icon-wrap uagb-infobox-shape-circle"><svg xmlns="https://www.w3.org/2000/svg" viewBox="0 0 640 512"><path d="M218.3 8.486C230.6-2.829 249.4-2.829 261.7 8.486L469.7 200.5C476.4 206.7 480 215.2 480 224H336C316.9 224 299.7 232.4 288 245.7V208C288 199.2 280.8 192 272 192H208C199.2 192 192 199.2 192 208V272C192 280.8 199.2 288 208 288H271.1V416H112C85.49 416 64 394.5 64 368V256H32C18.83 256 6.996 247.9 2.198 235.7C-2.6 223.4 .6145 209.4 10.3 200.5L218.3 8.486zM336 256H560C577.7 256 592 270.3 592 288V448H624C632.8 448 640 455.2 640 464C640 490.5 618.5 512 592 512H303.1C277.5 512 255.1 490.5 255.1 464C255.1 455.2 263.2 448 271.1 448H303.1V288C303.1 270.3 318.3 256 336 256zM352 304V448H544V304H352z"></path></svg></div></div><div class="uagb-ifb-title-wrap"><h3 class="uagb-ifb-title">Local Businesses</h3></div><p class="uagb-ifb-desc">Websites that bring you more calls, bookings, and foot traffic — optimized for local SEO and mobile.</p></div></div>
<!-- /wp:uagb/info-box --></div>
<!-- /wp:uagb/container -->

<!-- wp:uagb/container {"block_id":"e9dee57a","backgroundType":"color","backgroundColor":"var(\u002d\u002dast-global-color-2)","boxShadowColor":"rgba(47,47,47,0.06)","boxShadowVOffset":12,"boxShadowBlur":42,"boxShadowSpread":0,"boxShadowColorHover":"rgba(132,255,31,0.74)","boxShadowBlurHover":24,"boxShadowSpreadHover":0,"topPaddingDesktop":40,"bottomPaddingDesktop":40,"leftPaddingDesktop":40,"rightPaddingDesktop":40,"topPaddingMobile":24,"bottomPaddingMobile":24,"leftPaddingMobile":24,"rightPaddingMobile":24,"containerBorderTopLeftRadius":20,"containerBorderTopRightRadius":20,"containerBorderBottomLeftRadius":20,"containerBorderBottomRightRadius":20} -->
<div class="wp-block-uagb-container uagb-block-e9dee57a"><!-- wp:uagb/info-box {"classMigrate":true,"tempHeadingDesc":"Custom online stores that convert — with WooCommerce, integrations, and fast checkout UX.","headingAlign":"left","headingColor":"var(\u002d\u002dast-global-color-4)","subHeadingColor":"var(\u002d\u002dast-global-color-4)","icon":"shopify","iconSize":24,"iconColor":"var(\u002d\u002dast-global-color-0)","headSpace":12,"block_id":"a2d2cfa9","iconLeftMargin":12,"iconRightMargin":12,"iconTopMargin":12,"iconBottomMargin":12,"imageWidth":205,"spacingLink":true,"headTopMargin":20,"headRightMargin":0,"headLeftMargin":0,"iconView":"Stacked","iconBackgroundColor":"var(\u002d\u002dast-global-color-7)","btnBorderTopWidth":1,"btnBorderLeftWidth":1,"btnBorderRightWidth":1,"btnBorderBottomWidth":1,"btnBorderTopLeftRadius":0,"btnBorderTopRightRadius":0,"btnBorderBottomLeftRadius":0,"btnBorderBottomRightRadius":0,"btnBorderStyle":"solid","btnBorderColor":"#333"} -->
<div class="wp-block-uagb-info-box uagb-block-a2d2cfa9 uagb-infobox__content-wrap  uagb-infobox-icon-above-title uagb-infobox-image-valign-top"><div class="uagb-ifb-content"><div class="uagb-ifb-icon-wrap"><div class="uagb-iconbox-icon-wrap uagb-infobox-shape-circle"><svg xmlns="https://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M388.3 104.1a4.66 4.66 0 0 0 -4.4-4c-2 0-37.23-.8-37.23-.8s-21.61-20.82-29.62-28.83V503.2L442.8 472S388.7 106.5 388.3 104.1zM288.6 70.47a116.7 116.7 0 0 0 -7.21-17.61C271 32.85 255.4 22 237 22a15 15 0 0 0 -4 .4c-.4-.8-1.2-1.2-1.6-2C223.4 11.63 213 7.63 200.6 8c-24 .8-48 18-67.25 48.83-13.61 21.62-24 48.84-26.82 70.06-27.62 8.4-46.83 14.41-47.23 14.81-14 4.4-14.41 4.8-16 18-1.2 10-38 291.8-38 291.8L307.9 504V65.67a41.66 41.66 0 0 0 -4.4 .4S297.9 67.67 288.6 70.47zM233.4 87.69c-16 4.8-33.63 10.4-50.84 15.61 4.8-18.82 14.41-37.63 25.62-50 4.4-4.4 10.41-9.61 17.21-12.81C232.2 54.86 233.8 74.48 233.4 87.69zM200.6 24.44A27.49 27.49 0 0 1 215 28c-6.4 3.2-12.81 8.41-18.81 14.41-15.21 16.42-26.82 42-31.62 66.45-14.42 4.41-28.83 8.81-42 12.81C131.3 83.28 163.8 25.24 200.6 24.44zM154.1 244.6c1.6 25.61 69.25 31.22 73.25 91.66 2.8 47.64-25.22 80.06-65.65 82.47-48.83 3.2-75.65-25.62-75.65-25.62l10.4-44s26.82 20.42 48.44 18.82c14-.8 19.22-12.41 18.81-20.42-2-33.62-57.24-31.62-60.84-86.86-3.2-46.44 27.22-93.27 94.47-97.68 26-1.6 39.23 4.81 39.23 4.81L221.4 225.4s-17.21-8-37.63-6.4C154.1 221 153.8 239.8 154.1 244.6zM249.4 82.88c0-12-1.6-29.22-7.21-43.63 18.42 3.6 27.22 24 31.23 36.43Q262.6 78.68 249.4 82.88z"></path></svg></div></div><div class="uagb-ifb-title-wrap"><h3 class="uagb-ifb-title">E-commerce Stores</h3></div><p class="uagb-ifb-desc">Custom online stores that convert — with WooCommerce, integrations, and fast checkout UX.</p></div></div>
<!-- /wp:uagb/info-box --></div>
<!-- /wp:uagb/container --></div>
<!-- /wp:uagb/container --></div></div>
<!-- /wp:uagb/container -->

---

## Действия

1. Пройди по коду плагина `/ultimate-addons-for-gutenberg/`
2. Найди, как определяются блоки (через `registerBlockType`, `block.json`, `edit`, `save`)
3. Общие наблюдения о том как формируются json блоков пиши в /base-knowledge.md
Файл должен быть Markdown‑справочником, по которому ты будешь ориентироваться при будущей генерации блоков.
4. В папке /examples создай список файлов, который соответствует названиям блоков которые есть в спектра. Названия файлов должны быть в виде container.notes.md, info-box.notes.md, *.notes.md. Если
файл с именем уже есть в папке, пересоздавать не нужно, только писать туда наблюдения.
5. Пиши свои выводы о том как формируются блоки и валидный гутенберг код каждого блока в эти файлы /examples/*.notes.md, где * имя каждого отдельного блока.
Если файл уже существует — **дополняй его**, не пересоздавай и не дублируй информацию. Структурируй записи по разделам, если нужно.
6. На этапе изучения не выдумывай новые параметры. Все наблюдения фиксируй строго на основе реального кода Spectra — блоков и их логики и аттрибутов. Позже ты сможешь использовать эти знания для генерации валидных блоков.
---
### Что писать в /examples/*.notes.md

- Где и как они регистрируются
- Какие у них атрибуты
- Как они отображаются в редакторе и при сохранении
- Какие поля попадают в JSON
- Как формировать валидный код для вставки в гутенберг редактор.
Файл должен быть Markdown‑справочником, по которому ты будешь ориентироваться при будущей генерации блоков.

---


## Источники

- `/base-knowledge.md` — файл, содержащий:
  - общие наблюдения о формировании блоков Spectra
  - пути к ключевым файлам и папкам, в которых лежат настройки и логика конкретных блоков (`block.json`, `edit.js`, `save.js` и т.п.)
  - список использованных файлов для каждого блока (в разделе "Used Files")

- `/examples/*.notes.md` — наблюдения по каждому отдельному блоку.
  - Название файла соответствует имени блока: `container.notes.md`, `info-box.notes.md` и т.п.
  - Каждый файл содержит:
    - где и как регистрируется блок
    - какие у него атрибуты
    - как он отображается в редакторе и при сохранении
    - какие поля попадают в JSON

---
