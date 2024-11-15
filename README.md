# NPM module `@babbel/stylelint-config`

Hierarchical Stylelint configuration collection that intends to be simple to use, layered, and shared with others [[maintainers]](/config/github/codeOwners)

## Stylelint Configurations

If you're unfamiliar with [Stylelint](https://stylelint.io), it works similarly to [ESLint](https://eslint.org) with some minor but unique changes in configuration syntax. You can read more about those [differences here](https://stylelint.io/user-guide/configure).

There are multiple configurations you can use in your projects listed below. Please note that the base configuration is used by all the others, so there's no need to include that in your configuration unless it's the only one you're using.

The configuration names specified below should be used as items in the `extends` array in your Stylelint configuration file. Each configuration string is clickable to bring you to the configuration details.

- [`@babbel/stylelint-config`](./lib/stylelintBaseConfig.json): base configuration that all configurations inherit from
- [`@babbel/stylelint-config/css`](./lib/stylelintCssConfig.json): for pure CSS-based stylesheets
- [`@babbel/stylelint-config/css-modules`](./lib/stylelintCssModulesConfig.json): for CSS module-based stylesheets
- [`@babbel/stylelint-config/scss`](./lib/stylelintScssConfig.json): for SCSS-based stylesheets
- [`@babbel/stylelint-config/scss-modules`](./lib/stylelintScssModulesConfig.json): for SCSS module-based stylesheets
- [`@babbel/stylelint-config/styled-components`](./lib/stylelintStyledComponentsConfig.json): for styled-components

## Configuration Assumptions

- Similar to Prettier, these configurations are highly-opinionated, but unlike Prettier they are all customizable
  - This is meant to minimize decision paralysis and promote a common baseline
- Modern, performant features are enforced
- Browser incompatibilities are proactively avoided if you use [browserslist](https://github.com/browserslist/browserslist) with your project

## Example Usage

Here are a few common use cases to get you familiar with using this collection. The following examples should be added to the `.stylelintrc.json` file at the root of your repository.

### CSS-based Stylesheets

```jsonc
{ "extends": "@babbel/stylelint-config/css" }
```

Yep. That's it. 😀

Or if you want to add some custom rules:

```jsonc
{
  "extends": "@babbel/stylelint-config/css",
  "rules": {
    /* add your custom rules here */
  },
}
```

### CSS Module-based Stylesheets

```jsonc
{ "extends": "@babbel/stylelint-config/css-modules" }
```

I think you're getting the hang of it now...

### SCSS-based Stylesheets and a Custom Rule

```jsonc
{
  "extends": "@babbel/stylelint-config/scss",
  "rules": {
    "custom-property-pattern": "[a-z]+[a-zA-Z]*",
  },
}
```

## Making Your Own Config From the Base Config 🎓

```jsonc
{
  "extends": "@babbel/stylelint-config",
  "rules": {
    /* add all your custom rules here */
  },
}
```

The config export `@babbel/stylelint-config` maps to the base config file `lib/stylelintBaseConfig.json`. You can see how this works by looking for the `"."` entry in the `exports` section of `package.json`; that section defines all the config exports rather than using proxy files such as `index.js` at the root of the repository.

For example, if you want to add an export called `@babbel/stylelint-config/example`, you would do the following:

- Create a new Stylelint configuration file called `./lib/stylelintExampleConfig.json` and set your preferred settings within.
- For the `/example` package export to work, add a new entry in the `"exports"` section in `package.json`:

```jsonc
{
  "exports": {
    /* ... */
    "example": "./lib/stylelintExampleConfig.json",
    /* ... */
  },
}
```

- File a pull request. Be sure to at least extend from `lib/stylelintBaseConfig.json` or one of the more specific configs, otherwise the addition of your contribution to the project may be delayed.

## Final Thoughts

These are just a few examples. Any configuration option in any Stylelint configuration can be overridden, so you can customize these as much as you want. If you find yourself or your team using a configuration set over and over again, consider submitting it to make it part of this collection.

## Feedback Encouraged 🙂

If you have any suggestions for improvements, please send them our way. We're interested in your ideas. 📫
