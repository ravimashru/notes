# Extend `Request` type

When using a NestJS app on SAP Cloud Platform (Cloud Foundry) with the UAA service,
details of the logged in user are available at `req.user` (where `req` is the request object from Express).

However, since the type definition of `Request` does not have a `user` property, the TypeScript compiler
doesn't allow us to access it.

To extend the type definition, create a file at `@types/express/index.d.ts` from the root directory of the NestJS app
and add this to the file:

```typescript
declare namespace Express {
  interface Request {
    user: TSFixMe;
  }
}
```
