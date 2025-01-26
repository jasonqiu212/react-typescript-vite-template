# React + TypeScript + Vite

This web app template provides:

- Minimal setup to get React working in Vite
- [ESLint](https://eslint.org/) integrated with [Prettier](https://prettier.io/)

## Getting Started

1. Use this template to create a repository for your new web app.

2. Clone the created repository.

3. Install the packages.

```
npm install
```

4. Configure ESLint and Prettier to your preference. The ESLint configurations are inside `eslint.config.js` and the Prettier configurations are inside `.prettierrc`.

Congratulations! You have successfully initialized the template. 🎉

## Recreating the Template

1. Scaffold a Vite project.

```
npm create vite@latest
```

2. Follow the instructions to create a TypeScript React project.

> [!TIP]
> You can use `.` for the project name to scaffold in the current directory.

3. Install the packages in the created project directory.

```
cd new-project
npm install
```

4. Install [Prettier](https://prettier.io/).

```
npm install --save-dev prettier
```

Prettier helps to format code while ESLint (which comes installed from Step 3) helps with both code formatting and code quality. Hence, we should use Prettier for formatting and ESLint for code quality.

But if both ESLint and Prettier can format code, how do we handle conflicting rules between ESLint and Prettier?

5. Install [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) to turn off ESLint rules that may conflict with Prettier.

```
npm install --save-dev eslint-config-prettier
```

6. Add `eslint-config-prettier` to your ESLint configuration by adding `eslintConfigPrettier` to the `extends` array in the `eslint.config.js`.

7. Install [@trivago/prettier-plugin-sort-imports](https://github.com/trivago/prettier-plugin-sort-imports) to sort imports.

```
npm install --save-dev @trivago/prettier-plugin-sort-imports
```

8. Create a `.prettierrc` file to add Prettier configurations.

```json
{
  "trailingComma": "all",
  "semi": true,
  "singleQuote": true,
  "importOrder": ["^components/(.*)$", "^[./]"],
  "importOrderSeparation": true,
  "importOrderSortSpecifiers": true,
  "plugins": ["@trivago/prettier-plugin-sort-imports"]
}
```

9. Add scripts in `package.json` to format the project using ESLint and Prettier using 1 command: `npm run format`

```json
"scripts": {
  // ...
  "lint:fix": "npm run lint -- --fix",
  "prettier": "prettier . --check",
  "prettier:fix": "npm run prettier -- --write",
  "format": "npm run prettier:fix && npm run lint:fix"
},
```
