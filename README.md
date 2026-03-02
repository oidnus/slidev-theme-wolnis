# Slidev Theme — DS

A dark [Slidev](https://sli.dev/) theme for IT training and conference presentations by [Damian Ślimak](https://damianslimak.pl).

Based on [slidev-theme-nmt](https://github.com/AdyGCode/slidev-theme-nmt) by Adrian Gould, which itself builds on ["The Unnamed" VS Code theme](https://marketplace.visualstudio.com/items?itemName=eliostruyf.vscode-unnamed-theme) by [Elio Struyf](https://elio.dev).

## Usage

Add the following front-matter to your `slides.md`:

```yaml
---
theme: gh:oidnus/slidev-theme-ds
---
```

Start Slidev and the theme will be installed automatically.

## Layouts

The theme provides the following layouts:

- `cover` — title slide
- `about-me` — presenter introduction with photo
- `center` — centered content
- `default` — standard content slide
- `section` — section divider
- `end` — closing slide
- `fact` — highlight a key metric
- `quote` — styled quotation
- `comparison` — side-by-side comparison
- `grid` — 4-section grid (tl, tr, bl, br)
- `two-cols` — two equal columns
- `two-cols-2-1` — two columns (2:1 ratio)
- `image-right` — content with image on right
- `image-left` — content with image on left
- `image-full` — full-bleed background image
- `theory-code` — theory on left, code on right
- `timeline` — 3-step timeline
- `takeaways` — key takeaways list

### Cover

#### Usage

```yaml
---
layout: cover
---
```

### About me

#### Usage

```yaml
---
layout: about-me

helloMsg: O Mnie
name: Damian Ślimak
position: left
school: "Wykładowca na Uniwersytecie"
company: "Twórca nawigator.ai"
website: "damianslimak.pl"
website2: "nawigator.ai"
email: "info@damianslimak.pl"
imageSrc: /theme/assets/damian.jpg
---
```

### Two columns

#### Usage

```yaml
---
layout: two-cols
---

# Left

This shows on the left

::right::

# Right

This shows on the right
```

### Two columns 2:1

#### Usage

```yaml
---
layout: two-cols-2-1
---

# Left

This shows on the left

::right::

# Right

This shows on the right
```

## Components

### Announcement component

A small component to add announcements, callouts, and notes to slides.

Used in the form:

```vue
<Announcement type="default" title="Default Note" inline compact >
    Just something to think about
</Announcement>
```

- Types: `brainstorm`, `duration`, `idea`, `default`, `info`, `important`, `priority`, `warning`, `error`
- Options:
    - `compact` — smaller version (default `false`)
    - `title="..."` — title text (optional)
    - `inline` — allow multiple on a line (default `false`)
    - `width="fit|full"` — resize to full width or fit content (default `fit`)

#### Icon Override

```vue
<Announcement type="info" title="Heads up">
    Custom icon via slot
    <template #icon>
        <i class="i-fa7-solid-user-ninja h-5 w-5 mt-0.5"></i>
    </template>
</Announcement>
```

## Credits

- Original theme: [The Unnamed](https://github.com/estruyf/slidev-theme-the-unnamed) by Elio Struyf (MIT License)
- NMT fork: [slidev-theme-nmt](https://github.com/AdyGCode/slidev-theme-nmt) by Adrian Gould

## License

[MIT](./LICENSE.md)
