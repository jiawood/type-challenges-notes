### 14.First of Array 

infer 指在extends条件语句中待推断的类型变量，以下面的例子来看，在定义U的时候，不知道U是什么类型
```ts
type First<T extends any[]> = T extends [infer U ,...any[]] ? U : never
```

如果T为空就显示类型为never，否则T[0]
```ts
type First<T extends any[]> = T extends [] ? never : T[0]
```

### 18 Length of Tuple
```ts
type Length<T extends any> = T extends { length: infer L } ? L : never;
type length<T extends any> = T['length']
```

### 43 Exclude 
```ts
type Exclude<T,U> = T extends U ? never : T 
```

### 189 Awaited 
```ts
type Awaited<T extends Promise<any>> = T extends Promise<infer R> ? 
  R extends Promise<any> 
  ? Awaited<R> : R 
  : never    
```

### 268 If
```ts
type If<C extends boolean, T, F> = C extends true ? T : F 
```

### 533 Concat 
```ts
type Concat<T extends any[], U extends any[]> = [...T, ...U]
```

### 3057 Push
```ts
type Push<T extends any[], U extends any> = [...T, U]
```

#### 3312 Parameters 
```ts
type MyParameters<T extends (...args: any[]) => any> = T extends (...args: infer R) => any ? R : never 
```