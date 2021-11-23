### 14.First of Array 

infer 指在extends条件语句中待推断的类型变量，以下面的例子来看，在定义U的时候，不知道U是什么类型
```ts
type First<T extends any[]> = T extends [infer U ,...any[]] ? U : never
```

如果T为空就显示类型为never，否则T[0]
```ts
type First<T extends any[]> = T extends [] ? never : T[0]
```