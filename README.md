# tslint-config-lottery

TSLint config for Lottery.com projects. Includes configs for frontend and backend projects.

## Usage

1. Add this package to your project:

```sh
yarn add git+https://github.com/autolotto/tslint-config-lottery.git#1.0.0
```

1. Create a `tslint.json` file in the root of your project with the following:

```json
{
  "extends": "tslint-config-lottery/config-backend"
}
```

Replace `config-backend` with `config-frontend` for a frontend project.
