# Make your public API augmentation-friendly

Once a package is published, its type definitions are often [augmented](https://www.typescriptlang.org/docs/handbook/declaration-merging.html) by the consumers. There are a few reasons for that:

* **Type definitions are not precise enough.** If a public API makes use of broad types \(like `any` or `{}`\), not only does it defeat the purpose of using TypeScript — but it may also conflict with TSLint rules like [`no-unsafe-any`](https://palantir.github.io/tslint/rules/no-unsafe-any/), forcing the consumer to use a type assertion.
* **A new version of TypeScript was released in the meantime.** TypeScript has a relatively short release cycle. When a new feature lands, it can used to get more type safety out of your code.
* **Functionality was added to your library, but its type definitions do not reflect that.** That's often the case when the source code is at least partially created with JavaScript.

By allowing your consumers to augment the type definitions bundled with your package, you can create a safe environment in which everyone can get what they want without being dependent on each other.

What does it mean for a pubic interface to be augmentation friendly?

* Functions and methods are described with interfaces \(_call signatures_\), not function types. This

  makes it possible to add overload definitions for them.

* Type definitions are built of small definitions composed together. It makes it easier to import

  just a small subset of a type definition and reuse it \(instead of having to decompose a big

  definition yourself\).

* If it depends on third party types, ECMAScript import syntax is used instead of

  [triple-slash directives](https://www.typescriptlang.org/docs/handbook/triple-slash-directives.html).

