# web-projects-checklist

## :mag: Validation

- HTML — http://validator.w3.org/nu/.

## :cop: Security

## :runner: Performance

## :wheelchair: A11y

## :mortar_board: UX

### Tag `<a>`

#### Attribute `download` with a value or without the one.

1. Prompts the user to save the linked URL instead of navigating to it. For instance:

   ```html
   <a href="document.pdf" download>
     Save me as document.pdf
   </a>
   
   <a href="1h24v9lj.jpg" download="other-document">
     Save me as other-document.jpg
   </a>
   ```

1. Use different protocols in attribute `href`:

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
