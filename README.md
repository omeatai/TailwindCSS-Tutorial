# TailwindCSS-Tutorial
Learn TailwindCSS by Ifeanyi Omeata

## Tutorial

---

### [1-TAILWINDCSS CRASH COURSE - NET NINJA](#)

+INTRODUCTION

<details>
  <summary>1. Tailwind via CLI </summary>

Check Node Version:

```bash
node -v
```

Create package.json file:

```bash
npm init -y
```

Install Tailwind CSS:

```bash
npm install -D tailwindcss
```

Create a tailwind.config.js file:

```bash
npx tailwindcss init
```

Configure your template paths:

tailwind.config.js:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./public/*.{html,js}"],
  //content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Add the Tailwind directives to your CSS:

src/styles.css:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Setup Package.json build:

package.json:

```json
"scripts": {
    "build-css": "tailwindcss build -i src/styles.css -o public/styles.css --watch"
  },
```

```json
{
  "name": "ninjafood",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build-css": "tailwindcss build -i src/styles.css -o public/styles.css --watch"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "tailwindcss": "^3.2.4"
  }
}
```

Start the Tailwind CLI build process:

```bash
npm run build-css
```

```bash
npx tailwindcss -i ./src/styles.css -o ./public/styles.css --watch
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

Compile and minify your CSS for production:

```bash
npx tailwindcss -i ./src/styles.css -o ./public/styles.css --minify
```

</details>

<details>
  <summary>2. HTML Template</summary>

public/index.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body class="text-gray-600">

    <div>
        <div>
        <nav>
            <div>
            <h1 class="font-bold uppercase">
                <a href="/">Food Ninja</a>
            </h1>
            </div>
            <ul>
            <li class="text-gray-700 font-bold">
                <a href="#">
                <span>Home</span>
                </a>
            </li>
            <li>
                <a href="#">
                <span>About</span>
                </a>
            </li>
            <li>
                <a href="#">
                <span>Contact</span>
                </a>
            </li>
            </ul>
        </nav>
        </div>

        <main>
        <div>
            <a href="#">Log in</a>
            <a href="#">Sign up</a>
        </div>

        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>

        <div>
            <h4 class="font-bold">Latest Recipes</h4>

            <div>
            <!-- cards go here -->
            <div>
                <img src="img/stew.jpeg" alt="stew">
                <div>
                <span>5 Bean Chili Stew</span>
                <span>Recipe by Mario</span>
                </div>
            </div>
            </div>

            <h4 class="font-bold">Most Popular</h4>

            <div>
            <!-- cards go here -->
            </div>
        </div>

        <div>
            <div>Load more</div>
        </div>
        </main>
    </div>

</body>
</html>
```

</details>

<details>
  <summary>3. Install Live Server</summary>

```bash
npm install -g live-server
```

Run Live Server:

```bash
live-server public
```

</details>

+TYPOGRAPHY

<details>
  <summary>4. Font Size</summary>

```html
<p class="text-sm ...">The quick brown fox ...</p>
<p class="text-base ...">The quick brown fox ...</p>
<p class="text-lg ...">The quick brown fox ...</p>
<p class="text-xl ...">The quick brown fox ...</p>
<p class="text-2xl ...">The quick brown fox ...</p>
```

```bash
Class                   Properties

text-xs	                font-size: 0.75rem; /* 12px */
                        line-height: 1rem; /* 16px */

text-sm	                font-size: 0.875rem; /* 14px */
                        line-height: 1.25rem; /* 20px */

text-base	            font-size: 1rem; /* 16px */
                        line-height: 1.5rem; /* 24px */

text-lg	                font-size: 1.125rem; /* 18px */
                        line-height: 1.75rem; /* 28px */

text-xl	                font-size: 1.25rem; /* 20px */
                        line-height: 1.75rem; /* 28px */

text-2xl	            font-size: 1.5rem; /* 24px */
                        line-height: 2rem; /* 32px */

text-3xl	            font-size: 1.875rem; /* 30px */
                        line-height: 2.25rem; /* 36px */

text-4xl	            font-size: 2.25rem; /* 36px */
                        line-height: 2.5rem; /* 40px */

text-5xl	            font-size: 3rem; /* 48px */
                        line-height: 1;

text-6xl	            font-size: 3.75rem; /* 60px */
                        line-height: 1;

text-7xl	            font-size: 4.5rem; /* 72px */
                        line-height: 1;

text-8xl	            font-size: 6rem; /* 96px */
                        line-height: 1;

text-9xl	            font-size: 8rem; /* 128px */
                        line-height: 1;
```

</details>

<details>
  <summary>5. Font Size change on Hover </summary>

```html
<a class="text-4xl hover:text-base" href="/">Food Ninja</a>
```

</details>

<details>
  <summary>6. Font Size change on media queries</summary>

```html
<a class="text-4xl lg:text-9xl" href="/">Food Ninja</a>
```

```html

Breakpoint prefix	        Minimum width	        CSS
sm	                        640px	                @media (min-width: 640px) { ... }
md	                        768px	                @media (min-width: 768px) { ... }
lg	                        1024px	                @media (min-width: 1024px) { ... }
xl	                        1280px	                @media (min-width: 1280px) { ... }
2xl	                        1536px	                @media (min-width: 1536px) { ... }
```

</details>

<details>
  <summary>7. Font Size Real Values</summary>

```html
<a class="text-[32px] lg:text-[8rem]" href="/">Food Ninja</a>
```

</details>

<details>
  <summary>8. Font Size Custom Values</summary>

```html
<a class="text-base lg:text-5base" href="/">Food Ninja</a>
```

tailwind.config.js:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./public/*.{html,js}"],
  theme: {
    fontSize: {
      'xs': '.75rem',
      'sm': '.875rem',
      'base': '1rem',
      '2base': '2rem',
      '3base': '3rem',
      '4base': '4rem',
      '5base': '5rem',
      'lg': '1.125rem',
      'xl': '1.25rem',
      '2xl': '1.5rem',
      '3xl': '1.875rem',
      '4xl': '2.25rem',
      '5xl': '3rem',
      '6xl': '3.75rem',
      '7xl': '4.5rem',
      '8xl': '6rem',
      '9xl': '8rem',
    },
    extend: {},
  },
  plugins: [],
}
```

Providing a default line-height:

The form => [fontSize, lineHeight]

```js
module.exports = {
  theme: {
    fontSize: {
      sm: ['14px', '20px'],
      base: ['16px', '24px'],
      lg: ['20px', '28px'],
      xl: ['24px', '32px'],
    }
  }
}
```

Also provide default letter-spacing and font-weight values:

The form => [fontSize, { lineHeight?, letterSpacing?, fontWeight? }]

```js
module.exports = {
  theme: {
    fontSize: {
      '2xl': ['1.5rem', {
        lineHeight: '2rem',
        letterSpacing: '-0.01em',
        fontWeight: '500',
      }],
      '3xl': ['1.875rem', {
        lineHeight: '2.25rem',
        letterSpacing: '-0.02em',
        fontWeight: '700',
      }],
    }
  }
}
```

</details>

<details>
  <summary>9. Text Color</summary>

```html
<p class="text-sky-400">The quick brown fox...</p>
```

```bash
text-sky-50
text-sky-100
text-sky-200
text-sky-300
text-sky-400
text-sky-500
text-sky-600
text-sky-700
text-sky-800
text-sky-900
```

Color Choices:

```bash
text-slate-50
text-gray-50
text-zinc-50
text-neutral-50
text-stone-50
text-red-50
text-orange-50
text-amber-50
text-yellow-50
text-lime-50
text-green-50
text-emerald-50
text-teal-50
text-cyan-50
text-sky-50
text-blue-50
text-indigo-50
text-violet-50
text-purple-50
text-fuchsia-50
text-pink-50
text-rose-50
```

Default Color settings:

```html
text-inherit
text-current
text-transparent
text-black
text-white
```

```html
node -v
```

</details>

<details>
  <summary>10. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>11. Text Color Opacity</summary>

```html
<p class="text-sky-400/100">The quick brown fox...</p>
<p class="text-sky-400/75">The quick brown fox...</p>
<p class="text-sky-400/50">The quick brown fox...</p>
<p class="text-sky-400/25">The quick brown fox...</p>
<p class="text-sky-400/0">The quick brown fox...</p>
```

```html
<p class="text-blue-600/[.06]">The quick brown fox...</p>
```

</details>

<details>
  <summary>12. Text Color change on Hover</summary>

```html
<p class="text-slate-400 hover:text-sky-400">The quick brown fox...</p>
```

</details>

<details>
  <summary>13. Text Color change on media queries</summary>

```html
<p class="text-slate-400 lg:text-sky-400">The quick brown fox...</p>
```

</details>

<details>
  <summary>14. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>15. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>16. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>17. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>18. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>19. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>

<details>
  <summary>20. sample</summary>

```html
node -v
```

```html
node -v
```

```html
node -v
```

</details>