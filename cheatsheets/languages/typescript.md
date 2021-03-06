# TypeScript

| Official documentation | <https://www.typescriptlang.org/docs/> |
| ---------------------- | -------------------------------------- |

Make sure to have Node.js, TypeScript, and some essential linting and styling tools installed:

```sh
# node
sudo apt update && sudo apt upgrade
sudo apt install nodejs

# typescript
npm install -g typescript@next

# linting/styling
npm install -g prettier eslint
```

## Init Project

### Bare CLI Setup

For creating plain CLI applications, TypeScript can be really useful.
You can init your project with this:

```sh
mkdir project && cd project

# npm setup
npm init
npm install --save-dev typescript @types/node ts-node

# ts setup
npx tsc --init --rootDir src --outDir dist --lib esnext
mkdir src && touch src/index.ts
```

For the available `lib` versions, check the [official documentation][tsconfig-lib].

For the linting/styling part, add the following packages:

```sh
npm install --save-dev eslint-config-airbnb eslint-config-prettier eslint-plugin-prettier
touch .eslintrc.json .prettierrc
```

Now start your IDE (preferably VScode via `code .`).
For linting setup add the following lines to your `.eslint.json`:

```json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": ["error"]
  }
}
```

Your `.prettierrc` should look like this:

```json
{
  "arrowParens": true,
  "bracketSameLine": false,
  "bracketSpacing": true,
  "endOfLine": "auto",
  "jsxSingleQuote": false,
  "printWidth": 120,
  "quoteProps": "as-needed",
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "all",
  "useTabs": false
}
```

All the options are described [here][prettier-options].

Add some start scripts to your `package.json` for CLI execution:

```json
"scripts": {
  "start": "ts-node src/index.ts",
  "live": "tsc -w -p ."
}
```

You can now start your TypeScript CLI with:

- `npm run start` - run your tool
- `npm run live` - hot compile all `.ts` files according to your `ts-config.json` (probably output in `./dist`)
- `node dist/index.js` - run your main file from the output folder

### React.js & Next.js

For React and Next an official init procedure is available:

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

[tsconfig-lib]: https://www.typescriptlang.org/tsconfig#lib
[prettier-options]: https://prettier.io/docs/en/options.html
