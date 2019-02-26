# Configuration

## Repository contents

- [ ] Your package has a README. Read more at [makeareadme.com](https://www.makeareadme.com/).
- [ ] Your package has a license. Not sure which should you choose? Go to
      [choosealicense.com](https://choosealicense.com/).

## `package.json`

Generate the file by running `npm init` or `yarn init`. Once it's done, make sure:

- [ ] The required fields are present (`name`, `main`, `version`)
- [ ] The `main` field points to an existing file
- [ ] The `types` (or `typings`) field points to a type declaration (`*.d.ts`) file
- [ ] The `typesVersions` field, if used, follows the
      [correct syntax](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-1.html)
- [ ] The `files` field includes your JavaScript artifacts as well as your declaration files
- [ ] A corresponding lockfile (`package-lock.json` or `yarn.lock`) is generated and commited to the
      repository

Read more about `package.json` in the
[official documentation](https://docs.npmjs.com/files/package.json) and
[here](https://github.com/stereobooster/package.json).

## `tsconfig.json`

It's best to create your `tsconfig.json` by running `tsc --init` in your terminal. A configuration
file generated this way makes the decisions explicit, and it also provides comments useful for any
collaborators not familiar with TypeScript.

Once that's done, make sure that:

- [ ] `sourceMap` is set to `true`
- [ ] `declaration` is set to `true`
- [ ] `declarationMap` is set to `true`
- [ ] `removeComments` is set to `false`
- [ ] `strict` is set to `true`
- [ ] `allowSyntheticDefaultImports` is set to `true`
- [ ] `moduleResolution` is set to `"node"`
- [ ] `esModuleInterop` is set to `true`

Read more about
[the options available in `tsconfig.json`.](https://www.typescriptlang.org/docs/handbook/compiler-options.html)
