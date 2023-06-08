# Installation & Setup Guide of Tailwind CSS with PHP

**TailwindCSS** is an open-source "Utility-first framework" of CSS (Cascading style sheet).

**PHP** is a server-side scripting language used to manage the Back-end of the Web Application.

So there are 2 ways to Install & Setup Guide to install TailwindCSS with PHP:

*Method 1:* Put the PlayCDN script directly into the PHP file and run it directly:

Create a new File named index.php in xampp/htdocs forlder.

Now at the Following CDN command in the last of the HTML body section.

```html
<script src="https://cdn.tailwindcss.com"></script>
```

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <h1 class='text-3xl font-bold underline bg-slate-500 p-5 text-blue-300'>Tailwindcss using Play CDN</h1>
  <script src="https://cdn.tailwindcss.com"></script>
</body>
</html>
```

Go to the browser and type **localhost/foldername**.

But for Production, CDN is not recommended.

*Method 2:* By Using CLI with a small modification: You can use TailwindCSS with PHP easily by following these steps.

Create a Brand New folder and Open that folder with any Code Editor.

**Step 1.** Create a new File named index.php in xampp/htdocs folder.
**Step 2.** Install TailwindCSS: Use terminal to install Tailwindcss by following these commands.

```sh
npm install -D tailwindcss
```

**Step 3.** Create TailwindCSS config file: Copy and Paste this command into the Terminal to create TailwindCSS config file.

```sh
npx tailwindcss init
```

This commadn will create on file named as tailwind.config.js.

**Step 4.** Configure the tailwind.config.js file: Open the tailwind.config.js file and replace the existing code with this code.

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
    content: ["*/*.{html,js,php}"],
     theme: {
       extend: {},
 },
     plugins: [],
}
```

**Step 5.** Add the Tailwind directives to your CSS: create an input.css file in the folder(directory).

Paste the following code into it.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Now, link that input.css file index.php that we created earlier.

**Step 6.** Start the Tailwind CLI build process: run the following command in the Terminal.

```sh
npx tailwindcss -i input.css -o output.css --watch
```

**Step 7.** Check if the Setup is running: Copy and paste the following code in the index.php file to check if the Code is running and save it.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href='output.css' rel='stylesheet'>
  <title>Document</title>
</head>
<body>
  <h1 class='text-3xl font-bold underline'>Hello World</h1>
</body>
</html>
```

and Go to the browser and type localhost/foldername.

One more thing! Before deploying to production, make sure to minify output.css first. This will reduce its size and improve loading speed. Open package.json and paste this code.

```js
{
  ...
  "scripts": {
    "dev": "npx tailwindcss -i input.css -o output.css --watch",
    "build": "npx tailwindcss -i input.css -o output.css --minify"
  }
}
```