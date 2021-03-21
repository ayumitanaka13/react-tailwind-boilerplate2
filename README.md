# Getting Started with Create React App with TailwindCSS

#### 1. Create React App with npm

`create-react-app {app-name} --use-npm`

#### 2. Move to App directory

`cd {app-name}`

#### 3. Install postcss and autoprefixer

`npm i -D tailwindcss postcss-cli autoprefixer`

#### 4. Install tailwind

`npm install -D tailwindcss@npm:@tailwindcss/postcss7-compat @tailwindcss/postcss7-compat postcss@^7 autoprefixer@^9 `

#### 5. Install and configure CRACO

`npm install @craco/craco`

Once it is installed, change "scripts" in your "package.json".

```
    "scripts": {
     "start": "craco start",
     "build": "craco build",
     "test": "craco test",
      "eject": "react-scripts eject"
    },
```

#### 6. Create craco config file

`touch craco.config.js`

In this file, write like this.

```
module.exports = {
  style: {
    postcss: {
      plugins: [
        require('tailwindcss'),
        require('autoprefixer'),
      ],
    },
  },
}
```

#### 7. Create tailwind config file

`npx tailwindcss init`

In this file, write like this.

```
module.exports = {
  purge: [],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
}
```

If you want to remove unused styles, you can change it like this.

```
  module.exports = {
   purge: [],
   purge: ['./src/**/*.{js,jsx,ts,tsx}', './public/index.html'],
    darkMode: false, // or 'media' or 'class'
    theme: {
      extend: {},
    },
    variants: {
      extend: {},
    },
    plugins: [],
  }
```

#### 8. Modifiy index.css

In this file, write like this.

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Make sure "index.css" file is imported in "index.js".

#### 9. Run React app

`npm start`

#### Reference

[Install Tailwind CSS with Create React App](https://tailwindcss.com/docs/guides/create-react-app)
