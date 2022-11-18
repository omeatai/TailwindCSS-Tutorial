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
<!DOCTYPE html>
```

```bash
node -v
```

</details>

<details>
  <summary>3. sample</summary>

```bash
node -v
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