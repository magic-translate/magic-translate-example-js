# Magic Translate JavaScript Example

This is an example website with Magic Translate integrated through a single
script tag, without any framework or build step. You can see it deployed here:
https://magic-translate.github.io/magic-translate-example-js/

## Getting Started

First create a Magic Translate account at https://magictranslate.io/signin to
obtain your API key. No credit card is required for the Free plan.

Then replace `YOUR_API_KEY` in `index.html` with your API key, and serve the
folder with any web server, for example:

```bash
npx serve .
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the
result.

## How it works

Magic Translate is set up with one script tag in `index.html`:

```html
<script
  src="https://cdn.jsdelivr.net/npm/@magic-translate/js@1/dist/magic-translate.min.js"
  data-api-key="YOUR_API_KEY"
  data-language="en"
  defer
></script>
```

Any text or HTML inside a `<t>` element is translated:

```html
<t>Get started with</t>
```

The attributes listed in `data-t-attrs` are translated too:

```html
<input placeholder="Type your name" data-t-attrs="placeholder" />
```

The small script at the end of `index.html` switches the language with
`magicTranslate.setLanguage()`, and changes the greeting while you type your
name. Changed content is translated again automatically.

## Learn More

To learn more about Magic Translate please visit
[https://magictranslate.io](https://magictranslate.io), and see the
[@magic-translate/js](https://www.npmjs.com/package/@magic-translate/js)
package for the full API.

## Deploy on GitHub Pages

`.github/workflows/deploy.yml` deploys the page to GitHub Pages on every push
to `main`, with the API key from the `MAGIC_TRANSLATE_API_KEY` repository
variable filled in. The key is visible in the page's source, as with any
client-side Magic Translate integration.
