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

Font Size change on Hover:

```html
<a class="text-4xl hover:text-base" href="/">Food Ninja</a>
```

Font Size change on media queries:

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

Font Size Exact Values:

```html
<a class="text-[32px] lg:text-[8rem]" href="/">Food Ninja</a>
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

Text Color change on Hover:

```html
<p class="text-slate-400 hover:text-sky-400">The quick brown fox...</p>
```

Text Color change on media queries:

```html
<p class="text-slate-400 lg:text-sky-400">The quick brown fox...</p>
```

Text Color Custom Values:

```html
<h2 class="text-exclusive text-6xl font-semibold">Recipes</h2>
```

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

Text Color Exact Values:

```html
<h2 class="text-[#50d71e] text-6xl font-semibold">Recipes</h2>
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

Font Weight Custom Values:

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

```html
<h2 class="text-[#30638E] text-6xl font-extreme">Recipes</h2>
```

Font Weight Exact Values:

```html
<h2 class="text-[#30638E] text-6xl font-[900]">Recipes</h2>
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

Text Transform change on Hover:

```html
<h2 class="text-[#30638E] text-6xl font-[900] hover:uppercase">Recipes</h2>
```

Text Transform on media queries:

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

Font-Family Custom Values:

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

Font-Family Exact Values:

```html
<h2 class="text-[#30638E] text-6xl font-[900] lg:uppercase font-['Open_Sans']">Recipes</h2>
```

Font-Family Base Values:

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

Font Style change on hover:

```html
<h2 class="text-[#30638E] text-6xl font-[900] hover:italic">Recipes</h2>
```

Font Style change on media queries:

```html
<h2 class="text-[#30638E] text-6xl font-[900] lg:italic">Recipes</h2>
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

```html
node -v
```

Letter Spacing Custom Values

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

Letter Spacing Exact Values:

```html
<h2 class="text-[#30638E] text-6xl font-[900] tracking-[.25em]">Recipes</h2>
```

</details>

+LINE-HEIGHT

<details>
  <summary>31. Line Height</summary>

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

</details>

<details>
  <summary>32. Line Height change on hover</summary>

```html
<h3 class="text-2xl font-semibold leading-none hover:leading-loose">For Ninjas</h3>
```

</details>

<details>
  <summary>33. Line Height change on media queries</summary>

```html
<h3 class="text-2xl font-semibold leading-none lg:leading-loose">For Ninjas</h3>
```

</details>

<details>
  <summary>34. Line Height Custom Values</summary>

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

</details>

<details>
  <summary>35. Line Height Exact Values</summary>

```html
<h3 class="text-2xl font-semibold leading-[3rem]">For Ninjas</h3>
```

</details>

+LIST STYLE

<details>
  <summary>36. List Style Type</summary>

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

</details>

<details>
  <summary>37. List Style Type change on hover</summary>

```html
<ol class="list-none hover:list-decimal list-inside">
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
</ol>
```

</details>

<details>
  <summary>38. List Style Type change on media queries</summary>

```html
<ol class="list-none lg:list-decimal list-inside">
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
</ol>
```

</details>

<details>
  <summary>39. List Style Type Custom Values</summary>

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

</details>

<details>
  <summary>40. List Style Type Exact Values</summary>

```html
 <ol class="list-[upper-roman] list-inside">
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
    <li>Now this is a story all about how, my life got flipped-turned upside down</li>
</ol>
```

</details>

<details>
  <summary>41. List Style Position</summary>

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

+TEXT-ALIGN

<details>
  <summary>42. Text Align</summary>

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

</details>

<details>
  <summary>43. Text Align change on hover </summary>

```html
<p class="text-left hover:text-center">So I started to walk into the water...</p>
```

</details>

<details>
  <summary>44. Text Align change on media queries</summary>

```html
<p class="text-left lg:text-center">So I started to walk into the water...</p>
```

</details>

+TEXT-DECORATION

<details>
  <summary>45. Text Decoration</summary>

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

</details>

<details>
  <summary>46. Text Decoration change on hover </summary>

```html
<a href="#" class="no-underline hover:underline">This is a sentence.</a>
```

</details>

<details>
  <summary>47. Text Decoration change on media queries </summary>

```html
<a href="#" class="no-underline lg:underline">This is a sentence.</a>
```

</details>

<details>
  <summary>48. Text Decoration Color</summary>

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

```html
<a href="#" class="no-underline hover:underline hover:decoration-pink-700">This is a sentence.</a>
```

Arbitrary values:

```html
<p class="decoration-[#50d71e]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>49. Text Decoration Style</summary>

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

</details>

<details>
  <summary>50. Text Decoration Thickness</summary>

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

Arbitrary values:

```html
<p class="decoration-[3px]">
  <!-- ... -->
</p>
```

</details>

<details>
  <summary>51. sample</summary>

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
  <summary>52. sample</summary>

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
  <summary>53. sample</summary>

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
  <summary>54. sample</summary>

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
  <summary>55. sample</summary>

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
  <summary>56. sample</summary>

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
  <summary>57. sample</summary>

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
  <summary>58. sample</summary>

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
  <summary>59. sample</summary>

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
  <summary>60. sample</summary>

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




##### [B. TYPOGRAPHY](#)