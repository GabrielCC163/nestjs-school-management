# Steps to GraphQL Playground

GraphQL

Requirements: graphql, graphql-tools, apollo-server-express @nestjs/graphql

1. Create a lesson module (nest g module lesson), lesson.type.ts (just like a schema FOR GRAPHQL) and a lesson.resolver.ts (handle requests just like a controller)
2. Create a QUERY in the resolver.
3. Import the resolver into the lesson.module.ts file
4. Start the application (npm run start:dev)
5. Go to http://localhost:3000/graphql
6. Create a query and run it

```
query {
  lesson {
    name
    startDate
  }
}
```

MongoDB

Requirements: typeorm @nestjs/typeorm mongodb @types/mongodb

1. Set up the TypeORM into "imports" in the app.module.ts (forRoot)
2. Create the lesson.entity.ts (FOR MONGODB) and set it into "imports > entities array".
3. Create a MUTATION in the resolver, but set the database transactions into a lesson.service.ts file (nest g service lesson --no-spec).
4. Set up the TypeORM into "imports" in the lesson.module.ts (forFeature) \*When it goes inside sub folders, then it must be "forFeature" instead of "forRoot".
5. Create a mutation

```
mutation {
  createLesson (
    name:"Physics Class",
    startDate: "2020-03-28T18:00:00Z",
    endDate: "2020-03-28T18:30:00Z"
  ) {
  name
}
}
```
