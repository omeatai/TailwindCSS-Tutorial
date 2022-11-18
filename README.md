# TailwindCSS-Tutorial
Learn TailwindCSS by Ifeanyi Omeata

## Tutorial

---

### [1-TAILWINDCSS CRASH COURSE - NET NINJA](#)

+INTRODUCTION

<details>
  <summary>1. Install TailwindCSS</summary>

Check Node Version:

```bash
node -v
```

Create package.json file:

```bash
npm init -y
```

Install TailwindCSS:

```bash
npm install tailwindcss
```

```bash
npm install -D tailwindcss
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
```

Configure your template paths:

```bash
npx tailwindcss init
```

tailwind.config.js:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
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
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
npx tailwindcss -i ./src/input.css -o ./public/styles.css --watch
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
    <body>

    <div>
        <div>
        <nav>
            <div>
            <h1>
                <a href="/">Food Ninja</a>
            </h1>
            </div>
            <ul>
            <li>
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
            <h2>Recipes</h2>
            <h3>For Ninjas</h3>
        </header>

        <div>
            <h4>Latest Recipes</h4>

            <div>
            <!-- cards go here -->
            <div>
                <img src="img/stew.jpg" alt="stew">
                <div>
                <span>5 Bean Chili Stew</span>
                <span>Recipe by Mario</span>
                </div>
            </div>
            </div>

            <h4>Most Popular</h4>

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
npm install live-server -g
```

Run Live Server:

```bash
live-server public
```

</details>

<details>
  <summary>4. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>5. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>6. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>7. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>8. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>9. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>10. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>11. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>12. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>13. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>14. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>15. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>16. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>17. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>18. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>19. sample</summary>

```bash
node -v
```

</details>

<details>
  <summary>20. sample</summary>

```bash
node -v
```

</details>