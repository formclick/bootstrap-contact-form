# Bootstrap contact form

A Bootstrap 5 contact form that sends submissions with the [Formclick](https://www.formclick.io) form API. One HTML file, no build step, no backend: copy it into any Bootstrap site and every message lands in your inbox and your Formclick dashboard.

## Quick start

1. Create a free account at [formclick.io](https://www.formclick.io), create a form and copy its **access key**.
2. Open [`index.html`](index.html) and replace `YOUR_ACCESS_KEY` with your key.
3. Open the page in a browser and send a test message.

Already using Bootstrap? Copy just the `<form>` and the Formclick `<script>` tag into your page.

## How it works

```html
<form action="https://api.formclick.io/submit" method="POST"
      data-success-msg="Thanks! Your message has been sent.">
  <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY">
  <input type="email" class="form-control" name="email" required>
  <textarea class="form-control" name="message" required></textarea>
  <button type="submit" class="btn btn-primary">Send message</button>
</form>

<script src="https://cdn.formclick.io/formclick.min.js"></script>
```

| Piece | Why it's there |
| --- | --- |
| `action` + `method="POST"` | Sends the form to Formclick. Works even with JavaScript turned off. |
| Bootstrap classes | `form-control`, `form-label`, the grid (`row g-3`, `col-md-6`) and `btn btn-primary` style the form; Formclick doesn't need any of them. |
| `formclick.min.js` | Submits in the background, shows a loading state and an inline success or error message. |
| `data-success-msg` | The message shown after a successful submit. |
| `access_key` | Identifies your form. It can only create submissions, so it's safe in public HTML. |
| `subject` | Sets the subject line of your notification email. |
| `_honeypot` | A hidden spam trap. Bots fill it and those submissions are silently discarded. |

Bootstrap 5.3.9 is loaded from jsDelivr with a Subresource Integrity hash, so the browser rejects the file if it's ever altered.

## Customise it

- **More fields:** add any input with a `name`; it's included in your email and dashboard.
- **Your own thank-you page:** add `<input type="hidden" name="redirect" value="https://yourwebsite.com/thanks.html">` (same website on the Free plan).
- **File uploads:** add `<input type="file" name="resume">`; the Formclick script uploads it (plans with file uploads, 5 MB per file).

## Learn more

- [Form API reference](https://www.formclick.io/form-api)
- [Tailwind CSS version](https://github.com/formclick/tailwind-contact-form)
- [All Formclick examples](https://github.com/formclick/contact-form-examples)

## License

[MIT](LICENSE)
