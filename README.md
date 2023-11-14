# Vite Yu-Gi-Oh


## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
## Description 
![Alt text](Screenshot.png)
Create a new project using Vite and Vue 3 and define the components necessary to structure the layout as the attached screenshot.
When the page loads, make an ajax call to the Yu Gi Oh API: https://db.ygoprodeck.com/api/v7/cardinfo.php
and with the data returned, print a card for each card.
Then add a search bar to filter results by archetype.