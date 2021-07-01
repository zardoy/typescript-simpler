# TypeScript Simpler

> Status: planned

It is like ReScript library, but it designed to work with more popular TypeScript language.

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

