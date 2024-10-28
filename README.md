<!-- configure eslint and prettier -->

install these packages : - eslint-config-standard - eslint-plugin-tailwindcss - eslint-config-prettier - prettier
change .eslintrc.json file
{
"extends": ["next/core-web-vitals", "next/typescript", "standard", "plugin:tailwindcss/recommended", "prettier"]
}

integrate eslint and prettier into vscode
create a folder .vscode with settings.json file
{
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true,
"editor.codeActionsOnSave": {
"source.fixAll.eslint": "explicit",
"source.addMissingImports": "explicit"
},
"prettier.tabWidth": 2,
"prettier.useTabs": false,
"prettier.semi": true,
"prettier.singleQuote": false,
"prettier.jsxSingleQuote": false,
"prettier.trailingComma": "es5",
"prettier.arrowParens": "always",
"[json]": {
"editor.defaultFormatter": "esbenp.prettier-vscode"
},
"[typescript]": {
"editor.defaultFormatter": "esbenp.prettier-vscode"
},
"[typescriptreact]": {
"editor.defaultFormatter": "esbenp.prettier-vscode"
},
"[javascriptreact]": {
"editor.defaultFormatter": "esbenp.prettier-vscode"
},
"typescript.tsdk": "node_modules/typescript/lib"
}

- in .eslintrc.json
  {
  "extends": [
  "next/core-web-vitals",
  "next/typescript",
  "standard",
  "plugin:tailwindcss/recommended",
  "prettier"
  ],
  "plugins": ["import"],
  "rules": {
  "import/order": [
  "error",
  {
  "groups": [
  "builtin",
  "external",
  "internal",
  ["parent", "sibling"],
  "index",
  "object"
  ],
  "newlines-between": "always",
  "pathGroups": [
  {
  "pattern": "@app/**",
  "group": "external",
  "position": "after"
  }
  ],
  "pathGroupsExcludedImportTypes": ["builtin"],
  "alphabetize": {
  "order": "asc",
  "caseInsensitive": true
  }
  }
  ]
  }
  }

- npm i eslint-plugin-import --save-dev (for imports)
- install eslint, prettier and prettier ESlint extensions
- Ctrl shift p -> type reload
