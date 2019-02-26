# Keep your dependencies up to date

JavaScript ecosystem is know for its frequent updates. It's even more true for TypeScript, because when the source code of your dependency and its type definitions live in two different places \(DefinitelyTyped\), you can expect them to evolve asynchronously. It's important to make sure _your_ dependencies are well-defined and deterministic in their behavior.

## Saving exact versions

One solution to this problem is to save [exact versions](https://docs.npmjs.com/cli/install) of your dependencies.

```bash
npm install <library-name> --save-exact
```

This will opt-out of the default `npm install` behavior which takes semantic versioning into account. While it makes your builds deterministic, it has a severe disadvantage: it makes it more difficult to reuse already installed packages, since they will rarely match the same version.

## Automatic updates

A better solution is to have a tool like [Greenkeeper](https://greenkeeper.io/) or [Dependabot](https://dependabot.com/) scan the npm registry for updates and open a pull request when they are found. When a dependency from within the desired version range is going to break your build, a pull request with the details will be created for you.

## Manual updates

Greenkeeper and Dependabot are free for open source projects. If your project is private and you are ale looking for a free solution, you can create an npm script running `npx npm-check`.

In your `package.json`, add a script like this one:

```javascript
{
  "scripts": {
    "dependencies:update": "npx npm-check --update"
  }
}
```

Running `npm run dependencies:update` will open an interactive panel in your terminal. Cherry-pick the packages you are interested in and hit Enter to confirm.

