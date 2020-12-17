# dfaiv-dev.github.io

### Run
Just a static `index.html` page (no Jekyll or any other static site generator). There is [some tooling](#stack) to help with build watching and auto reloading during development.

* `npm install` to load any dependencies
* `npm start` to watch the theme css and enable auto reload of the `index.html`
* `src/theme` for theme styling.
    * output is `assets/styles.css` - should probably be optimized. [See TODO](#todo).

### TODO
* [Optimize Tailwind CSS](https://tailwindcss.com/docs/optimizing-for-production#basic-usage)

### Hosting
[![Netlify Status](https://api.netlify.com/api/v1/badges/6cb17eb2-20b0-4658-a515-c95032107376/deploy-status)](https://app.netlify.com/sites/dfaiv-dev-profile-01/deploys)

### Stack
#### [tailwind css](https://tailwindcss.com/)
One of my favorite parts of Bootstrap is the utility classes. This is _all_ utility classes.

Related dependencies:
* [postcss](https://postcss.org/) - what `tailwind` uses.
* [postcss-cli](https://github.com/postcss/postcss-cli) - allows running `postcss` from an npm script. _eg_ `"build:theme": "postcss src/theme/theme.css -o styles.css"`
  
#### [npm-watch](https://github.com/M-Zuber/npm-watch)
Rebuild css theme on changes.

#### [live-server](https://www.npmjs.com/package/live-server)
Allows serving the static `index.html` file with auto reload. I'm so lazy.

#### [npm-run-all](https://www.npmjs.com/package/npm-run-all)
Allows running both `npm-watch` and `live-server` in parallel from the `npm start` script. `"start": "run-p watch serve"`

#### FavIcon Generation
[https://realfavicongenerator.net/](https://realfavicongenerator.net/)

Generates all icons, manifests, sizes. Was the best out of the top three google results. I donated.
