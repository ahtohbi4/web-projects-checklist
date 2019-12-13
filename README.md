# web-projects-checklist

## 1. :mag: Quality of code

### 1.1. Passing validation of HTML

Use validator http://validator.w3.org/nu/.

### 1.2. Passing Lighthouse audit in Google Chrome.

See:
- https://developers.google.com/speed/pagespeed/insights/
- https://developers.google.com/web/tools/lighthouse/

### 1.3. Passing audit from Firefox Accessibility Inspector

See https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector

<br>

## 2. :cop: Security

### 2.1. Attribute `rel="noopener"` for links with `target="_blank"`

```html
<a href="evil.com" rel="noopener" target="_blank">
  Click Me!
</a>
```

<br>

## 3. :runner: Performance

### 3.1. Fonts

#### 3.1.1. Preload main style of custom font

For instance regular style.

```html
<link rel="preload" href="rubik-regular-latin.woff2"
      as="font" type="font/woff2"
      crossorigin>
```

#### 3.1.2. CSS property `font-display` with values `swap` or `fallback`

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

<br>

## 4. :wheelchair: A11y

### 4.1. The size of the target for pointer inputs is at least 44×44px

See https://www.w3.org/WAI/WCAG21/Understanding/target-size.html

### 4.2. Attributes `aria-label`, `aria-describedby` and `aria-labelledby`

See:
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-describedby_attribute
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute

<br>

## 5. :mortar_board: UX

### 5.1. Turn off the auto-detection of phone numbers on mobile devices

For instance, some prices or IDs can be confused with the phone number.

```html
<meta name="format-detection" content="telephone=no">
```

You should have total control of phone number detection by using the protocol `tel:` for the tag `<a>`.

```html
<a href="tel:79999999999999">
  Call me!
</a>
```

### 5.2. Tag `<a>`

#### 5.2.1. Attribute `download` with a value or without the one.

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

#### 5.2.2. Different protocols in attribute `href`:

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

### 5.3. CSS property `touch-action: manipulation`

Prevents of 300ms delaying after a tap on touch devices.

See https://developer.mozilla.org/ru/docs/Web/CSS/touch-action#manipulation

### 5.4. CSS property `text-decoration-skip-ink: auto`

Underlines and overlines are only drawn where they do not touch or closely approach a glyph.

See https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink
