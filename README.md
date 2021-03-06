# react-parcel-boilerplate

> Quick and easy boilerplate startup with parcel

## Features

- Parcel
- Babel 6
- Babel-eslint
- Eslint
- Prettier (on save)
- Airbnb Eslint Rules
- Styled Components 3
- React 16

## Getting started

```bash
yarn
yarn start
```

Then open `http://localhost:1234` and edit `src/index.js` and press save. Parcel
will automagically hot reload you files whenever you make changes.

## Building for Production

```bash
npm run build
```

This will compile your JS and copy your `index.html` to the `dist` folder which
you can deploy wherever as a good ol' webpage.

## CSS

[Parcel uses PostCSS plugins to manage CSS assets](https://parceljs.org/transforms.html#postcss).
I've included `autoprefixer` for vendor prefixing with the same setup as
`create-react-app`. You can find and modify the PostCSS setup in `package.json`.
If you'd rather keep your PostCSS setup in a dotfile, you can delete the
`postcss` key from `package.json`, and place its contents in a `.postcssrc` file
too.

---

## Folder structure and relative paths

Keeping everything in the root directory obviously won't scale past a point.
Parcel is very flexible about folder structure, but there are

**a few gotchas**:

### Moving JS entry

When you do move index.js just make sure to update the `<script>` tag in
`index.html` so that it points to the correct relative path.

For example, if you want to move `index.js` to `src/index.js`, you would need
make the following change to `index.html`:

```bash
<   <script src="./index.js"></script>
---
>   <script src="./src/index.js"></script>
```

### Moving `index.html`

If you want to move `index.html`, you will need to update your npm scripts in
`package.json` with the new relative path.

---

## Deployment

Refer to the deployment guide in `create-react-app`, just note that you will
need to account for the fact that Parcel builds out to a `dist` directory, while
CRA builds to a `build` directory. You can make it identical by adding
`--out-dir build` to both `start` and `build` npm tasks in `package.json`.

---

# FAQs/Issue fixes

### I'm getting a long error message after `yarn`-ing regarding failing to install `fsevents`

This is fixed by running the following commands:

```bash
   $ rm yarn.lock
   $ yarn cache clean
   $ yarn install
```
