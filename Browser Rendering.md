# How Does a Browser Render HTML, CSS, and JS to the DOM? What Is the Mechanism Behind It?

The mechanism behind parsing HTML, CSS, and JS is called the **Critical Rendering Path (CRP)**. It's a process where the browser collects code from HTML, CSS, and JS files and merges it into the rendering tree. Although this process isn't necessarily always sequential, the baseline implementation flows in that order.

Let's break down the rendering (CRP) process into steps for easy explanation. When the browser receives the HTML, CSS, and JS files from the network, it processes them into the following sequence:

## 1. HTML to DOM

### 1.1
The browser reads the raw bytes from the HTML file and converts them into characters based on an encoding method such as UTF-8.

### 1.2
It converts those characters into W3C standard tokens like `<head>`, `<body>` etc.

### 1.3
The tokens are converted into objects with their rules and properties.

### 1.4
Finally, the browser structures these nodes into a tree hierarchy. This is our DOM.

## 2. CSS to CSSOM

### 2.1
While parsing the HTML file, the browser encounters the CSS file through a `<link>` or `<style>` tag. It pauses the HTML parsing (or performs in parallel) and follows pretty much the same process as the DOM.

### 2.2
It goes like raw bits> characters > tokens > objects > CSSOM.

## 3. JS

### 3.1
When the browser encounters `<script>` tag, it pauses the HTML rendering and loads the script, and passes it to the browser's JS engine (V8 in Chrome, SpiderMonkey in Firefox).

### 3.2
Since a JS script can affect the DOM and CSSOM, it is given priority to read the correct style and object model.

### 3.3
Once it's done, the browser resumes DOM construction where it left off.

## 4. Integeration

Once the DOM, CSSOM, and JS are done processing, the browser turns everything into a rendering tree. The rendering tree only contains the nodes that finally have to be visible on the screen. For example, it excludes elements with `display:none` and includes elements with `display:hidden` properties.

## 5. Layout and Formatting

The browser calculates the size and position for each element according to the screen size.

## 6. Painting

The browser uses a graphics engine (like Skia in Chrome) to convert the elements into a bitmap and shows the final frame on the screen.

# References

- Link: https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/Critical_rendering_path
- Link: https://developer.chrome.com/docs/web-platform/blink
- Link: https://web.dev/learn/performance/understanding-the-critical-path
