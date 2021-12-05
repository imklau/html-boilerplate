# 🦾 HTML boilerplate

A static HTML, CSS, JS boilerplate built with Parcel.

## ✨ Features

- Dev server & hot reloading
- Minifiers for JavaScript, CSS, HTML, and SVG
- Image optimization
- Linters for JS and SCSS
- ITCSS architecture
- [normalize.css](https://necolas.github.io/normalize.css/) included

## 🚀 Quick start

Make sure you have node +14 and npm +7 installed, then run:

```
npx @imklau/html-boilerplate <project-name>
```

## 👩🏻‍💻 Available commands:

- `yarn start` - runs the app in the development mode. (`localhost:1234` by default)
- `yarn build` - builds the app for production, files are saved to the `public` folder
- `yarn lint` - runs eslint to check all your files in the `src` directory
- `yarn format` - runs prettier to format all your files in the `src` directory

## 🌳 Folder structure

```
├── src
│   ├── assets
│   ├── js
│   ├── styles
│   │  ├── components
│   │  ├── elements
│   │  ├── generic
│   │  ├── objects
│   │  ├── settings
│   │  ├── tools
│   │  ├── utilities
│   │  └── main.scss
│   ├── index.html
│   └── about.html
├── package.json
├── .eslintrc
└── .prettierrc
```

### Production

The production mode automatically bundles and optimizes your application for production. It can be run using the build command: `yarn build`.

#### Minification

Minifiers for JavaScript, CSS, HTML, and SVG are included out of the box. By default, minification is enabled when using the build command.

#### Image optimization

Parcel supports resizing, converting, and optimizing images. You can use query parameters when referencing an image in HTML, CSS, or JavaScript to specify which format and size the image should be converted to.

[Parcel Images](https://parceljs.org/recipes/image/)

```html
<picture>
  <source
    type="image/webp"
    srcset="image.jpg?as=webp&width=400, image.jpg?as=webp&width=800 2x"
  />
  <source
    type="image/jpeg"
    srcset="image.jpg?width=400, image.jpg?width=800 2x"
  />
  <img src="image.jpg?width=400" width="400" />
</picture>
```

#### ITCSS

The SCSS file structure follows the ITCSS architecture.

ITCSS stands for Inverted Triangle CSS. It helps you organize your project CSS files in such a way that you can better deal with CSS specifics like global namespace, cascade and selectors specificity.

The main idea of ITCSS is that it separates your CSS codebase into several sections (called layers).

Those layers are:

- **Settings** – used with preprocessors and contain font, colors definitions, etc.
- **Tools** – globally used mixins and functions. It’s important not to output any CSS in the first 2 layers.
- **Generic** – reset and/or normalize styles, box-sizing definition, etc. This is the first layer which generates actual CSS.
- **Elements** – styling for bare HTML elements (like H1, A, etc.). These come with default styling from the browser so we can redefine them here.
- **Objects** – class-based selectors which define undecorated design patterns, for example the media object known from OOCSS
- **Components** – specific UI components. This is where most of our work takes place. We often compose UI components of Objects and Components
- **Utilities** – utilities and helper classes with ability to override anything which goes before in the triangle, e.g. hide helper class

More information [here](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)

## 📃 License

This project is available under the WTFPL license.
