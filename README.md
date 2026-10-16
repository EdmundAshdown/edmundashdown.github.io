# edmundashdown.github.io

Central hub for [edmundashdown.github.io](https://edmundashdown.github.io/) — a single
static `index.html` listing the apps.

Each app lives in **its own repo** with its own GitHub Pages site, and the hub links to it
at `/<repo>/` (e.g. `iron-log`, `magiccitydetail`). A link to an app whose repo has no
Pages site enabled will 404, so add the card only once the app is deployed.

## Styling

Tailwind is compiled to a static stylesheet. There is no CDN and no runtime build.

**`css/styles.css` is committed** — GitHub Pages serves this repo statically and does not
run a build step, so the built file must be in the repo.

After editing `index.html` (especially when adding new utility classes), rebuild and
commit the output:

```sh
npm install        # first time only
npm run build:css  # rewrites css/styles.css
```

`npm run watch:css` rebuilds on save while working locally.

Source of truth for the stylesheet is `src/input.css` plus the theme in
`tailwind.config.js` (the `brand` colour ramp and `darkMode: 'class'`). Tailwind scans
`./index.html` for class names, including classes that appear only inside JavaScript
strings.
