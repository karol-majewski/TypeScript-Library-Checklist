# Do not depend on global variables

[Depend on an interface](https://en.wikipedia.org/wiki/Dependency_inversion_principle) instead.

## Example 1

If your library is a wrapper for Web Storage, don't call `window.localStorage` directly.

### Bad

When `localStorage` is unavailable \(think Safari Private Mode on iOS\), this function will throw an exception.

```typescript
function get(key: string): string | null {
  localStorage.get(key);
}
```

### Good

Your consumers must bring their own `Storage` — be it `localStorage`, `sessionStorage` or a custom `Storage`.

```typescript
function get(key: string, storage: Storage): string | null {
  storage.get(key);
}
```

### Good

Your consumers _can_ bring their own `Storage` if they want, and `localStorage` is used by default.

```typescript
function get(key: string, storage: Storage = localStorage): string | null {
  storage.get(key);
}
```

