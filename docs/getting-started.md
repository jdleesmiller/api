---
title: Getting Started
category: 5d4c940cae4e610060475769
---

<p align="center">
  <img width="400" src="https://raw.githubusercontent.com/readmeio/api/main/docs/images/logo.svg" />
</p>

<p align="center">
  Magical SDK generation from an OpenAPI definition 🪄
</p>

<p align="center">
  <a href="https://npm.im/api"><img src="https://img.shields.io/npm/v/api.svg?style=for-the-badge" alt="NPM Version"></a>
  <a href="https://npm.im/api"><img src="https://img.shields.io/node/v/api.svg?style=for-the-badge" alt="Node Version"></a>
  <a href="https://npm.im/api"><img src="https://img.shields.io/npm/l/api.svg?style=for-the-badge" alt="MIT License"></a>
  <a href="https://github.com/readmeio/api"><img src="https://img.shields.io/github/workflow/status/readmeio/api/CI.svg?style=for-the-badge" alt="Build status"></a>
</p>

`api` is a library that facilitates creating an SDK from an OpenAPI definition. You can use its codegen offering to create an opinionated SDK for TypeScript or JS (+ TypeScript types).

```sh
$ npx api install https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/examples/v3.0/petstore.json
```

```js
const SDK = require('@api/petstore');

const petstore = new SDK();
petstore.listPets().then(res => {
  console.log(`My pets name is ${res[0].name}!`);
});
```

Or you can use it dynamically (though you won't have fancy TypeScript types):

```js
const petstore = require('api')(
  'https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/examples/v3.0/petstore.json'
);

petstore.listPets().then(res => {
  console.log(`My pets name is ${res[0].name}!`);
});
```