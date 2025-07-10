**Промпт: Работа с контейнерами Spectra (UAG) — Полное руководство для ИИ и разработчиков**

---

В непонятных ситуациях, если не знаешь есть ли свойства, аттрибуты или значения для настроек, проверяй в документации. Документация: https://github.com/brainstormforce/wp-spectra
Ключевые директории для изучения:
- /includes/blocks/ - информация о каждом блоке
- /blocks-config/ - настройки конфигурации блоков
- Файлы attributes.php для каждого блока содержат все доступные атрибуты

### 🔹 ОБЩАЯ СТРУКТУРА КОНТЕЙНЕРА
Контейнер — универсальный блок, служит для группировки и размещения других блоков в структуре макета.
```html
<!-- wp:uagb/container {"block_id":"", ... } -->
<div class="wp-block-uagb-container uagb-block-...">
  ...внутренние блоки...
</div>
<!-- /wp:uagb/container -->
```
- `block_id`: необязателен (Spectra сгенерирует сам).
- `layout`: принимает значения `"grid"`, `"flex"` или не указывается.

---

### 🔹 ОТСТУПЫ (PADDING)

#### ✅ **Родительский контейнер:** отступы НЕ задаются, если они уже заданы через CSS `padding: 80px 100px`.

#### Стандартные свойства:
```json
"topPaddingDesktop": 20,
"bottomPaddingDesktop": 20,
"leftPaddingDesktop": 20,
"rightPaddingDesktop": 20,
"paddingType": "px"
```

---

### 🔹 СЕТКА (GRID) и КОЛОНКИ
```json
"layout": "grid",
"gridColumnDesktop": [
  {"default":"custom","custom":{"unit":"fr","value":1}},
  {"default":"custom","custom":{"unit":"fr","value":1}}
]
```
- Для внутренних контейнеров, входящих в сетку:
```json
"isGridCssInParent": true,
"gridColumnSpan": 1,
"gridRowSpan": 1
```

---

### 🔹 ФОНЫ
```json
"backgroundType": "color" | "image" | "gradient",
"backgroundColor": "#000000",
"gradientValue": "linear-gradient(...)"
```

#### Адаптивные изображения фона:
```json
"backgroundImageDesktop": {...},
"backgroundImageTablet": {...},
"backgroundImageMobile": {...}
```

---

### 🔹 OVERLAY (НАЛОЖЕНИЕ)

#### Типы:
```json
"overlayType": "color" | "gradient" | "image",
"overlayOpacity": 0.6
```

#### Если `overlayType = "image"`:
```json
"backgroundOverlayImageDesktop": {...},
"backgroundOverlayImageTablet": {...},
"backgroundOverlayImageMobile": {...}
```

#### Дополнительно:
```json
"backgroundAttachmentOverlayDesktop": "fixed" | "scroll",
"backgroundSizeOverlayMobile": "cover" | "contain" | "auto"
```

---

### 🔹 ТЕКСТ И ССЫЛКИ ВНУТРИ
```json
"textColor": "#ffffff",
"linkColor": "#00aaff",
"linkHoverColor": "#ff0000"
```

---

### 🔹 ТЕНЬ (BOX SHADOW)
```json
"boxShadowColor": "rgba(...)" ,
"boxShadowVOffset": 4,
"boxShadowBlur": 12,
"boxShadowSpread": 0
```
#### Hover-состояние:
```json
"boxShadowColorHover": "#fff",
"boxShadowVOffsetHover": 10,
"boxShadowBlurHover": 30,
"boxShadowSpreadHover": 5,
"boxShadowPositionHover": "inset"
```

> Примечание: свойства тени **не адаптивные** — одно значение для всех устройств.

---

### 🔹 POSITION: STICKY
```json
"UAGPosition": "sticky",
"UAGStickyLocation": "top" | "bottom",
"UAGStickyOffset": 50,
"UAGStickyRestricted": true
```

---

### 🔹 ВИДИМОСТЬ НА УСТРОЙСТВАХ
```json
"UAGHideDesktop": true,
"UAGHideTab": true,
"UAGHideMob": true,
"UAGResponsiveConditions": true
```
- Класс автоматически добавляется: `uag-hide-tab`, `uag-hide-desktop`, `uag-hide-mob`

---

### 🔹 Z-INDEX (АДАПТИВНЫЙ)
```json
"zIndex": 1000,
"zIndexTablet": 5,
"zIndexMobile": 3
```

---

### 🔹 ДОПОЛНИТЕЛЬНО
- `variationSelected: true` — активирует пользовательскую стилизацию контейнера
- `isBlockRootParent: true` — используется для корневого контейнера страницы

---

### 🌐 ПРИМЕР СТРУКТУРЫ
```json
{
  "layout": "grid",
  "backgroundType": "image",
  "backgroundImageDesktop": {"url": "https://..."},
  "overlayType": "gradient",
  "overlayOpacity": 0.5,
  "topPaddingDesktop": 80,
  "textColor": "#fff",
  "zIndex": 10
}
```

---