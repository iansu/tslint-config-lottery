# tslint-config-lottery

TSLint config for Lottery.com projects. Includes configs for frontend and backend projects.

## Usage

Add TSLint and Prettier to your project:

```sh
yarn add --dev tslint
yarn add --dev --exact prettier@1.13.5
```

*It is recommended that you install an exact version of Prettier as they may introduce formatting changes in minor versions.*

Add a `.prettierrc` file to the root of your project with the following:

```json
{
  "printWidth": 100,
  "singleQuote": true
}
```

Add this package to your project:

```sh
yarn add git+https://github.com/autolotto/tslint-config-lottery.git#1.0.0
```

Create a `tslint.json` file in the root of your project with the following:

```json
{
  "extends": "tslint-config-lottery/config-backend"
}
```

*Replace `config-backend` with `config-frontend` for a frontend project.*

Recommended: Create an `.editorconfig` file in the root of your project with the following:

```ini
# http://editorconfig.org
root = true

[*]
charset = utf-8
end_of_line = lf
indent_size = 2
indent_style = space
insert_final_newline = true
max_line_length = 100

[*.md]
max_line_length = 0
trim_trailing_whitespace = false

[COMMIT_EDITMSG]
max_line_length = 0
```