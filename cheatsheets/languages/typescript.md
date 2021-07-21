# TypeScript CheatSheet

Make sure to have TypeScript installed:

```sh
npm install -g typescript@next
```

## Init Project

You can init your project with this:

```sh
mkdir project && cd project
npm init
npm install --save-dev typescript @types/node ts-node
npx tsc --init --rootDir src --outDir dist --lib es2020
mkdir src && touch src/index.ts
```

Now add this to your `package.json`:

```json
// package.json
...
"scripts": {
  "start": "ts-node src/index.ts"
}
...
```

Start IDE `code .` and let's go!

## CLI Input

To accept CLI input, use `yargs`:

```sh
npm install yargs
npm install --save-dev @types/yargs
```

Then use it like this:

```js
// src/index.ts

import yargs from 'yargs';

const args = yargs.options({
  'api-key': { type: 'string', demandOption: true, alias: 'a' },
  'url': { type: 'string', demandOption: true, alias: 'u' },
  'instructions': { type: 'array', demandOption: true, alias: 'i' },
}).argv;

console.log(args);
```

