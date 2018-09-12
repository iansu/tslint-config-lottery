# tslint-config-lottery

This is the official TSLint config for Lottery.com. Includes configs for frontend and backend projects.

## Usage

### Install Package

```sh
yarn add --dev tslint-config-lottery
```

### Install Peer Dependencies

```sh
yarn add --dev tslint lint-staged husky
yarn add --dev --exact prettier@1.13.5
```

*It is recommended that you install an exact version of Prettier as they may introduce formatting changes in minor versions.*

### Add TSLint Config File

Add `tslint.json` to project root:

```json
{
  "extends": "tslint-config-lottery/config-backend"
}
```

*Replace `config-backend` with `config-frontend` for a frontend project.*

### Add Prettier Config File

Add `.prettierrc` to project root:

```json
{
  "printWidth": 120,
  "singleQuote": true
}
```

Optional: If there are any files you want to exclude from Prettier add `.prettierignore` to project root.

### Add Editorconfig File

Recommended: Add `.editorconfig` to project root:

```ini
# http://editorconfig.org
root = true

[*]
charset = utf-8
end_of_line = lf
indent_size = 2
indent_style = space
insert_final_newline = true
max_line_length = 120

[*.md]
max_line_length = 0
trim_trailing_whitespace = false

[COMMIT_EDITMSG]
max_line_length = 0
```

### Add Scripts

Add scripts for linting and formatting to `package.json`:

```json
scripts: {
  "precommit": "lint-staged",
  "lint": "tslint -p tsconfig.json -c tslint.json",
  "format:all": "prettier --write \"**/*.{ts,js,json,graphql}\"",
  "format:check": "prettier --debug-check \"**/*.{ts,js,json,graphql}\"",
}
```

### Add Precommit Hook

Add a precommit hook to `package.json` to automatically lint and format any files staged for commit:

```json
"lint-staged": {
  "concurrent": false,
  "linters": {
    "*.ts": [
      "tslint -p tsconfig.json -c tslint.json",
      "git add"
    ],
    "*.{ts,js,json,graphql}": [
      "prettier --write",
      "git add"
    ]
  }
}
```