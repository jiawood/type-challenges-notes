### 8. readonly2
```ts
type MyReadonly2<T, K extends keyof T = keyof T> = {
  [Key in keyof T]: T[Key]
} & {
  readonly[Key in K]: T[Key]
}
```