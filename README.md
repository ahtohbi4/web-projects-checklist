# web-projects-checklist

## :mag: Validation

- HTML — http://validator.w3.org/nu/.

## :cop: Security

### Attribute `rel="noopener"` for links with `target="_blank"`

```html
<a href="evil.com" rel="noopener" target="_blank">
  Click Me!
</a>
```

## :runner: Performance

### Fonts

#### Preload main style of custom font

For instance regular style.

```html
<link rel="preload" href="rubik-regular-latin.woff2"
      as="font" type="font/woff2"
      crossorigin>
```

#### CSS property `font-display` with values `swap` or `fallback`

```css
@font-face {
    font-family: 'DIN Condensed';
    font-display: swap;
    src: url('din.woff2') format('woff2'),
         url('din.woff') format('woff');
}
```

See
- https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display
- https://github.com/soflyy/oxygen-bugs-and-features/issues/337

## :wheelchair: A11y

### The size of the target for pointer inputs is at least 44×44px

See https://www.w3.org/WAI/WCAG21/Understanding/target-size.html

### Attributes `aria-label`, `aria-describedby` and `aria-labelledby`

See:
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-describedby_attribute
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute

## :mortar_board: UX

### Tag `<a>`

#### Attribute `download` with a value or without the one.

Prompts the user to save the linked URL instead of navigating to it. For instance:

```html
<a href="document.pdf" download>
  Save me as document.pdf
</a>

<a href="1h24v9lj.jpg" download="other-document">
  Save me as other-document.jpg
</a>
```

See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#download

#### Different protocols in attribute `href`:

- `http:`/`https:` — Opens a hyperlink.
- `mailto:` — Opens default mail program, creates a new message with the `To` field already filled out. Additional `GET`-parameters for the link:
  - `subject` — the `Subject` field filled out,
  - `cc` — the `Carbon Copy` field filled out,
  - `bcc` — the `Blind Carbon Copy` field filled out,
  - `body` — the `Body` field filled out.
- `tel:` — Opens the calling interface on a phone.
- `skype:` — Opens Skype if it is registered.
- `slack:` — Opens Slack if it is registered.
- ...

For instance:

```html
Get in touch by

<a href="tel:79999999999999">
  Phone
</a>

<a href="skype:examplecom">
  Skype
</a>

<a href="mailto:info@example.com?cc=sales@example.com,media@example.com&bcc=granny@gmail.com&subject=I%20want%20to%20subscribe&body=I%20want%20to%20subscribe">
  Email
</a>
```

See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href

#### CSS property `touch-action: manipulation`

Prevents of 300ms delaying after a tap on touch devices.

See https://developer.mozilla.org/ru/docs/Web/CSS/touch-action#manipulation

#### CSS property `text-decoration-skip-ink: auto`

Underlines and overlines are only drawn where they do not touch or closely approach a glyph.

See https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink
