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

##### [A. TYPOGRAPHY](#)

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

On Hover:

```html
<a class="text-4xl hover:text-base" href="/">Food Ninja</a>

<p class="text-sm hover:text-base">
  <!-- ... -->
</p>
```

On Media queries:

```html
<a class="text-4xl lg:text-9xl" href="/">Food Ninja</a>

<p class="text-sm md:text-base">
  <!-- ... -->
</p>
```

```html

Breakpoint prefix	        Minimum width	        CSS
sm	                        640px	                @media (min-width: 640px) { ... }
md	                        768px	                @media (min-width: 768px) { ... }
lg	                        1024px	                @media (min-width: 1024px) { ... }
xl	                        1280px	                @media (min-width: 1280px) { ... }
2xl	                        1536px	                @media (min-width: 1536px) { ... }
```



Font Size Custom Values:

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

Exact Values:

```html
<a class="text-[32px] lg:text-[8rem]" href="/">Food Ninja</a>

<p class="text-[14px]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>5. Text Color</summary>

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

Text Color Opacity:

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

On Hover:

```html
<p class="text-slate-400 hover:text-sky-400">The quick brown fox...</p>
```

On Media queries:

```html
<p class="text-slate-400 lg:text-sky-400">The quick brown fox...</p>
```

Custom Values:

```html
<h2 class="text-exclusive text-6xl font-semibold">Recipes</h2>
```

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'exclusive': '#243c5a',
      },
    }
  }
}
```

Exact Values:

```html
<h2 class="text-[#50d71e] text-6xl font-semibold">Recipes</h2>

<p class="text-[#50d71e]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>6. Font Weight</summary>

```html
Class                           Properties

font-thin	                    font-weight: 100;
font-extralight	                    font-weight: 200;
font-light	                    font-weight: 300;
font-normal	                    font-weight: 400;
font-medium	                    font-weight: 500;
font-semibold	                    font-weight: 600;
font-bold	                    font-weight: 700;
font-extrabold	                    font-weight: 800;
font-black	                    font-weight: 900;
```

```html
<p class="font-light ...">The quick brown fox ...</p>
<p class="font-normal ...">The quick brown fox ...</p>
<p class="font-medium ...">The quick brown fox ...</p>
<p class="font-semibold ...">The quick brown fox ...</p>
<p class="font-bold ...">The quick brown fox ...</p>
```

Custom Values:

```html
<h2 class="text-[#30638E] text-6xl font-extreme">Recipes</h2>
```

tailwind.config.js:

```js
module.exports = {
  theme: {
    fontWeight: {
      hairline: 100,
      'extra-light': 100,
      thin: 200,
      light: 300,
      normal: 400,
      medium: 500,
      semibold: 600,
      bold: 700,
      extrabold: 800,
      'extra-bold': 800,
      black: 900,
      'extreme': 900,
    }
  }
}
```

Exact Values:

```html
<h2 class="text-[#30638E] text-6xl font-[900]">Recipes</h2>

<p class="font-[100]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>7. Text Transform</summary>

```html
Class                       Properties
uppercase	                text-transform: uppercase;
lowercase	                text-transform: lowercase;
capitalize	                text-transform: capitalize;
normal-case	                text-transform: none;
```

```html
<p class="normal-case ...">The quick brown fox ...</p>
<p class="uppercase ...">The quick brown fox ...</p>
<p class="lowercase ...">The quick brown fox ...</p>
<p class="capitalize ...">The quick brown fox ...</p>
```

On Hover:

```html
<h2 class="text-[#30638E] text-6xl font-[900] hover:uppercase">Recipes</h2>
```

On Media queries:

```html
<h2 class="text-[#30638E] text-6xl font-[900] lg:uppercase">Recipes</h2>
```

</details>

<details>
  <summary>8. Font-Family</summary>

```html
Class                       Properties

font-sans	                font-family: ui-sans-serif, system-ui, -apple-system,
                            BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
font-serif	                font-family: ui-serif, Georgia, Cambria, "Times New Roman",
                            Times, serif;
font-mono	                font-family: ui-monospace, SFMono-Regular, Menlo, Monaco,
                            Consolas, "Liberation Mono", "Courier New", monospace;
```

```html
<p class="font-sans ...">The quick brown fox ...</p>
<p class="font-serif ...">The quick brown fox ...</p>
<p class="font-mono ...">The quick brown fox ...</p>
```

On Hover:

```html
<p class="font-sans hover:font-serif">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="font-sans md:font-serif">
  <!-- ... -->
</p>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    fontFamily: {
      'sans': ['ui-sans-serif', 'system-ui', ...],
      'serif': ['ui-serif', 'Georgia', ...],
      'mono': ['ui-monospace', 'SFMono-Regular', ...],
      'display': ['Oswald', ...],
      'body': ['"Open Sans"', ...],
    }
  }
}
```

```js
{
  // Array format:
  'sans': ['Helvetica', 'Arial', 'sans-serif'],

  // Comma-delimited format:
  'sans': 'Helvetica, Arial, sans-serif',
}
```

Exact Values:

```html
<h2 class="text-[#30638E] text-6xl font-[900] lg:uppercase font-['Open_Sans']">Recipes</h2>

<p class="font-['Open_Sans']">
  <!-- ... -->
</p>
```

Base Values:

styles.css:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  html {
    font-family: Proxima Nova, system-ui, sans-serif;
  }
}
```

</details>

<details>
  <summary>9. Font Style </summary>

```html
Class               Properties

italic	            font-style: italic;
not-italic	        font-style: normal;
```

```html
<p class="italic ...">The quick brown fox ...</p>
<p class="not-italic ...">The quick brown fox ...</p>
```

On Hover:

```html
<h2 class="text-[#30638E] text-6xl font-[900] hover:italic">Recipes</h2>

<p class="italic hover:not-italic">
  <!-- ... -->
</p>
```

On Media queries:

```html
<h2 class="text-[#30638E] text-6xl font-[900] lg:italic">Recipes</h2>

<p class="italic md:not-italic">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>10. Letter Spacing</summary>

```html
Class                   Properties

tracking-tighter	    letter-spacing: -0.05em;
tracking-tight	        letter-spacing: -0.025em;
tracking-normal	        letter-spacing: 0em;
tracking-wide	        letter-spacing: 0.025em;
tracking-wider	        letter-spacing: 0.05em;
tracking-widest	        letter-spacing: 0.1em;
```

```html
<p class="tracking-tight ...">The quick brown fox ...</p>
<p class="tracking-normal ...">The quick brown fox ...</p>
<p class="tracking-wide ...">The quick brown fox ...</p>
```

Using negative values:

```html
<p class="-tracking-2">The quick brown fox ...</p>
```

tailwind.config.js:

```js
module.exports = {
  theme: {
    letterSpacing: {
      '1': '0em',
      '2': '0.025em',
      '3': '0.05em',
      '4': '0.1em',
    }
  }
}
```

On Hover:

```html
<p class="tracking-tight hover:tracking-wide">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="tracking-tight md:tracking-wide">
  <!-- ... -->
</p>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    letterSpacing: {
      tightest: '-.075em',
      tighter: '-.05em',
      tight: '-.025em',
      normal: '0',
      wide: '.025em',
      wider: '.05em',
      widest: '.1em',
      widest: '.25em',
    }
  }
}
```

Exact Values:

```html
<h2 class="text-[#30638E] text-6xl font-[900] tracking-[.25em]">Recipes</h2>
```

</details>

<details>
  <summary>11. Line Height</summary>

```html
Class               Properties
leading-3	        line-height: .75rem; /* 12px */
leading-4	        line-height: 1rem; /* 16px */
leading-5	        line-height: 1.25rem; /* 20px */
leading-6	        line-height: 1.5rem; /* 24px */
leading-7	        line-height: 1.75rem; /* 28px */
leading-8	        line-height: 2rem; /* 32px */
leading-9	        line-height: 2.25rem; /* 36px */
leading-10	        line-height: 2.5rem; /* 40px */
leading-none	    line-height: 1;
leading-tight	    line-height: 1.25;
leading-snug	    line-height: 1.375;
leading-normal	    line-height: 1.5;
leading-relaxed	    line-height: 1.625;
leading-loose	    line-height: 2;
```

```html
<p class="leading-normal ...">So I started to walk into the water...</p>
<p class="leading-relaxed ...">So I started to walk into the water...</p>
<p class="leading-loose ...">So I started to walk into the water...</p>
```

```html
<p class="leading-6 ...">So I started to walk into the water...</p>
<p class="leading-7 ...">So I started to walk into the water...</p>
<p class="leading-8 ...">So I started to walk into the water...</p>
```

On Hover:

```html
<h3 class="text-2xl font-semibold leading-none hover:leading-loose">For Ninjas</h3>
```

On Media queries:

```html
<h3 class="text-2xl font-semibold leading-none lg:leading-loose">For Ninjas</h3>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      lineHeight: {
        'extra-loose': '2.5',
        '12': '3rem',
      }
    }
  }
}
```

Exact Values:

```html
<h3 class="text-2xl font-semibold leading-[3rem]">For Ninjas</h3>
```

</details>

<details>
  <summary>12. List Style Type</summary>

```html
Class           Properties
list-none	    list-style-type: none;
list-disc	    list-style-type: disc;
list-decimal	    list-style-type: decimal;
```

```html
<ul class="list-disc list-inside">
  <li>Now this is a story all about how, my life got flipped-turned upside down</li>
  <!-- ... -->
</ul>

<ol class="list-decimal list-inside">
  <li>Now this is a story all about how, my life got flipped-turned upside down</li>
  <!-- ... -->
</ol>

<ul class="list-none list-inside">
  <li>Now this is a story all about how, my life got flipped-turned upside down</li>
  <!-- ... -->
</ul>
```

On Hover:

```html
<ol class="list-none hover:list-decimal list-inside">
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
</ol>
```

On Media queries:

```html
<ol class="list-none lg:list-decimal list-inside">
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
</ol>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    listStyleType: {
      none: 'none',
      disc: 'disc',
      decimal: 'decimal',
      square: 'square',
      roman: 'upper-roman',
    }
  }
}
```

Exact Values:

```html
 <ol class="list-[upper-roman] list-inside">
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
</ol>
```

List Style Position:

```html
Class               Properties
list-inside	        list-style-position: inside;
list-outside	        list-style-position: outside;
```

```html
<ul class="list-inside ...">
  <li>5 cups chopped Porcini mushrooms</li>
  <!-- ... -->
</ul>

<ul class="list-outside ...">
  <li>5 cups chopped Porcini mushrooms</li>
  <!-- ... -->
</ul>
```

</details>

<details>
  <summary>13. Text Align</summary>

```html
Class           Properties
text-left	    text-align: left;
text-center	    text-align: center;
text-right	    text-align: right;
text-justify	    text-align: justify;
text-start	    text-align: start;
text-end	    text-align: end;
```

```html
<p class="text-left ...">So I started to walk into the water...</p>
<p class="text-center ...">So I started to walk into the water...</p>
<p class="text-right ...">So I started to walk into the water...</p>
<p class="text-justify ...">So I started to walk into the water...</p>
```

On Hover:

```html
<p class="text-left hover:text-center">So I started to walk into the water...</p>
```

On Media queries:

```html
<p class="text-left lg:text-center">So I started to walk into the water...</p>
```

</details>

<details>
  <summary>14. Text Decoration</summary>

```html
Class           Properties

underline	    text-decoration-line: underline;
overline	    text-decoration-line: overline;
line-through	    text-decoration-line: line-through;
no-underline	    text-decoration-line: none;
```

```html
<p class="underline ...">The quick brown fox ...</p>
<p class="overline ...">The quick brown fox ...</p>
<p class="line-through ...">The quick brown fox ...</p>
<p class="no-underline ...">The quick brown fox ...</p>
```

On Hover:

```html
<a href="#" class="no-underline hover:underline">This is a sentence.</a>
```

On Media queries:

```html
<a href="#" class="no-underline lg:underline">This is a sentence.</a>
```

</details>

<details>
  <summary>15. Text Decoration Color</summary>

```html
Class                       Properties
decoration-inherit	        text-decoration-color: inherit;
decoration-current	        text-decoration-color: currentColor;
decoration-transparent	        text-decoration-color: transparent;
decoration-black	        text-decoration-color: #000;
decoration-white	        text-decoration-color: #fff;
decoration-slate-50	        text-decoration-color: #f8fafc;
decoration-slate-100	        text-decoration-color: #f1f5f9;
decoration-slate-200	        text-decoration-color: #e2e8f0;
decoration-slate-300	        text-decoration-color: #cbd5e1;
decoration-slate-400	        text-decoration-color: #94a3b8;
decoration-slate-500	        text-decoration-color: #64748b;
decoration-slate-600	        text-decoration-color: #475569;
decoration-slate-700	        text-decoration-color: #334155;
decoration-slate-800	        text-decoration-color: #1e293b;
decoration-slate-900	        text-decoration-color: #0f172a;
```

```html
<div>
  <p>
    I’m Derek, an astro-engineer based in Tattooine. I like to build X-Wings at
    <a class="underline decoration-sky-500">My Company, Inc</a>.
    Outside of work, I like to <a class="underline decoration-pink-500">watch
    pod-racing</a> and have <a class="underline decoration-indigo-500">light-saber</a> fights.
  </p>
</div>
```

Changing the opacity:

```html
<div>
  <p>
    I’m Derek, an astro-engineer based in Tattooine. I like to build X-Wings at
    <a class="underline decoration-sky-500/30">My Company, Inc</a>.
    Outside of work, I like to <a class="underline decoration-pink-500/30">watch
    pod-racing</a> and have <a class="underline decoration-indigo-500/30">light-saber</a> fights.
  </p>
</div>
```

```html
<strong class="underline decoration-sky-500/[.33]"></strong>
```

On Hover:

```html
<p class="underline decoration-sky-600 hover:decoration-blue-400">
  <!-- ... -->
</p>
```

```html
<a href="#" class="no-underline hover:underline hover:decoration-pink-700">This is a sentence.</a>
```

On Media queries:

```html
<p class="underline decoration-sky-600 md:decoration-blue-400">
  <!-- ... -->
</p>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'regal-blue': '#243c5a',
      },
    }
  }
}
```

Exact values:

```html
<p class="decoration-[#50d71e]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>16. Text Decoration Style</summary>

```html
Class                   Properties

decoration-solid	    text-decoration-style: solid;
decoration-double	    text-decoration-style: double;
decoration-dotted	    text-decoration-style: dotted;
decoration-dashed	    text-decoration-style: dashed;
decoration-wavy	        text-decoration-style: wavy;
```

```html
<p class="underline decoration-solid ...">The quick brown fox...</p>
<p class="underline decoration-double ...">The quick brown fox...</p>
<p class="underline decoration-dotted ...">The quick brown fox...</p>
<p class="underline decoration-dashed ...">The quick brown fox...</p>
<p class="underline decoration-wavy ...">The quick brown fox...</p>
```

On Hover:

```html
<p class="underline hover:decoration-dashed">
  <!-- ... -->
</p>
```

On Media Queries:

```html
<p class="underline md:decoration-dashed">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>17. Text Decoration Thickness</summary>

```html
Class                   Properties

decoration-auto	        text-decoration-thickness: auto;
decoration-from-font	text-decoration-thickness: from-font;
decoration-0	        text-decoration-thickness: 0px;
decoration-1	        text-decoration-thickness: 1px;
decoration-2	        text-decoration-thickness: 2px;
decoration-4	        text-decoration-thickness: 4px;
decoration-8	        text-decoration-thickness: 8px;
```

```html
<p class="underline decoration-1 ...">The quick brown fox...</p>
<p class="underline decoration-2 ...">The quick brown fox...</p>
<p class="underline decoration-4 ...">The quick brown fox...</p>
```

On Hover:

```html
<p class="underline hover:decoration-4">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="underline md:decoration-4">
  <!-- ... -->
</p>
```

Custom Values:

tailwind.config.js:

```js

module.exports = {
  theme: {
    extend: {
      textDecorationThickness: {
        3: '3px',
      }
    }
  }
}
```

Exact values:

```html
<p class="decoration-[3px]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>18. Text Underline Offset</summary>

```html
Class                       Properties
underline-offset-auto	    text-underline-offset: auto;
underline-offset-0	    text-underline-offset: 0px;
underline-offset-1	    text-underline-offset: 1px;
underline-offset-2	    text-underline-offset: 2px;
underline-offset-4	    text-underline-offset: 4px;
underline-offset-8	    text-underline-offset: 8px;
```

```html
<p class="underline underline-offset-1 ...">The quick brown fox...</p>
<p class="underline underline-offset-2 ...">The quick brown fox...</p>
<p class="underline underline-offset-4 ...">The quick brown fox...</p>
<p class="underline underline-offset-8 ...">The quick brown fox...</p>
```

On Hover:

```html
<p class="underline hover:underline-offset-4">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="underline md:underline-offset-4">
  <!-- ... -->
</p>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      textUnderlineOffset: {
        3: '3px',
      }
    }
  }
}
```

Exact Values:

```html
<p class="underline-offset-[3px]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>52. Text Overflow</summary>

```html
Class               Properties

truncate	    overflow: hidden;
                    text-overflow: ellipsis;
                    white-space: nowrap;
text-ellipsis	    text-overflow: ellipsis;
text-clip	    text-overflow: clip;
```

```html
<p class="truncate ...">...</p>
<p class="text-ellipsis overflow-hidden ...">...</p>
<p class="text-clip overflow-hidden ...">...</p>
```

On Hover:

```html
<p class="truncate hover:text-clip">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="truncate md:text-clip">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>53. Text Indent</summary>

```html
Class       Properties
indent-0	text-indent: 0px;
indent-px	text-indent: 1px;
indent-0.5	text-indent: 0.125rem; /* 2px */
indent-1	text-indent: 0.25rem; /* 4px */
indent-1.5	text-indent: 0.375rem; /* 6px */
indent-2	text-indent: 0.5rem; /* 8px */
indent-2.5	text-indent: 0.625rem; /* 10px */
indent-3	text-indent: 0.75rem; /* 12px */
indent-3.5	text-indent: 0.875rem; /* 14px */
indent-4	text-indent: 1rem; /* 16px */
indent-5	text-indent: 1.25rem; /* 20px */
indent-6	text-indent: 1.5rem; /* 24px */
indent-7	text-indent: 1.75rem; /* 28px */
indent-8	text-indent: 2rem; /* 32px */
indent-9	text-indent: 2.25rem; /* 36px */
indent-10	text-indent: 2.5rem; /* 40px */
indent-11	text-indent: 2.75rem; /* 44px */
indent-12	text-indent: 3rem; /* 48px */
indent-14	text-indent: 3.5rem; /* 56px */
indent-16	text-indent: 4rem; /* 64px */
indent-20	text-indent: 5rem; /* 80px */
indent-24	text-indent: 6rem; /* 96px */
indent-28	text-indent: 7rem; /* 112px */
indent-32	text-indent: 8rem; /* 128px */
indent-36	text-indent: 9rem; /* 144px */
indent-40	text-indent: 10rem; /* 160px */
indent-44	text-indent: 11rem; /* 176px */
indent-48	text-indent: 12rem; /* 192px */
indent-52	text-indent: 13rem; /* 208px */
indent-56	text-indent: 14rem; /* 224px */
indent-60	text-indent: 15rem; /* 240px */
indent-64	text-indent: 16rem; /* 256px */
indent-72	text-indent: 18rem; /* 288px */
indent-80	text-indent: 20rem; /* 320px */
indent-96	text-indent: 24rem; /* 384px */
```

```html
<p class="indent-8">
  So I started to walk into the water. I won't lie to you boys, I was
  terrified. But I pressed on, and as I made my way past the breakers
  a strange calm came over me. I don't know if it was divine intervention
  or the kinship of all living things but I tell you Jerry at that moment,
  I <em>was</em> a marine biologist.
</p>
```

```html
<div class="-indent-8">
  So I started to walk into the water. I won't lie to...
</div>
```

On Hover:

```html
<div class="indent-4 hover:indent-8">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="indent-4 md:indent-8">
  <!-- ... -->
</div>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      spacing: {
        '128': '32rem',
      }
    }
  }
}
```

```js
module.exports = {
  theme: {
    extend: {
      textIndent: {
        '128': '32rem',
      }
    }
  }
}
```

Exact Values:

```html
<div class="indent-[50%]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>54. Vertical Align</summary>

```html
Class                   Properties
align-baseline	        vertical-align: baseline;
align-top	        vertical-align: top;
align-middle	        vertical-align: middle;
align-bottom	        vertical-align: bottom;
align-text-top	        vertical-align: text-top;
align-text-bottom	vertical-align: text-bottom;
align-sub	        vertical-align: sub;
align-super	        vertical-align: super;
```

```html
<span class="inline-block align-baseline ...">...</span>
<span class="inline-block align-top ...">...</span>
<span class="inline-block align-middle ...">...</span>
<span class="inline-block align-bottom ...">...</span>
<span class="inline-block align-text-top ...">...</span>
<span class="inline-block align-text-bottom ...">...</span>
```

On Hover:

```html
<p class="align-middle hover:align-top">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="align-middle md:align-top">
  <!-- ... -->
</p>
```

Exact Values:

```html
<div class="align-[4px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>55. Whitespace</summary>

```html
Class                           Properties
whitespace-normal	        white-space: normal;
whitespace-nowrap	        white-space: nowrap;
whitespace-pre	                white-space: pre;
whitespace-pre-line	        white-space: pre-line;
whitespace-pre-wrap	        white-space: pre-wrap;
```

Normal -
Use whitespace-normal to cause text to wrap normally within an element. Newlines and spaces will be collapsed.

```html
<div class="w-3/4 ...">
  <div class="whitespace-normal ...">Hey everyone!

It's almost 2022       and we still don't know if there is aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</div>
</div>
```

No Wrap -
Use whitespace-nowrap to prevent text from wrapping within an element. Newlines and spaces will be collapsed.

```html
<div class="w-3/4 overflow-x-auto ...">
  <div class="whitespace-nowrap ...">Hey everyone!

It's almost 2022       and we still don't know if there is aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</div>
</div>
```

Pre -
Use whitespace-pre to preserve newlines and spaces within an element. Text will not be wrapped.

```html
<div class="w-3/4 overflow-x-auto ...">
  <div class="whitespace-pre ...">Hey everyone!

It's almost 2022       and we still don't know if there is aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</div>
</div>
```

Pre Line -
Use whitespace-pre-line to preserve newlines but not spaces within an element. Text will be wrapped normally.

```html
<div class="w-3/4 ...">
  <div class="whitespace-pre-line ...">Hey everyone!

It's almost 2022       and we still don't know if there is aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</div>
</div>
```

Pre Wrap -
Use whitespace-pre-wrap to preserve newlines and spaces within an element. Text will be wrapped normally.

```html
<div class="w-3/4 ...">
  <div class="whitespace-pre-wrap ...">Hey everyone!

It's almost 2022       and we still don't know if there is aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</div>
</div>
```

On Hover:

```html
<div class="whitespace-normal hover:whitespace-pre">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="whitespace-normal md:whitespace-pre">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>56. Word Break</summary>

```html
Class                   Properties
break-normal	        overflow-wrap: normal;
word-break:             normal;
break-words	        overflow-wrap: break-word;
break-all	        word-break: break-all;
break-keep	        word-break: keep-all;
```

```html
<p class="break-normal ...">...</p>
<p class="break-words ...">...</p>
<p class="break-all ...">...</p>
```

On Hover:

```html
<p class="break-normal hover:break-all">
  <!-- ... -->
</p>
```

On Media queries:

```html
<p class="break-normal md:break-all">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>57. Content</summary>

```html
Class               Properties
content-none	    content: none;
```

Setting a pseudo-element's content:

```html
Higher resolution means more than just a better-quality image. With a Retina
6K display, <a class="text-sky-400 after:content-['_↗'] ..." href="https://www.
apple.com/pro-display-xdr/" target="_blank">Pro Display XDR</a> gives you
nearly 40 percent more screen real estate than a 5K display.
```

Referencing an attribute value:

```html
<div before="Hello World" class="before:content-[attr(before)]">
  <!-- ... -->
</div>
```

Using spaces and underscores:

```html
<div class="before:content-['Hello_World']">
  <!-- ... -->
</div>
```

```html
<div class="before:content-['Hello\_World']">
  <!-- ... -->
</div>
```

On Hover:

```html
<div class="before:content-['Not_Hovering'] hover:before:content-['Hovering']">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="before:content-['Mobile'] md:before:content-['Desktop']">
  <!-- ... -->
</div>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      content: {
        'link': 'url("/icons/link.svg")',
      },
    }
  }
}
```

Exact Values:

```html
<div class="before:content-['Hello_World']">
  <!-- ... -->
</div>
```

</details>

##### [B. SPACING](#)

<details>
  <summary>58. Padding</summary>

```html
Class                       Properties
<!-- p-0 -->
p-0	                    padding: 0px;
px-0	                    padding-left: 0px;
                            padding-right: 0px;
py-0	                    padding-top: 0px;
                            padding-bottom: 0px;
pt-0	                    padding-top: 0px;
pr-0	                    padding-right: 0px;
pb-0	                    padding-bottom: 0px;
pl-0	                    padding-left: 0px;
p-px	                    padding: 1px;
px-px	                    padding-left: 1px;
                            padding-right: 1px;
py-px	                    padding-top: 1px;
                            padding-bottom: 1px;
pt-px	                    padding-top: 1px;
pr-px	                    padding-right: 1px;
pb-px	                    padding-bottom: 1px;
pl-px	                    padding-left: 1px;
<!-- p-0.5 -->
p-0.5	                    padding: 0.125rem; /* 2px */
px-0.5	                    padding-left: 0.125rem; /* 2px */
                            padding-right: 0.125rem; /* 2px */
py-0.5	                    padding-top: 0.125rem; /* 2px */
                            padding-bottom: 0.125rem; /* 2px */
pt-0.5	                    padding-top: 0.125rem; /* 2px */
pr-0.5	                    padding-right: 0.125rem; /* 2px */
pb-0.5	                    padding-bottom: 0.125rem; /* 2px */
pl-0.5	                    padding-left: 0.125rem; /* 2px */
<!-- p-1 -->
p-1	                    padding: 0.25rem; /* 4px */
px-1	                    padding-left: 0.25rem; /* 4px */
                            padding-right: 0.25rem; /* 4px */
py-1	                    padding-top: 0.25rem; /* 4px */
                            padding-bottom: 0.25rem; /* 4px */
pt-1	                    padding-top: 0.25rem; /* 4px */
pr-1	                    padding-right: 0.25rem; /* 4px */
pb-1	                    padding-bottom: 0.25rem; /* 4px */
pl-1	                    padding-left: 0.25rem; /* 4px */
<!-- others -->
p-1.5	                    padding: 0.375rem; /* 6px */
p-2	                    padding: 0.5rem; /* 8px */
p-3	                    padding: 0.75rem; /* 12px */
p-4	                    padding: 1rem; /* 16px */
p-5	                    padding: 1.25rem; /* 20px */
p-6	                    padding: 1.5rem; /* 24px */
p-7	                    padding: 1.75rem; /* 28px */
p-8	                    padding: 2rem; /* 32px */
p-9	                    padding: 2.25rem; /* 36px */
p-10	                    padding: 2.5rem; /* 40px */
p-11	                    padding: 2.75rem; /* 44px */
p-12	                    padding: 3rem; /* 48px */
p-14	                    padding: 3.5rem; /* 56px */
p-16	                    padding: 4rem; /* 64px */
p-20	                    padding: 5rem; /* 80px */
p-24	                    padding: 6rem; /* 96px */
p-28	                    padding: 7rem; /* 112px */
p-32	                    padding: 8rem; /* 128px */
p-36	                    padding: 9rem; /* 144px */
p-40	                    padding: 10rem; /* 160px */
p-44                        padding: 11rem; /* 176px */
p-48	                    padding: 12rem; /* 192px */
p-52	                    padding: 13rem; /* 208px */
p-56	                    padding: 14rem; /* 224px */
p-60	                    padding: 15rem; /* 240px */
p-64	                    padding: 16rem; /* 256px */
p-72	                    padding: 18rem; /* 288px */
p-80	                    padding: 20rem; /* 320px */
p-96	                    padding: 24rem; /* 384px */
```

```html
<div class="pt-6 ...">pt-6</div>
<div class="pr-4 ...">pr-4</div>
<div class="pb-8 ...">pb-8</div>
<div class="pl-2 ...">pl-2</div>

<div class="px-8 ...">px-8</div>
<div class="py-8 ...">py-8</div>
<div class="p-8 ...">p-8</div>
```

On Hover:

```html
<div class="py-4 hover:py-8">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="py-4 md:py-8">
  <!-- ... -->
</div>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      spacing: {
        '5px': '5px',
      }
    }
  }
}
```

```js
module.exports = {
  theme: {
    extend: {
      padding: {
        '5px': '5px',
      }
    }
  }
}
```

Exact Values:

```html
<div class="p-[5px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>59. Margin</summary>

```html
Class                   Properties
<!-- p-0 -->
m-0	                margin: 0px;
mx-0	                margin-left: 0px;
                        margin-right: 0px;
my-0	                margin-top: 0px;
                        margin-bottom: 0px;
mt-0	                margin-top: 0px;
mr-0	                margin-right: 0px;
mb-0	                margin-bottom: 0px;
ml-0	                margin-left: 0px;
<!-- p-px -->
m-px	                margin: 1px;
mx-px	                margin-left: 1px;
                        margin-right: 1px;
my-px	                margin-top: 1px;
                        margin-bottom: 1px;
mt-px	                margin-top: 1px;
mr-px	                margin-right: 1px;
mb-px	                margin-bottom: 1px;
ml-px	                margin-left: 1px;
<!-- p-0.5 -->
m-0.5	                margin: 0.125rem; /* 2px */
mx-0.5	                margin-left: 0.125rem; /* 2px */
                        margin-right: 0.125rem; /* 2px */
my-0.5	                margin-top: 0.125rem; /* 2px */
                        margin-bottom: 0.125rem; /* 2px */
mt-0.5	                margin-top: 0.125rem; /* 2px */
mr-0.5	                margin-right: 0.125rem; /* 2px */
mb-0.5	                margin-bottom: 0.125rem; /* 2px */
ml-0.5	                margin-left: 0.125rem; /* 2px */
<!-- p-1 -->
m-1	                margin: 0.25rem; /* 4px */
mx-1	                margin-left: 0.25rem; /* 4px */
                        margin-right: 0.25rem; /* 4px */
my-1	                margin-top: 0.25rem; /* 4px */
                        margin-bottom: 0.25rem; /* 4px */
mt-1	                margin-top: 0.25rem; /* 4px */
mr-1	                margin-right: 0.25rem; /* 4px */
mb-1	                margin-bottom: 0.25rem; /* 4px */
ml-1	                margin-left: 0.25rem; /* 4px */
<!-- others -->
m-1.5	                margin: 0.375rem; /* 6px */
m-2	                margin: 0.5rem; /* 8px */
m-2.5	                margin: 0.625rem; /* 10px */
m-3	                margin: 0.75rem; /* 12px */
m-3.5	                margin: 0.875rem; /* 14px */
m-4	                margin: 1rem; /* 16px */
m-5	                margin: 1.25rem; /* 20px */
m-6	                margin: 1.5rem; /* 24px */
m-7	                margin: 1.75rem; /* 28px */
m-8	                margin: 2rem; /* 32px */
m-9	                margin: 2.25rem; /* 36px */
m-10	                margin: 2.5rem; /* 40px */
m-11	                margin: 2.75rem; /* 44px */
m-12	                margin: 3rem; /* 48px */
m-14	                margin: 3.5rem; /* 56px */
m-16	                margin: 4rem; /* 64px */
m-20	                margin: 5rem; /* 80px */
m-24	                margin: 6rem; /* 96px */
m-28	                margin: 7rem; /* 112px */
m-32	                margin: 8rem; /* 128px */
m-36	                margin: 9rem; /* 144px */
m-40	                margin: 10rem; /* 160px */
m-44	                margin: 11rem; /* 176px */
m-48	                margin: 12rem; /* 192px */
m-52	                margin: 13rem; /* 208px */
m-56	                margin: 14rem; /* 224px */
m-60	                margin: 15rem; /* 240px */
m-64	                margin: 16rem; /* 256px */
m-72	                margin: 18rem; /* 288px */
m-80	                margin: 20rem; /* 320px */
m-96	                margin: 24rem; /* 384px */
<!-- auto -->
m-auto	                margin: auto;
mx-auto	                margin-left: auto;
                        margin-right: auto;
my-auto	                margin-top: auto;
                        margin-bottom: auto;
mt-auto	                margin-top: auto;
mr-auto	                margin-right: auto;
mb-auto	                margin-bottom: auto;
ml-auto	                margin-left: auto;
```

```html
<div class="mt-6 ...">mt-6</div>
<div class="mr-4 ...">mr-4</div>
<div class="mb-8 ...">mb-8</div>
<div class="ml-2 ...">ml-2</div>

<div class="mx-8 ...">mx-8</div>
<div class="my-8 ...">my-8</div>
<div class="m-8 ...">m-8</div>

<div class="w-36 h-16 bg-sky-400 opacity-20 ..."></div>
<div class="-mt-8 bg-sky-300 ...">-mt-8</div>
```

On Hover:

```html
<div class="mt-4 hover:mt-8">
  <!-- ... -->
</div>
```

On Media Queries:

```html
<div class="mt-4 md:mt-8">
  <!-- ... -->
</div>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      spacing: {
        '5px': '5px',
      }
    }
  }
}
```

```js
module.exports = {
  theme: {
    extend: {
      margin: {
        '5px': '5px',
      }
    }
  }
}
```

Exact Values:

```html
<div class="m-[5px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>60. Space Between</summary>

```html
Class                       Properties

space-x-0 > * + *	    margin-left: 0px;
space-y-0 > * + *	    margin-top: 0px;
space-x-0.5 > * + *	    margin-left: 0.125rem; /* 2px */
space-y-0.5 > * + *	    margin-top: 0.125rem; /* 2px */
space-x-1 > * + *	    margin-left: 0.25rem; /* 4px */
space-y-1 > * + *	    margin-top: 0.25rem; /* 4px */
space-x-1.5 > * + *	    margin-left: 0.375rem; /* 6px */
space-y-1.5 > * + *	    margin-top: 0.375rem; /* 6px */
space-x-2 > * + *	    margin-left: 0.5rem; /* 8px */
space-y-2 > * + *	    margin-top: 0.5rem; /* 8px */
space-x-2.5 > * + *	    margin-left: 0.625rem; /* 10px */
space-y-2.5 > * + *	    margin-top: 0.625rem; /* 10px */
space-x-3 > * + *	    margin-left: 0.75rem; /* 12px */
space-y-3 > * + *	    margin-top: 0.75rem; /* 12px */
space-x-3.5 > * + *	    margin-left: 0.875rem; /* 14px */
space-y-3.5 > * + *	    margin-top: 0.875rem; /* 14px */
space-x-4 > * + *	    margin-left: 1rem; /* 16px */
space-y-4 > * + *	    margin-top: 1rem; /* 16px */
space-x-5 > * + *	    margin-left: 1.25rem; /* 20px */
space-y-5 > * + *	    margin-top: 1.25rem; /* 20px */
space-x-6 > * + *	    margin-left: 1.5rem; /* 24px */
space-y-6 > * + *	    margin-top: 1.5rem; /* 24px */
space-x-7 > * + *	    margin-left: 1.75rem; /* 28px */
space-y-7 > * + *	    margin-top: 1.75rem; /* 28px */
space-x-8 > * + *	    margin-left: 2rem; /* 32px */
space-y-8 > * + *	    margin-top: 2rem; /* 32px */
space-x-9 > * + *	    margin-left: 2.25rem; /* 36px */
space-y-9 > * + *	    margin-top: 2.25rem; /* 36px */
space-x-10 > * + *	    margin-left: 2.5rem; /* 40px */
space-y-10 > * + *	    margin-top: 2.5rem; /* 40px */
space-x-11 > * + *	    margin-left: 2.75rem; /* 44px */
space-y-11 > * + *	    margin-top: 2.75rem; /* 44px */
space-x-12 > * + *	    margin-left: 3rem; /* 48px */
space-y-12 > * + *	    margin-top: 3rem; /* 48px */
space-x-14 > * + *	    margin-left: 3.5rem; /* 56px */
space-y-14 > * + *	    margin-top: 3.5rem; /* 56px */
space-x-16 > * + *	    margin-left: 4rem; /* 64px */
space-y-16 > * + *	    margin-top: 4rem; /* 64px */
space-x-20 > * + *	    margin-left: 5rem; /* 80px */
space-y-20 > * + *	    margin-top: 5rem; /* 80px */
space-x-24 > * + *	    margin-left: 6rem; /* 96px */
space-y-24 > * + *	    margin-top: 6rem; /* 96px */
space-x-28 > * + *	    margin-left: 7rem; /* 112px */
space-y-28 > * + *	    margin-top: 7rem; /* 112px */
space-x-32 > * + *	    margin-left: 8rem; /* 128px */
space-y-32 > * + *	    margin-top: 8rem; /* 128px */
space-x-36 > * + *	    margin-left: 9rem; /* 144px */
space-y-36 > * + *	    margin-top: 9rem; /* 144px */
space-x-40 > * + *	    margin-left: 10rem; /* 160px */
space-y-40 > * + *	    margin-top: 10rem; /* 160px */
space-x-44 > * + *	    margin-left: 11rem; /* 176px */
space-y-44 > * + *	    margin-top: 11rem; /* 176px */
space-x-48 > * + *	    margin-left: 12rem; /* 192px */
space-y-48 > * + *	    margin-top: 12rem; /* 192px */
space-x-52 > * + *	    margin-left: 13rem; /* 208px */
space-y-52 > * + *	    margin-top: 13rem; /* 208px */
space-x-56 > * + *	    margin-left: 14rem; /* 224px */
space-y-56 > * + *	    margin-top: 14rem; /* 224px */
space-x-60 > * + *	    margin-left: 15rem; /* 240px */
space-y-60 > * + *	    margin-top: 15rem; /* 240px */
space-x-64 > * + *	    margin-left: 16rem; /* 256px */
space-y-64 > * + *	    margin-top: 16rem; /* 256px */
space-x-72 > * + *	    margin-left: 18rem; /* 288px */
space-y-72 > * + *	    margin-top: 18rem; /* 288px */
space-x-80 > * + *	    margin-left: 20rem; /* 320px */
space-y-80 > * + *	    margin-top: 20rem; /* 320px */
space-x-96 > * + *	    margin-left: 24rem; /* 384px */
space-y-96 > * + *	    margin-top: 24rem; /* 384px */
space-x-px > * + *	    margin-left: 1px;
space-y-px > * + *	    margin-top: 1px;
space-y-reverse > * + *	    --tw-space-y-reverse: 1;
space-x-reverse > * + *	    --tw-space-x-reverse: 1;
```

```html
<div class="flex space-x-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

```html
<div class="flex flex-col space-y-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

```html
<div class="flex flex-row-reverse space-x-4 space-x-reverse ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

```html
<div class="flex -space-x-4 ...">
  <!-- ... -->
</div>
```

On Hover:

```html
<div class="flex space-x-2 hover:space-x-8">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="flex space-x-2 md:space-x-8">
  <!-- ... -->
</div>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      spacing: {
        '5px': '5px',
      }
    }
  }
}
```

```js
module.exports = {
  theme: {
    extend: {
      space: {
        '5px': '5px',
      }
    }
  }
}
```

Exact Values:

```html
<div class="space-y-[5px]">
  <!-- ... -->
</div>
```

</details>

##### [C. BORDERS](#)

<details>
  <summary>61. Border Radius</summary>

```html
Class                       Properties

rounded-none	            border-radius: 0px;
rounded-sm	            border-radius: 0.125rem; /* 2px */
rounded	                    border-radius: 0.25rem; /* 4px */
rounded-md	            border-radius: 0.375rem; /* 6px */
rounded-lg	            border-radius: 0.5rem; /* 8px */
rounded-xl	            border-radius: 0.75rem; /* 12px */
rounded-2xl	            border-radius: 1rem; /* 16px */
rounded-3xl	            border-radius: 1.5rem; /* 24px */
rounded-full	            border-radius: 9999px;

rounded-t-none	        border-top-left-radius: 0px;
                        border-top-right-radius: 0px;
rounded-t-sm	        border-top-left-radius: 0.125rem; /* 2px */
                        border-top-right-radius: 0.125rem; /* 2px */
rounded-t	            border-top-left-radius: 0.25rem; /* 4px */
                        border-top-right-radius: 0.25rem; /* 4px */
rounded-t-md	        border-top-left-radius: 0.375rem; /* 6px */
                        border-top-right-radius: 0.375rem; /* 6px */
rounded-t-lg	        border-top-left-radius: 0.5rem; /* 8px */
                        border-top-right-radius: 0.5rem; /* 8px */
rounded-t-xl	        border-top-left-radius: 0.75rem; /* 12px */
                        border-top-right-radius: 0.75rem; /* 12px */
rounded-t-2xl	        border-top-left-radius: 1rem; /* 16px */
                        border-top-right-radius: 1rem; /* 16px */
rounded-t-3xl	        border-top-left-radius: 1.5rem; /* 24px */
                        border-top-right-radius: 1.5rem; /* 24px */
rounded-t-full	        border-top-left-radius: 9999px;
                        border-top-right-radius: 9999px;

rounded-r-none	        border-top-right-radius: 0px;
                        border-bottom-right-radius: 0px;
rounded-r-sm	        border-top-right-radius: 0.125rem; /* 2px */
                        border-bottom-right-radius: 0.125rem; /* 2px */
rounded-r	            border-top-right-radius: 0.25rem; /* 4px */
                        border-bottom-right-radius: 0.25rem; /* 4px */
rounded-r-md	        border-top-right-radius: 0.375rem; /* 6px */
                        border-bottom-right-radius: 0.375rem; /* 6px */
rounded-r-lg	        border-top-right-radius: 0.5rem; /* 8px */
                        border-bottom-right-radius: 0.5rem; /* 8px */
rounded-r-xl	        border-top-right-radius: 0.75rem; /* 12px */
                        border-bottom-right-radius: 0.75rem; /* 12px */
rounded-r-2xl	        border-top-right-radius: 1rem; /* 16px */
                        border-bottom-right-radius: 1rem; /* 16px */
rounded-r-3xl	        border-top-right-radius: 1.5rem; /* 24px */
                        border-bottom-right-radius: 1.5rem; /* 24px */
rounded-r-full	        border-top-right-radius: 9999px;
                        border-bottom-right-radius: 9999px;

rounded-b-none	        border-bottom-right-radius: 0px;
                        border-bottom-left-radius: 0px;
rounded-b-sm	        border-bottom-right-radius: 0.125rem; /* 2px */
                        border-bottom-left-radius: 0.125rem; /* 2px */
rounded-b	            border-bottom-right-radius: 0.25rem; /* 4px */
                        border-bottom-left-radius: 0.25rem; /* 4px */
rounded-b-md	        border-bottom-right-radius: 0.375rem; /* 6px */
                        border-bottom-left-radius: 0.375rem; /* 6px */
rounded-b-lg	        border-bottom-right-radius: 0.5rem; /* 8px */
                        border-bottom-left-radius: 0.5rem; /* 8px */
rounded-b-xl	        border-bottom-right-radius: 0.75rem; /* 12px */
                        border-bottom-left-radius: 0.75rem; /* 12px */
rounded-b-2xl	        border-bottom-right-radius: 1rem; /* 16px */
                        border-bottom-left-radius: 1rem; /* 16px */
rounded-b-3xl	        border-bottom-right-radius: 1.5rem; /* 24px */
                        border-bottom-left-radius: 1.5rem; /* 24px */
rounded-b-full	        border-bottom-right-radius: 9999px;
                        border-bottom-left-radius: 9999px;

rounded-l-none	        border-top-left-radius: 0px;
                        border-bottom-left-radius: 0px;
rounded-l-sm	        border-top-left-radius: 0.125rem; /* 2px */
                        border-bottom-left-radius: 0.125rem; /* 2px */
rounded-l	            border-top-left-radius: 0.25rem; /* 4px */
                        border-bottom-left-radius: 0.25rem; /* 4px */
rounded-l-md	        border-top-left-radius: 0.375rem; /* 6px */
                        border-bottom-left-radius: 0.375rem; /* 6px */
rounded-l-lg	        border-top-left-radius: 0.5rem; /* 8px */
                        border-bottom-left-radius: 0.5rem; /* 8px */
rounded-l-xl	        border-top-left-radius: 0.75rem; /* 12px */
                        border-bottom-left-radius: 0.75rem; /* 12px */
rounded-l-2xl	        border-top-left-radius: 1rem; /* 16px */
                        border-bottom-left-radius: 1rem; /* 16px */
rounded-l-3xl	        border-top-left-radius: 1.5rem; /* 24px */
                        border-bottom-left-radius: 1.5rem; /* 24px */
rounded-l-full	        border-top-left-radius: 9999px;
                        border-bottom-left-radius: 9999px;

rounded-tl-none	        border-top-left-radius: 0px;
rounded-tl-sm	        border-top-left-radius: 0.125rem; /* 2px */
rounded-tl	            border-top-left-radius: 0.25rem; /* 4px */
rounded-tl-md	        border-top-left-radius: 0.375rem; /* 6px */
rounded-tl-lg	        border-top-left-radius: 0.5rem; /* 8px */
rounded-tl-xl	        border-top-left-radius: 0.75rem; /* 12px */
rounded-tl-2xl	        border-top-left-radius: 1rem; /* 16px */
rounded-tl-3xl	        border-top-left-radius: 1.5rem; /* 24px */
rounded-tl-full	        border-top-left-radius: 9999px;

rounded-tr-none	        border-top-right-radius: 0px;
rounded-tr-sm	        border-top-right-radius: 0.125rem; /* 2px */
rounded-tr	            border-top-right-radius: 0.25rem; /* 4px */
rounded-tr-md	        border-top-right-radius: 0.375rem; /* 6px */
rounded-tr-lg	        border-top-right-radius: 0.5rem; /* 8px */
rounded-tr-xl	        border-top-right-radius: 0.75rem; /* 12px */
rounded-tr-2xl	        border-top-right-radius: 1rem; /* 16px */
rounded-tr-3xl	        border-top-right-radius: 1.5rem; /* 24px */
rounded-tr-full	        border-top-right-radius: 9999px;

rounded-br-none	        border-bottom-right-radius: 0px;
rounded-br-sm	        border-bottom-right-radius: 0.125rem; /* 2px */
rounded-br	            border-bottom-right-radius: 0.25rem; /* 4px */
rounded-br-md	        border-bottom-right-radius: 0.375rem; /* 6px */
rounded-br-lg	        border-bottom-right-radius: 0.5rem; /* 8px */
rounded-br-xl	        border-bottom-right-radius: 0.75rem; /* 12px */
rounded-br-2xl	        border-bottom-right-radius: 1rem; /* 16px */
rounded-br-3xl	        border-bottom-right-radius: 1.5rem; /* 24px */
rounded-br-full	        border-bottom-right-radius: 9999px;

rounded-bl-none	        border-bottom-left-radius: 0px;
rounded-bl-sm	        border-bottom-left-radius: 0.125rem; /* 2px */
rounded-bl	            border-bottom-left-radius: 0.25rem; /* 4px */
rounded-bl-md	        border-bottom-left-radius: 0.375rem; /* 6px */
rounded-bl-lg	        border-bottom-left-radius: 0.5rem; /* 8px */
rounded-bl-xl	        border-bottom-left-radius: 0.75rem; /* 12px */
rounded-bl-2xl	        border-bottom-left-radius: 1rem; /* 16px */
rounded-bl-3xl	        border-bottom-left-radius: 1.5rem; /* 24px */
rounded-bl-full	        border-bottom-left-radius: 9999px;
```

```html
<div class="rounded ..."></div>
<div class="rounded-md ..."></div>
<div class="rounded-lg ..."></div>
<div class="rounded-full ..."></div>
```

Pill buttons:

```html
<button class="rounded-full ...">Save Changes</button>
```

No rounding/border-Radius:

```html
<button class="rounded-none ...">Save Changes</button>
```

Rounding sides separately:

```html
<div class="rounded-t-lg ..."></div>
<div class="rounded-r-lg ..."></div>
<div class="rounded-b-lg ..."></div>
<div class="rounded-l-lg ..."></div>
```

Rounding corners separately:

```html
<div class="rounded-tl-lg ..."></div>
<div class="rounded-tr-lg ..."></div>
<div class="rounded-br-lg ..."></div>
<div class="rounded-bl-lg ..."></div>
```

On Hover:

```html
<div class="rounded hover:rounded-lg">
  <!-- ... -->
</div>
```

On Media Queries:

```html
<div class="rounded md:rounded-lg">
  <!-- ... -->
</div>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    borderRadius: {
      'none': '0',
      'sm': '0.125rem',
      DEFAULT: '0.25rem',
      DEFAULT: '4px',
      'md': '0.375rem',
      'lg': '0.5rem',
      'full': '9999px',
      'large': '12px',
    }
  }
}
```

Exact Values:

```html
<div class="rounded-[12px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>62. Border Width</summary>

```html
Class                   Properties
border-0	            border-width: 0px;
border-2	            border-width: 2px;
border-4	            border-width: 4px;
border-8	            border-width: 8px;
border	                    border-width: 1px;

border-x-0	            border-left-width: 0px;
                        border-right-width: 0px;
border-x-2	            border-left-width: 2px;
                        border-right-width: 2px;
border-x-4	            border-left-width: 4px;
                        border-right-width: 4px;
border-x-8	            border-left-width: 8px;
                        border-right-width: 8px;
border-x	            border-left-width: 1px;
                        border-right-width: 1px;

border-y-0	            border-top-width: 0px;
                        border-bottom-width: 0px;
border-y-2	            border-top-width: 2px;
                        border-bottom-width: 2px;
border-y-4	            border-top-width: 4px;
                        border-bottom-width: 4px;
border-y-8	            border-top-width: 8px;
                        border-bottom-width: 8px;
border-y	            border-top-width: 1px;
                        border-bottom-width: 1px;

border-t-0	            border-top-width: 0px;
border-t-2	            border-top-width: 2px;
border-t-4	            border-top-width: 4px;
border-t-8	            border-top-width: 8px;
border-t	            border-top-width: 1px;

border-r-0	            border-right-width: 0px;
border-r-2	            border-right-width: 2px;
border-r-4	            border-right-width: 4px;
border-r-8	            border-right-width: 8px;
border-r	            border-right-width: 1px;

border-b-0	            border-bottom-width: 0px;
border-b-2	            border-bottom-width: 2px;
border-b-4	            border-bottom-width: 4px;
border-b-8	            border-bottom-width: 8px;
border-b	            border-bottom-width: 1px;

border-l-0	            border-left-width: 0px;
border-l-2	            border-left-width: 2px;
border-l-4	            border-left-width: 4px;
border-l-8	            border-left-width: 8px;
border-l	            border-left-width: 1px;
```

All sides:

```html
<div class="border border-sky-500"></div>
<div class="border-2 border-sky-500"></div>
<div class="border-4 border-sky-500"></div>
<div class="border-8 border-sky-500"></div>
```

Individual sides:

```html
<div class="border-t-4 border-indigo-500 ..."></div>
<div class="border-r-4 border-indigo-500 ..."></div>
<div class="border-b-4 border-indigo-500 ..."></div>
<div class="border-l-4 border-indigo-500 ..."></div>
```

Horizontal and vertical sides:

```html
<div class="border-x-4 border-indigo-500 ..."></div>
<div class="border-y-4 border-indigo-500 ..."></div>
```

Between elements:

```html
<div class="divide-y divide-slate-700 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

On Hover:

```html
<div class="border-2 hover:border-t-4">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="border-2 md:border-t-4">
  <!-- ... -->
</div>
```

Custom Values:

```js
module.exports = {
  theme: {
    borderWidth: {
      DEFAULT: '1px',
      '0': '0',
      '2': '2px',
      '3': '3px',
      '4': '4px',
      '6': '6px',
      '8': '8px',
    }
  }
}
```

Exact Values:

```html
<div class="border-t-[3px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>63. Border Color</summary>

```html
Class                               Properties

border-inherit	                    border-color: inherit;
border-current	                    border-color: currentColor;
border-transparent	            border-color: transparent;
border-black	                    border-color: rgb(0 0 0);
border-white	                    border-color: rgb(255 255 255);

border-slate-50	                    border-color: rgb(248 250 252);
border-slate-100	            border-color: rgb(241 245 249);
border-slate-200	            border-color: rgb(226 232 240);
border-slate-300	            border-color: rgb(203 213 225);
border-slate-400	             border-color: rgb(148 163 184);
border-slate-500	            border-color: rgb(100 116 139);
border-slate-600	            border-color: rgb(71 85 105);
border-slate-700	            border-color: rgb(51 65 85);
border-slate-800	            border-color: rgb(30 41 59);
border-slate-900	            border-color: rgb(15 23 42);
```

Setting the border color:

```html
<input class="border-2 border-rose-500 ...">
```

Changing the opacity:

```html
<div class="border-4 border-indigo-500/100 ..."></div>
<div class="border-4 border-indigo-500/75 ..."></div>
<div class="border-4 border-indigo-500/50 ..."></div>
```

```html
<div class="border-4 border-indigo-600/[.55] ..."></div>
```

Individual sides:

```html
<div class="border-4 border-indigo-200 border-t-indigo-500 ..."></div>
<div class="border-4 border-indigo-200 border-r-indigo-500 ..."></div>
<div class="border-4 border-indigo-200 border-b-indigo-500 ..."></div>
<div class="border-4 border-indigo-200 border-l-indigo-500 ..."></div>
```

Horizontal and vertical sides:

```html
<div class="border-4 border-indigo-200 border-x-indigo-500 ..."></div>
<div class="border-4 border-indigo-200 border-y-indigo-500 ..."></div>
```

On Hover:

```html
<button class="border border-slate-300 hover:border-slate-400 ...">
  Send email
</button>
```

On Media queries:

```html
<button class="border-blue-500 md:border-green-500">
  <!-- ... -->
</button>
```

Custom Values:

tailwind.config.js:

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'regal-blue': '#243c5a',
      },
    }
  }
}
```

Exact Values:

```html
<button class="border-[#243c5a]">
  <!-- ... -->
</button>
```

</details>

<details>
  <summary>64. Border Style</summary>

```html
Class                       Properties
border-solid	            border-style: solid;
border-dashed	            border-style: dashed;
border-dotted	            border-style: dotted;
border-double	            border-style: double;
border-hidden	            border-style: hidden;
border-none	                border-style: none;
```

```html
<div class="border-solid border-2 border-sky-500 ..."></div>
<div class="border-dashed border-2 border-sky-500 ..."></div>
<div class="border-dotted border-2 border-sky-500 ..."></div>
<div class="border-double border-4 border-sky-500 ..."></div>
```

No style:

```html
<button class="border-none ...">Save Changes</button>
```

On Hover:

```html
<div class="border-solid hover:border-dotted">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="border-solid md:border-dotted">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>65. Divide Width</summary>

Add borders between horizontal children:

```html
<div class="grid grid-cols-3 divide-x">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

Add borders between stacked children:

```html
<div class="grid grid-cols-1 divide-y">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

Reversing children order:

```html
<div class="flex flex-col-reverse divide-y divide-y-reverse">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

On Hover:

```html
<div class="divide-y divide-gray-400 hover:divide-y-8">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="divide-y divide-gray-400 md:divide-y-8">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="divide-x-[3px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>66. Divide Color</summary>

Setting the divide color:

```html
<div class="divide-y divide-blue-200">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

Changing the opacity:

```html
<div class="divide-y-4 divide-slate-400/25 ...">
  <!-- ... -->
</div>
```

```html
<div class="divide-y-4 divide-slate-400/[.24] ...">
  <!-- ... -->
</div>
```

On Hover:

```html
<div class="divide-y divide-teal-400 hover:divide-pink-400">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="divide-y divide-teal-400 md:divide-pink-400">
  <!-- ... -->
</div>
```

Custom Values:

```html
<div class="divide-[#243c5a]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>67. Divide Style</summary>

Set the divide style:

```html
<div class="divide-y divide-dashed">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

On Hover:

```html
<div class="divide-y divide-dashed hover:divide-solid">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="divide-y divide-dashed md:divide-solid">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>68. Outline Width</summary>

Setting the outline width:

```html
<button class="outline outline-offset-2 outline-1 ...">Button A</button>
<button class="outline outline-offset-2 outline-2 ...">Button B</button>
<button class="outline outline-offset-2 outline-4 ...">Button C</button>
```

On Hover:

```html
<div class="outline hover:outline-2">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="outline md:outline-2">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="outline-[5px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>69. Outline Color</summary>

Setting the outline color:

```html
<button class="outline outline-offset-2 outline-blue-500 ...">Button A</button>
<button class="outline outline-offset-2 outline-cyan-500 ...">Button B</button>
<button class="outline outline-offset-2 outline-pink-500 ...">Button C</button>
```

Changing the opacity:

```html
<button class="outline-2 outline-blue-500/50 ...">Save Changes</button>
```

```html
<button class="outline-4 outline-pink-400/[.55] ..."></button>
```

On Hover:

```html
<button class="outline hover:outline-blue-400">
  <!-- ... -->
</button>
```

On Media queries:

```html
<button class="outline md:outline-blue-400">
  <!-- ... -->
</button>
```

Exact Values:

```html
<button class="outline-[#243c5a]">
  <!-- ... -->
</button>
```

</details>

<details>
  <summary>70. Outline Style</summary>

Setting the outline style:

```html
<button class="outline outline-2  outline-offset-2 ...">Button A</button>
<button class="outline-dashed outline-2 outline-offset-2 ...">Button B</button>
<button class="outline-dotted outline-2 outline-offset-2 ...">Button C</button>
<button class="outline-double outline-3 outline-offset-2 ...">Button D</button>
```

Removing outlines:

```html
<input type="text"
  placeholder="Default focus style"
  class="..." />

<input type="text"
  placeholder="Custom focus style"
  class="focus:outline-none focus:ring focus:border-blue-500 ..." />
```

On Hover:

```html
<div class="outline hover:outline-dashed">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="outline md:outline-dashed">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>71. Outline Offset</summary>

Setting the outline offset:

```html
<button class="outline outline-offset-0 ...">Button A</button>
<button class="outline outline-offset-2 ...">Button B</button>
<button class="outline outline-offset-4 ...">Button C</button>
```

On Hover:

```html
<button class="outline hover:outline-offset-2">
  <!-- ... -->
</button>
```

On Media queries:

```html
<button class="outline md:outline-offset-2">
  <!-- ... -->
</button>
```

Exact Values:

```html
<button class="outline-offset-[3px]">
  <!-- ... -->
</button>
```

</details>

<details>
  <summary>72. Ring Width</summary>

Adding a ring:

```html
<button class="... ring-offset-2 ring-2">Button A</button>
<button class="... ring-offset-2 ring">Button B</button>
<button class="... ring-offset-2 ring-4">Button C</button>
```

```html
<button class="... focus:ring-2">Save Changes</button>
```

Inset rings:

```html
<button class="... ring-2 ring-pink-500 ring-inset">
  Save Changes
</button>
```

On Hover:

```html
<div class="ring-2 hover:ring-4">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="ring-2 md:ring-4">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="ring-[10px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>73. Ring Color</summary>

Setting the ring color:

```html
<button class="... ring-2 ring-blue-500">
  Create account
</button>
```

Changing the opacity:

```html
<button class="... ring-2 ring-blue-500/50">Subscribe</button>
```

```html
<button class="... ring-2 ring-blue-500/[.55]">Subscribe</button>
```

On Hover:

```html
<div class="ring ring-blue-300 hover:ring-blue-500">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="ring ring-blue-300 md:ring-blue-500">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="ring-[#50d71e]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>74. Ring Offset Width</summary>

Setting the ring offset width:

```html
<button class="... ring ring-pink-500 ring-offset-0">Button A</button>
<button class="... ring ring-pink-500 ring-offset-2">Button B</button>
<button class="... ring ring-pink-500 ring-offset-4">Button C</button>
```

Changing the offset color:

```html
<button class="ring ring-pink-500 ring-offset-2 ring-offset-slate-50 dark:ring-offset-slate-900 ...">
  Save Changes
</button>
```

On Hover:

```html
<button class="ring-2 ring-offset-2 hover:ring-offset-4">
  <!-- ... -->
</button>
```

On Media queries:

```html
<button class="ring-2 ring-offset-2 md:ring-offset-4">
  <!-- ... -->
</button>
```

Exact Values:

```html
<div class="ring-offset-[3px]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>75. Ring Offset Color</summary>

Setting the ring offset color:

```html
<button class="ring-2 ring-purple-500 ring-offset-4 ring-offset-slate-50 dark:ring-offset-slate-900 ...">
  Save Changes
</button>
```

Changing the opacity:

```html
<button class="ring-2 ring-purple-500 ring-offset-4 ring-offset-purple-100/50"></button>
```

```html
<button class="ring-2 ring-purple-500 ring-offset-4 ring-offset-purple-100/[.55]"></button>
```

On Hover:

```html
<div class="ring-2 ring-offset-2 ring-offset-blue-300 hover:ring-offset-blue-500">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="ring-2 ring-offset-2 ring-offset-blue-300 md:ring-offset-blue-500">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="ring-offset-[#50d71e]">
  <!-- ... -->
</div>
```

</details>

##### [D. CUSTOMIZATION](#)

<details>
  <summary>76. Tailwind Config Files</summary>

tailwindcss.config.js:

```js
module.exports = {
  content: ['./src/**/*.{html,js}'],
  // content: ['./public/*.{html,js}'],
  theme: {
    colors: {
      'blue': '#1fb6ff',
      'purple': '#7e5bef',
      'pink': '#ff49db',
      'orange': '#ff7849',
      'green': '#13ce66',
      'yellow': '#ffc82c',
      'gray-dark': '#273444',
      'gray': '#8492a6',
      'gray-light': '#d3dce6',
    },
    fontFamily: {
      sans: ['Graphik', 'sans-serif'],
      serif: ['Merriweather', 'serif'],
    },
    extend: {
      spacing: {
        '8xl': '96rem',
        '9xl': '128rem',
      },
      borderRadius: {
        '4xl': '2rem',
      }
    }
  },
}
```

Install Config file:

```bash
npx tailwindcss init
npx tailwindcss init --full

npx tailwindcss init tailwindcss-config.js
```

```bash
npm run build-css

npx tailwindcss -c ./tailwindcss-config.js -i input.css -o output.css
```

tailwindcss.config.js:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./public/*.{html,js}"],
  theme: {
    extend: {
      colors: {
        primary: '#FF6363',
        secondary: {
        100: '#E2E2D5',
        200: '#888883',
        }
      }
    },
  },
  plugins: [],
}
```

```html
<div class="">
    <a class="text-primary" href="#">Log in</a>
    <a class="text-secondary-100" href="#">Sign up</a>
</div>
```

</details>

<details>
  <summary>77. Custom Font Family</summary>

```html
<body class="text-gray-600 px-4 font-serif">
```

styles.css:

```css
@import url('https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;0,1000;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900;1,1000&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;
```

tailwindcss.config.js:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./public/*.{html,js}"],
  theme: {
    extend: {
      colors: {
        primary: '#FF6363',
        secondary: {
        100: '#E2E2D5',
        200: '#888883',
        }
      },
      fontFamily: {
        nunito: ['Nunito']
      }
    },
  },
  plugins: [],
}

```

```html
npm run build-css
```

```html
<body class="text-gray-600 px-4 font-nunito">
```

</details>

##### [E. FLEXBOX & GRID](#)

<details>
  <summary>78. Flex Basis</summary>

```html
Class               Properties
basis-0	            flex-basis: 0px;
basis-1	            flex-basis: 0.25rem; /* 4px */
basis-2	            flex-basis: 0.5rem; /* 8px */
basis-3	            flex-basis: 0.75rem; /* 12px */
basis-4	            flex-basis: 1rem; /* 16px */
basis-5	            flex-basis: 1.25rem; /* 20px */
basis-6	            flex-basis: 1.5rem; /* 24px */
basis-7	            flex-basis: 1.75rem; /* 28px */
basis-8	            flex-basis: 2rem; /* 32px */
basis-9	            flex-basis: 2.25rem; /* 36px */
basis-10	        flex-basis: 2.5rem; /* 40px */
basis-11	        flex-basis: 2.75rem; /* 44px */
basis-12	        flex-basis: 3rem; /* 48px */
basis-14	        flex-basis: 3.5rem; /* 56px */
basis-16	        flex-basis: 4rem; /* 64px */
basis-20	        flex-basis: 5rem; /* 80px */
basis-24	        flex-basis: 6rem; /* 96px */
basis-28	        flex-basis: 7rem; /* 112px */
basis-32	        flex-basis: 8rem; /* 128px */
basis-36	        flex-basis: 9rem; /* 144px */
basis-40	        flex-basis: 10rem; /* 160px */
basis-44	        flex-basis: 11rem; /* 176px */
basis-48	        flex-basis: 12rem; /* 192px */
basis-52	        flex-basis: 13rem; /* 208px */
basis-56	        flex-basis: 14rem; /* 224px */
basis-60	        flex-basis: 15rem; /* 240px */
basis-64	        flex-basis: 16rem; /* 256px */
basis-72	        flex-basis: 18rem; /* 288px */
basis-80	        flex-basis: 20rem; /* 320px */
basis-96	        flex-basis: 24rem; /* 384px */

basis-auto	        flex-basis: auto;
basis-px	        flex-basis: 1px;
basis-0.5	        flex-basis: 0.125rem; /* 2px */
basis-1.5	        flex-basis: 0.375rem; /* 6px */
basis-2.5	        flex-basis: 0.625rem; /* 10px */
basis-3.5	        flex-basis: 0.875rem; /* 14px */
basis-1/2	        flex-basis: 50%;
basis-1/3	        flex-basis: 33.333333%;
basis-2/3	        flex-basis: 66.666667%;
basis-1/4	        flex-basis: 25%;
basis-2/4	        flex-basis: 50%;
basis-3/4	        flex-basis: 75%;
basis-1/5	        flex-basis: 20%;
basis-2/5	        flex-basis: 40%;
basis-3/5	        flex-basis: 60%;
basis-4/5	        flex-basis: 80%;
basis-1/6	        flex-basis: 16.666667%;
basis-2/6	        flex-basis: 33.333333%;
basis-3/6	        flex-basis: 50%;
basis-4/6	        flex-basis: 66.666667%;
basis-5/6	        flex-basis: 83.333333%;
basis-1/12	        flex-basis: 8.333333%;
basis-2/12	        flex-basis: 16.666667%;
basis-3/12	        flex-basis: 25%;
basis-4/12	        flex-basis: 33.333333%;
basis-5/12	        flex-basis: 41.666667%;
basis-6/12	        flex-basis: 50%;
basis-7/12	        flex-basis: 58.333333%;
basis-8/12	        flex-basis: 66.666667%;
basis-9/12	        flex-basis: 75%;
basis-10/12	        flex-basis: 83.333333%;
basis-11/12	        flex-basis: 91.666667%;
basis-full	        flex-basis: 100%;
```

Setting the flex basis:

```html
<div class="flex flex-row">
  <div class="basis-1/4">01</div>
  <div class="basis-1/4">02</div>
  <div class="basis-1/2">03</div>
</div>
```

On Hover:

```html
<div class="basis-1/3 hover:basis-1/2">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="flex flex-row">
  <div class="basis-1/4 md:basis-1/3">01</div>
  <div class="basis-1/4 md:basis-1/3">02</div>
  <div class="basis-1/2 md:basis-1/3">03</div>
</div>
```

Exact Values:

```html
<div class="basis-[14.2857143%]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>79. Flex Direction</summary>

```html
Class                   Properties
flex-row	            flex-direction: row;
flex-row-reverse	    flex-direction: row-reverse;
flex-col	            flex-direction: column;
flex-col-reverse	    flex-direction: column-reverse;
```

```html
<div class="flex flex-row ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

```html
<div class="flex flex-row-reverse ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

```html
<div class="flex flex-col ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

```html
<div class="flex flex-col-reverse ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

On Hover:

```html
<div class="flex flex-col hover:flex-row">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="flex flex-col md:flex-row">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>80. Flex Wrap</summary>

```html
Class                       Properties
flex-wrap	                flex-wrap: wrap;
flex-wrap-reverse	        flex-wrap: wrap-reverse;
flex-nowrap	                flex-wrap: nowrap;
```

Don't wrap:

```html
<div class="flex flex-nowrap">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

Wrap normally:

```html
<div class="flex flex-wrap">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

Wrap reversed:

```html
<div class="flex flex-wrap-reverse">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

On Hover:

```html
<div class="flex flex-wrap hover:flex-wrap-reverse">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="flex flex-wrap md:flex-wrap-reverse">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>81. Flex</summary>

Utilities for controlling how flex items both grow and shrink.

```html
Class               Properties
flex-1	            flex: 1 1 0%;
flex-auto	        flex: 1 1 auto;
flex-initial	    flex: 0 1 auto;
flex-none	        flex: none;
```

Initial:
Use flex-initial to allow a flex item to shrink but not grow, taking into account its initial size:

```html
<div class="flex">
  <div class="flex-none w-14 h-14">
    01
  </div>
  <div class="flex-initial w-64 ...">
    02
  </div>
  <div class="flex-initial w-32 ...">
    03
  </div>
</div>
```

Flex 1
Use flex-1 to allow a flex item to grow and shrink as needed, ignoring its initial size:

```html
<div class="flex">
  <div class="flex-none ...">
    01
  </div>
  <div class="flex-1 w-64 ...">
    02
  </div>
  <div class="flex-1 w-32 ...">
    03
  </div>
</div>
```

Auto
Use flex-auto to allow a flex item to grow and shrink, taking into account its initial size:

```html
<div class="flex ...">
  <div class="flex-none ...">
    01
  </div>
  <div class="flex-auto w-64 ...">
    02
  </div>
  <div class="flex-auto w-32 ...">
    03
  </div>
</div>
```

None
Use flex-none to prevent a flex item from growing or shrinking:

```html
<div class="flex ...">
  <div class="flex-none w-14 h-14 ...">
    01
  </div>
  <div class="flex-none ...">
    02
  </div>
  <div class="flex-1 ...">
    03
  </div>
</div>
```

On Hover:

```html
<div class="flex-none hover:flex-1">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="flex-none md:flex-1">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="flex-[2_2_0%]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>82. Flex Grow</summary>

```html
Class           Properties
grow	        flex-grow: 1;
grow-0	        flex-grow: 0;
```

Grow
Use grow to allow a flex item to grow to fill any available space:

```html
<div class="flex ...">
  <div class="flex-none w-14 h-14 ...">
    01
  </div>
  <div class="grow h-14 ...">
    02
  </div>
  <div class="flex-none w-14 h-14 ...">
    03
  </div>
</div>
```

Don't grow
Use grow-0 to prevent a flex item from growing:

```html
<div class="flex ...">
  <div class="grow h-14 ...">
    01
  </div>
  <div class="grow-0 h-14 ...">
    02
  </div>
  <div class="grow h-14 ...">
    03
  </div>
</div>
```

On Hover:

```html
<div class="grow hover:grow-0">
  <!-- ... -->
</div>
```

On Media queries:

```html
<div class="grow md:grow-0">
  <!-- ... -->
</div>
```

Exact Values:

```html
<div class="grow-[2]">
  <!-- ... -->
</div>
```

</details>

<details>
  <summary>83. sample</summary>

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
  <summary>84. sample</summary>

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
  <summary>85. sample</summary>

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
  <summary>86. sample</summary>

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
  <summary>87. sample</summary>

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
  <summary>88. sample</summary>

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
  <summary>89. sample</summary>

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
  <summary>90. sample</summary>

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
  <summary>91. sample</summary>

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
  <summary>92. sample</summary>

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
  <summary>93. sample</summary>

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
  <summary>94. sample</summary>

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
  <summary>95. sample</summary>

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
  <summary>96. sample</summary>

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
  <summary>97. sample</summary>

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
  <summary>98. sample</summary>

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
  <summary>99. sample</summary>

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
  <summary>100. sample</summary>

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




##### [E. CUSTOMIZATION](#)