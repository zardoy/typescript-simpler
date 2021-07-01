# TypeScript Simpler

> Status: planned

It is like ReScript library, but it designed to work with more popular TypeScript language.

Please, open an issue if you know an alternative to it.

## New syntax

### [n * type]

```diff
-type Vector = [number, number, number];
+type Vector = [3 * number];
```

`updateSetting(...path.split(".") as [3 * string], value)` instead of `updateSetting(...path.split(".") as [string, string, string], value)` and so on

### Object type annotation

```diff
-type Users = { [name: string]: Info };
+type Users = { [name]: Info };
```

Bad (but useful sometimes tho): `Record<string, UserInfo>`
Better: `{ [userId: string]: UserInfo }`
Ideal: `{ [userId]: UserInfo }`

## Type Helpers

Add types in some places for more strict checks.

### Default Type for Catch variables

🔧 defaultTypeInCatchVariables (default: `Error`)

Remember when TypeScript team has [changed the type of](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4-beta/#use-unknown-catch-variables) of variables in catch blocks from `any` to `unknown`? This project, will set type of these variables to `Error`. Just for your convenience, there is no guarantee that 3d party code always would use Error-like classes.

- TODO:
- [ ] Link ESLint rule that disallows throwing non Error classes like `throw "Hey there!"`
