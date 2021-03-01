Chapter 4 - Designing a Schema
==================
GraphQL changes the way that applications are designed.  Instead of looking at your APIs as a collection of REST endpoints, you are going to start to look at your APIs as a collection of types. The blueprint for a GraphQL API is the schema. In this chapter, we'll learn more about GraphQL's type system and schema definition language.

- GraphQL即將改變你的設計程序。你會開始將API視為型態的集合,而不是REST端點的集合。而正式定義這個API將要公開的資料型態的集合稱為**schema**
- schema優先(Schema First)是可讓你的團隊對於組成app的資料型態達成共識的設計方法。後端團隊可藉由它來明確了解他們需要儲存與傳遞的資料。前端團隊可以知道他們開始建構使用者介面時需要的定義
- 為了便於定義型態,GraphQL附有一種定義schema的語言,稱為Schema Definition Language(又稱為SDL)。如同GraphQL Query Language,無論你使用哪種語言或框架來建構app,GraphQL SDL都是一樣的
- GraphQL schema文件是定義可在app中使用的型態之文字文件





Resource Links
------
* [Schema First Development by Danielle Man](https://conferences.oreilly.com/fluent/fl-ca-2017/public/schedule/detail/58715): A great talk about schema first development by Danielle Man from the Apollo team
* [GraphQL Schema Design](https://blog.apollographql.com/graphql-schema-design-building-evolvable-schemas-1501f3c59ed5): A blog article by Marc-Andre Giroux from GitHub about building evolvable schemas
* [Schema Language Cheat Sheet](https://github.com/sogko/graphql-schema-language-cheat-sheet): An overview of the main features in GraphQL schemas. Hang this at your desk! 

### Chapter Examples
* [City to City Through Types - Launchpad](https://launchpad.graphql.com/lk3qk3zq7q): Through types sample on Apollo GraphQL's Launchpad
* [Union Types - Launchpad](https://launchpad.graphql.com/r94qxj5q4n): Union types sample on Launchpad
* [Interfaces - Launchpad](https://launchpad.graphql.com/j8r375km3p): Interfaces sample on Launchpad

