# How to use tailwind CSS with Django

## Referenced from
https://stackoverflow.com/questions/63392426/how-to-use-tailwindcss-with-django

## Usage

$ mkdir jstoolchain

$ cd jstoolchain

$ npm init -y

$ npm install tailwind postcss-cli autoprefixer

$ npx tailwind init

$ touch postcss.config.js

```js
module.exports = {
    plugins: [
        require('tailwindcss'),
        require('autoprefixer')
    ]
}
```

$ mkdir css

$ touch css/tailwind.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

package.json

```json
"scripts": {
    "build": "postcss css/tailwind.css -o ../static/css/tailwind-output.css"
  },
```

$ npm run-script build

base.html

```html
{% load static %}

<head>
  <link rel="stylesheet" href="{% static 'css/tailwind-output.css' %}">
</head>
```
