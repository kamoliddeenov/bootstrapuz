---
layout: docs
title: Bootstrap bilan ishlashni boshlang
description: Bootstrap - bu kuchli, xususiyatlarga ega frontend materiallari to'plami. Bir necha daqiqada prototipdan tortib mukammal veb-saytgacha bo'lgan hamma narsani yarating.
group: getting-started
aliases:
  - "/docs/5.2/getting-started/"
  - "/docs/getting-started/"
  - "/getting-started/"
toc: true
---

## Tezkor boshlash

Bootstrap-ning ishlab chiqarishga tayyor CSS va JavaScript-ni CDN orqali hech qanday qurish bosqichlarisiz qo'shish orqali boshlang. Buni [Bootstrap CodePen demosi](https://codepen.io/team/bootstrap/pen/qBamdLj) bilan amalda ko'ring.

<br>

1. **Loyihangiz uchun yangi `index.html` nomli fayl yarating.** Veb saytingiz mobil qurilmalarda [to'g'ri ya'ni moslashuvchan shaklda](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag) ishlashi uchun `<meta name="viewport">` tegini qo'shing.

   ```html
   <!doctype html>
   <html lang="en">
     <head>
       <meta charset="utf-8">
       <meta name="viewport" content="width=device-width, initial-scale=1">
       <title>Bootstrap demo</title>
     </head>
     <body>
       <h1>Salom, Dunyo!</h1>
     </body>
   </html>
   ```

2. **Bootstrapning CSS va JS fayllarini qo'shing.** CSS ulash uchun  `<head>` tegi ichiga `<link>` attributi orqali qo'shing va `<script>` tegi orqali JavaScript faylini ulab oling (popper, dropdown, tooltip va shu kabi funksiyalar ishlashi uchun), bu `</body>` tegi yopilishidan avval qo'shiladi. [CDN linklari](#cdn-links) haqida ko'proq ma'lumotlarni o'rganib chiqing.

   ```html
   <!doctype html>
   <html lang="en">
     <head>
       <meta charset="utf-8">
       <meta name="viewport" content="width=device-width, initial-scale=1">
       <title>Bootstrap demo</title>
       <link href="{{< param "cdn.css" >}}" rel="stylesheet" integrity="{{< param "cdn.css_hash" >}}" crossorigin="anonymous">
     </head>
     <body>
       <h1>Hello, world!</h1>
       <script src="{{< param "cdn.js_bundle" >}}" integrity="{{< param "cdn.js_bundle_hash" >}}" crossorigin="anonymous"></script>
     </body>
   </html>
   ```

   You can also include [Popper](https://popper.js.org/) and our JS separately. If you don't plan to use dropdowns, popovers, or tooltips, save some kilobytes by not including Popper.

   ```html
   <script src="{{< param "cdn.popper" >}}" integrity="{{< param "cdn.popper_hash" >}}" crossorigin="anonymous"></script>
   <script src="{{< param "cdn.js" >}}" integrity="{{< param "cdn.js_hash" >}}" crossorigin="anonymous"></script>
   ```

3. **Hello, world!** Open the page in your browser of choice to see your Bootstrapped page. Now you can start building with Bootstrap by creating your own [layout]({{< docsref "/layout/grid" >}}), adding dozens of [components]({{< docsref "/components/buttons" >}}), and utilizing [our official examples]({{< docsref "/examples" >}}).

## CDN links

As reference, here are our primary CDN links.

{{< bs-table >}}
| Description | URL |
| --- | --- |
| CSS | `{{< param "cdn.css" >}}` |
| JS | `{{< param "cdn.js_bundle" >}}` |
{{< /bs-table >}}

You can also use the CDN to fetch any of our [additional builds listed in the Contents page]({{< docsref "/getting-started/contents" >}}).

## Next steps

- Read a bit more about some [important global environment settings](#important-globals) that Bootstrap utilizes.

- Read about what's included in Bootstrap in our [contents section]({{< docsref "/getting-started/contents/" >}}) and the list of [components that require JavaScript](#js-components) below.

- Need a little more power? Consider building with Bootstrap by [including the source files via package manager]({{< docsref "/getting-started/download#package-managers" >}}).

- Looking to use Bootstrap as a module with `<script type="module">`? Please refer to our [using Bootstrap as a module]({{< docsref "/getting-started/javascript#using-bootstrap-as-a-module" >}}) section.

## JS components

Curious which components explicitly require our JavaScript and Popper? Click the show components link below. If you're at all unsure about the general page structure, keep reading for an example page template.

<details>
<summary class="bd-summary-link mb-3">Show components requiring JavaScript</summary>
{{< markdown >}}
- Alerts for dismissing
- Buttons for toggling states and checkbox/radio functionality
- Carousel for all slide behaviors, controls, and indicators
- Collapse for toggling visibility of content
- Dropdowns for displaying and positioning (also requires [Popper](https://popper.js.org/))
- Modals for displaying, positioning, and scroll behavior
- Navbar for extending our Collapse and Offcanvas plugins to implement responsive behaviors
- Navs with the Tab plugin for toggling content panes
- Offcanvases for displaying, positioning, and scroll behavior
- Scrollspy for scroll behavior and navigation updates
- Toasts for displaying and dismissing
- Tooltips and popovers for displaying and positioning (also requires [Popper](https://popper.js.org/))
{{< /markdown >}}
</details>

## Important globals

Bootstrap employs a handful of important global styles and settings, all of which are almost exclusively geared towards the *normalization* of cross browser styles. Let's dive in.

### HTML5 doctype

Bootstrap requires the use of the HTML5 doctype. Without it, you'll see some funky and incomplete styling.

```html
<!doctype html>
<html lang="en">
  ...
</html>
```

### Responsive meta tag

Bootstrap is developed *mobile first*, a strategy in which we optimize code for mobile devices first and then scale up components as necessary using CSS media queries. To ensure proper rendering and touch zooming for all devices, add the responsive viewport meta tag to your `<head>`.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

You can see an example of this in action in the [quick start](#quick-start).

### Box-sizing

For more straightforward sizing in CSS, we switch the global `box-sizing` value from `content-box` to `border-box`. This ensures `padding` does not affect the final computed width of an element, but it can cause problems with some third-party software like Google Maps and Google Custom Search Engine.

On the rare occasion you need to override it, use something like the following:

```css
.selector-for-some-widget {
  box-sizing: content-box;
}
```

With the above snippet, nested elements—including generated content via `::before` and `::after`—will all inherit the specified `box-sizing` for that `.selector-for-some-widget`.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot

For improved cross-browser rendering, we use [Reboot]({{< docsref "/content/reboot" >}}) to correct inconsistencies across browsers and devices while providing slightly more opinionated resets to common HTML elements.

## Community

Stay up-to-date on the development of Bootstrap and reach out to the community with these helpful resources.

- Read and subscribe to [The Official Bootstrap Blog]({{< param blog >}}).
- Ask and explore [our GitHub Discussions](https://github.com/twbs/bootstrap/discussions).
- Chat with fellow Bootstrappers in IRC. On the `irc.libera.chat` server, in the `#bootstrap` channel.
- Implementation help may be found at Stack Overflow (tagged [`bootstrap-5`](https://stackoverflow.com/questions/tagged/bootstrap-5)).
- Developers should use the keyword `bootstrap` on packages that modify or add to the functionality of Bootstrap when distributing through [npm](https://www.npmjs.com/search?q=keywords:bootstrap) or similar delivery mechanisms for maximum discoverability.

You can also follow [@getbootstrap on Twitter](https://twitter.com/{{< param twitter >}}) for the latest gossip and awesome music videos.
