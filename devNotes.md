# Development Notes for Der Berg

This is a site built following the MDN [Client-Side Tools](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Client-side_tools/Package_management) walkthrough.

The final build can be viewed on my [github.io site](https://treagleman.github.io/derberg/)

It includes the boilerplate for a basic web application useing web development tools such as npm, vite, frameworks, etc.

The process includes:

1. creating a directory
2. initialize and configure npm
3. install vite as a dependency
4. setup for a basic app.

## Dependency scripts

Installs:

`npm install --save-dev vite`  
`npm install plotly.js-dist-min`  
`npm install --save-dev prettier`  
`npm install --save-dev eslint@8 @eslint/js globals`
`npm install --save-dev eslint-plugin-react eslint-plugin-react-hooks`
`npm install --save-dev @vitejs/plugin-react`
`npm install react react-dom @tanstack/react-query`

Prettier:

`npx prettier --write ./index.html`

## Tips

Use `npx` to run scripts local to the repository. This removes the need to declare npm scripts in the package.json file if desired. E.g. `npx vite` rather than `npm run dev` with vite configured to the dev script.

Use `npm update` to update all the dependency versions listed in your package.json. This will update all minor release versions. Major release versions will need to be installed separately.

JavaScript Transformation in vite can be done with an integrated plugin `@vitejs/plugin-react` rather than a transformation tool such as **Babel**.


Rather than a postprocessor such as PostCSS, vite allows the use of [css modules](https://vite.dev/guide/features.html#css-modules).
>  <a href="https://vite.dev/guide/features.html#postcss" class="external" target="_blank">Vite supports PostCSS by default</a>, so you just need to <a href="https://github.com/postcss/postcss#usage" class="external" target="_blank">configure PostCSS</a> if you want to compile any features. Check out the <a href="https://preset-env.cssdb.org/features/" class="external" target="_blank">cssdb</a> for what features are supported.

## Deploy

Github deployment steps:

1. You push your code to GitHub.
2. You define a GitHub Action that gets triggered when there's a new push to the main branch, which builds the code and puts it at a specific location.
3. GitHub Pages then serves the code at a specific URL.

Vite comes pre-packaged with all the build tools installed such as *tree-shaking*, *minification*, and *cache-busting*.

It is best practice to always include the build command as a script in the package.json.

[Publishing with a custom GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow)