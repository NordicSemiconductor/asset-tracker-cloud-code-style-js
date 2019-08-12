# Bifravst Code Style [![npm version](https://img.shields.io/npm/v/@bifravst/code-style.svg)](https://www.npmjs.com/package/@bifravst/code-style)

[![CircleCI](https://circleci.com/gh/bifravst/code-style/tree/saga.svg?style=svg)](https://circleci.com/gh/bifravst/code-style/tree/saga)
[![Greenkeeper badge](https://badges.greenkeeper.io/bifravst/code-style.svg)](https://greenkeeper.io/)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier/)
[![ESLint: TypeScript](https://img.shields.io/badge/ESLint-TypeScript-blue.svg)](https://github.com/typescript-eslint/typescript-eslint)

Code style definitions for all Bifravst projects.

- ESLint configuration (with
  [TypeScript support](https://github.com/typescript-eslint/typescript-eslint))
- Prettier configuration

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
    "*.ts": [
      "prettier --write",
      "eslint --ext .js,.ts",
      "git add"
    ],
    "*.{md,json,yaml,yml,js}": [
      "prettier --write",
      "git add"
    ]
  }
}
```

Then:

    npm i --save-dev @bifravst/code-style
    cp node_modules/@bifravst/code-style/templates/* ./
    cp node_modules/@bifravst/code-style/templates/.* ./
