# TypeScript CheatSheet

Make sure to have Node.js and TypeScript installed:

```sh
sudo apt update && sudo apt upgrade
sudo apt install nodejs
npm install -g typescript@next
```

## Init Project

For creating CLI applications, TypeScript can be really useful.

### Bare CLI Setup

You can init your project with this:

```sh
mkdir project && cd project
npm init
npm install --save-dev typescript @types/node ts-node
npx tsc --init --rootDir src --outDir dist --lib esnext
mkdir src && touch src/index.ts
```

For the available `lib` versions, check the [official documentation][1].

Start your IDE (preferably VScode via `code .`) and add the following scripts to your `package.json` for CLI execution:

```json
"scripts": {
  "start": "ts-node src/index.ts",
  "live": "tsc -w -p ."
}
```

You can now start your TypeScript CLI with:

- `npm run start` - run your tool
- `npm run live` - hot compile all `.ts` files according to your `ts-config.json`

have fun and happy coding!

### React.js & Next.js

for most frameworks a init procedure is available, for example:

```sh
npx create-react-app my-reactjs-app --typescript
npx create-next-app my-nextjs-app --typescript
```

## Handling CLI Input

To accept CLI input, use `yargs`:

```sh
npm install yargs
npm install --save-dev @types/yargs
```

Then use it like this:

```js
// src/index.ts

import yargs from "yargs";

const args = yargs.options({
  "api-key": { type: "string", demandOption: true, alias: "a" },
  url: { type: "string", demandOption: true, alias: "u" },
  instructions: { type: "array", demandOption: true, alias: "i" },
}).argv;

console.log(args);
```

[1]: https://www.typescriptlang.org/tsconfig#lib
