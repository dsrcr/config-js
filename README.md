# Project setup 🚀

<p align="center">
  <a href="https://github.com/dsrcr/config-js/stargazers">
    <img
      alt="Stargazers"
      src="https://img.shields.io/github/stars/dsrcr/config-js?style=for-the-badge&logo=starship&color=c678dd&logoColor=d9e0ee&labelColor=282a36"
    />
  </a>
  <a href="https://github.com/dsrcr/config-js/issues">
    <img
      alt="Issues"
      src="https://img.shields.io/github/issues/dsrcr/config-js?style=for-the-badge&logo=gitbook&color=f0c062&logoColor=d9e0ee&labelColor=282a36"
    />
  </a>
  <a href="https://github.com/dsrcr/config-js/contributors">
    <img
      alt="Contributors"
      src="https://img.shields.io/github/contributors/dsrcr/config-js?style=for-the-badge&logo=opensourceinitiative&color=abcf84&logoColor=d9e0ee&labelColor=282a36"
    />
  </a>
</p>

### Initial
I'm using Vite + pnpm to build my React projects.
Run this to initialize a project
```shell
pnpm create vite
```
Next, cd into the new project, install node_mods and check if everything works.
### Eslint
Run this and follow the instructions to generate .eslint.json
```bash
pnpm create @eslint/config
```
***[ Important ]*** Make sure eslint works
```bash
eslint .
```
Replace .eslint.json with this
```json
{
    "env": {
        "browser": true,
        "es2021": true,
        "jest": true
    },
    "extends": [
        "plugin:react/recommended",
        "airbnb",
        "react-app",
        "react-app/jest",
        "plugin:prettier/recommended"
    ],
    "overrides": [],
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    },
    "plugins": ["react", "prettier"],
    "rules": {
        "no-shadow": "off",
        "react/react-in-jsx-scope": "off",
        "react/jsx-filename-extension": [
            1,
            {
                "extensions": [".js", ".jsx"]
            }
        ]
    }
}
```

### Prettier
Create .prettierrc
```json
{
    "tabWidth": 4,
    "useTabs": false,
    "semi": true,
    "trailingComma": "all",
    "printWidth": 80,
    "bracketSpacing": true,
    "arrowParens": "always",
    "singleAttributePerLine": true
}
```
### Solving Errors
Before running eslint or prettier you should make sure that you have all the required prettier and eslint dependencies in your package.json.
This is how it should look like
```json
"dependencies": {
        "@babel/core": ">=7.0.0-0 <8.0.0",
        "@babel/plugin-syntax-flow": "^7.14.5",
        "@babel/plugin-transform-react-jsx": "^7.14.9",
        "@emotion/react": "^11.10.5",
        "@emotion/styled": "^11.10.5",
        "@mui/material": "^5.11.6",
        "@reduxjs/toolkit": "^1.9.1",
        "@testing-library/dom": "^8.20.0",
        "@typescript-eslint/eslint-plugin": "^5.13.0",
        "@typescript-eslint/parser": ">=5.0.0 <6.0.0",
        "axios": "^1.2.3",
        "eslint-config-react-app": "^7.0.1",
        "eslint-plugin-import": "^2.27.5",
        "eslint-plugin-jsx-a11y": "^6.5.1",
        "eslint-plugin-react-hooks": "^4.3.0",
        "jest": "^29.4.0",
        "prettier": "^2.8.3",
        "react": "^18.2.0",
        "react-dom": "^18.2.0",
        "react-redux": "^8.0.5",
        "react-router-dom": "^6.7.0",
        "typescript": ">=3.2.1 <4.0.0 || >=4.0.0 <5.0.0"
    },
    "devDependencies": {
        "@types/react": "^18.0.26",
        "@types/react-dom": "^18.0.9",
        "@vitejs/plugin-react-swc": "^3.0.0",
        "eslint": "^8.32.0",
        "eslint-config-airbnb": "^19.0.4",
        "eslint-config-prettier": "^8.6.0",
        "eslint-import-resolver-typescript": "^3.5.3",
        "eslint-plugin-prettier": "^4.2.1",
        "eslint-plugin-react": "^7.32.1",
        "husky": "^8.0.0",
        "react-test-renderer": "^18.2.0",
        "vite": "^4.0.0"
    }
```
Copy paste content and edit it as you wish, then run.
```shell
pnpm i
```
Now you should be able to use Eslint + Prettier to write better code
```shell
eslint .
```

### Integrating with IDE
At this point you have everything you need to start linting&formatting in CLI.
You can install some extensions to integrate this process in your IDE. I use Neovim for building React apps and I've set up autoformatting on-save in my [nvim](https://github.com/dsrcr/nvim) repository. 

### Using git hooks
I'm not using it yet but it seems like a nice feature 

Lot of people on the internet recommended using [Husky](https://typicode.github.io/husky/#/) so I've decided to mention it. 
The following commands are copy-pasted from above link. I prefer the automatic setup.
```bash
pnpm dlx husky-init && pnpm install
```
