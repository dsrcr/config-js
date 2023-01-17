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
> Pull required deps
```bash
pnpm add @babel/core@">=7.0.0-0 <8.0.0" @babel/plugin-syntax-flow@^7.14.5 @babel/plugin-transform-react-jsx@^7.14.9 @testing-library/dom@>=7.21.4 @typescript-eslint/eslint-plugin@^5.13.0 @typescript-eslint/parser@">=5.0.0 <6.0.0" typescript@">=3.2.1 <4.0.0 || >=4.0.0 <5.0.0"
```
> Pull dev deps

```bash
pnpm i --save-dev prettier eslint-config-prettier eslint-plugin-prettier eslint-config-airbnb-typescript eslint-plugin-import@">=2.25.3 <3.0.0" eslint@">=7.32.0 <8.0.0 || >=8.2.0 <9.0.0"
```

### Eslint
> Run this and follow the instructions to generate .eslint.json
```bash
pnpm create @eslint/config
```
> ***[ Important ]*** Make sure eslint works
```bash
eslint .
```

> Replace .eslint.json with this
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
> Create .prettierrc
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
> Now you should be able to use Eslint + Prettier to write better code

### Integrating with IDE

> At this point you have everything you need to start linting&formatting in CLI.
You can install some extensions to integrate this process in your IDE. I use Neovim for building React apps and I've set up autoformatting on-save in my [nvim](https://github.com/dsrcr/nvim) repository. 

### Using git hooks

> I'm not using it yet but it seems like a nice feature 

Lot of people on the internet recommended using [Husky](https://typicode.github.io/husky/#/) so I've decided to mention it. 
The following commands are copy-pasted from above link. I prefer the automatic setup.
```bash
pnpm dlx husky-init && pnpm install
```


