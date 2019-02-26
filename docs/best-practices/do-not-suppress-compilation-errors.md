# Do not suppress compilation errors

Using `// @ts-ignore` comments in your source is a serious code smell. Not only does it hide
ugliness, but it can also break your consumers' code when the `--removeComments` compiler flag is
turned on, because stripping these comments will uncover compilation errors in your package.
