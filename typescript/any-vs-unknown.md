# `any` vs `unknown`

Both are top types in type hierarchy.

> ... we're allowed to do everything with `any`
>
> ... we're not allowed to do anything with `unknown`


## Example 1

```typescript

function foo(bar: any): string {
    return bar; // Okay - any is assignable to anything
}

function foo(bar: unknown): string {
    return bar; // NOT okay!
}

```

## Example 2

```typescript
let vAny: any = 10;          // We can assign anything to any
let vUnknown: unknown =  10; // We can assign anything to unknown just like any 


let s1: string = vAny;     // Any is assignable to anything 
let s2: string = vUnknown; // Invalid; we can't assign vUnknown to any other type (without an explicit assertion)

vAny.method();     // Ok; anything goes with any
vUnknown.method(); // Not ok; we don't know anything about this variable
```

## References

- Lesson 10: TypeScript in 50 Lessions
- https://stackoverflow.com/questions/51439843/unknown-vs-any
