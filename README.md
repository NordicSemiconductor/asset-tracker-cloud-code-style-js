# Bifravst Code Style [![npm version](https://img.shields.io/npm/v/@bifravst/code-style.svg)](https://www.npmjs.com/package/@bifravst/code-style)

[![GitHub Actions](https://github.com/bifravst/code-style/workflows/Semantic%20Release/badge.svg)](https://github.com/bifravst/code-style/actions)
[![Known Vulnerabilities](https://snyk.io/test/github/bifravst/code-style/badge.svg)](https://snyk.io/test/github/bifravst/code-style)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![Mergify Status](https://img.shields.io/endpoint.svg?url=https://dashboard.mergify.io/badges/bifravst/athena-helpers&style=flat)](https://mergify.io)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier/)
[![ESLint: TypeScript](https://img.shields.io/badge/ESLint-TypeScript-blue.svg)](https://github.com/typescript-eslint/typescript-eslint)

Code style definitions for all Bifravst projects.

- ESLint configuration (with
  [TypeScript support](https://github.com/typescript-eslint/typescript-eslint))
- Prettier configuration

## Installation

    npm i --save-dev @bifravst/code-style

## Usage

Update your `package.json`:

```json
{
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.{ts,tsx}": ["prettier --write", "eslint --ext .js,.ts", "git add"],
    "*.{md,json,yaml,yml,js}": ["prettier --write", "git add"]
  }
}
```

Then:

    npm i --save-dev @bifravst/code-style
    cp node_modules/@bifravst/code-style/templates/* ./
    cp node_modules/@bifravst/code-style/templates/.* ./

## Use with React

    npm install eslint-plugin-react --save-dev

Use this `.eslintrc`

```json
{
  "extends": ["@bifravst/eslint-config-typescript", "plugin:react/recommended"],
  "settings": {
    "react": {
      "version": "latest"
    }
  }
}
```

`tsconfig.json`:

```json
{
  "extends": "@bifravst/code-style/tsconfig.json",
  "include": ["src/*.tsx", "src/*.ts"],
  "exclude": ["src/*.spec.ts"],
  "compilerOptions": {
    "outDir": "dist/",
    "jsx": "react",
    "lib": ["DOM", "ES5"],
    "target": "es2018",
    "esModuleInterop": true
  }
}
```

## Use with Creat React App

Use this `.eslintrc`

```json
{
  "extends": ["@bifravst/eslint-config-typescript", "react-app"]
}
```

    npm i --save-dev babel-eslint@10.0.2 eslint-config-react-app@5.0.1 eslint-plugin-flowtype@4.2.0 eslint-plugin-import@2.18.2 eslint-plugin-jsx-a11y@6.2.3 eslint-plugin-react@7.14.3 eslint-plugin-react-app@6.0.0 eslint-plugin-react-hooks@1.7.0

Do not use `tsconfig.json` from code-style.

## Migrating to @bifravst/code-style

For converting projects to use _code-style_:

    npm uninstall --save --save-dev @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-prettier lint-staged prettier semantic-release @bifravst/code-style tslint lint-staged prettier typescript
