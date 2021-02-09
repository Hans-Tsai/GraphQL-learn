Chapter 1 - Welcome To GraphQL
==================
GraphQL is a query language for your APIs and a runtime for fulfilling those queries with your data. The GraphQL service is transport agnostic but is typically served over HTTP. Throughout this chapter, we'll introduce GraphQL: its history, its spec, and its architectural differences from other API paradigms like REST and SOAP.


什麼是GraphQL?
------
- GraphQL是供API使用的查詢語言。它也是滿足資料查詢的runtime。GraphQL服務部規定使用哪種傳輸協定,但通常是透過HTTP來提供的
- GraphQL是一種用戶端/伺服器端之間的通訊規格(spec)


GraphQL 的設計準則
------
- 階層式
  + GraphQL query是階層式的,query有一些欄位在其他欄位裡面,且query的外型類似它回傳的資料
- 以產品為中心
  + GraphQL的目的是提供用戶端需要的資料,以及支援用戶端的語言和runtime
- 強型態
  + GraphQL伺服器採取GraphQL型態系統。在schema內,每一個資料點都有一種特定的型態,GraphQL會拿它來驗證資料點
- 由用戶端指定的query
  + GraphQL伺服器提供用戶端可以使用的功能
- 自我查詢
  + GraphQL語言可查詢GraphQL伺服器的型態系統


GraphQL的緣起
------
- 在2012年,Facebook決定重建app的原生行動app,之後由Lee Byron、Nick Schrock、Dan Schafer的團隊決定站在用戶端的角度重新考慮他們的資料,於是他們開始著手建構了GraphQL這個查詢語言,並在2015/07月首次對外發表第一版的GraphQL規格,並推出`graphql.js`
- REST (Representational State Transfer, 表現層狀態轉換)
  + REST是在2000年由Roy Fielding所發表的博士論文中所定義出來的API架構。他描述了一個資源導向的架構,可讓使用者在這個架構中,執行諸如`GET`、`PUT`、`POST`、`DELETE`...等動作來處理網路資源。我們可以將資源組成的網路當成一種虛擬狀態機,而那些REST動作(例: `GET`、`PUT`、`POST`、`DELETE`)是這個機制內的狀態改變


REST的缺陷
------
- 隨著網路的發展,REST在某些狀況下已經顯露一些疲態了,GraphQL正是為了緩解這些疲態而造就的
- REST 常見的缺點
  + OverFetch (過度擷取)
  + UnderFetch (擷取不足)
- 使用GraphQL時,典型的架構只有一個API端點。單一端點可扮演閘道的角色並協調多個資料來源,但就算只有一個端點,我們仍然可以更輕鬆地組織資料
  + 有許多公司都會同時使用GraphQL、REST。設置GraphQL端點來從REST端點擷取資料是完全有效的GraphQL使用方式。因此,在我們的專案中逐漸地使用GraphQL是一種很好的方法
  + 例如: The New York Times、IBM、Twitter、Yelp、Airbnb、GitHub也都有在使用GraphQL


現實世界的GraphQL
------
- 目前全世界有3個以GraphQL為主題的會議
  + 舊金山的GraphQL summit
  + 赫爾辛基的GraphQL Finland
  + 柏林的GraphQL Europe
- 基於GraphQL只是一種"規格"(spec)。它並不在乎與它一起使用的是 React 或是 Vue 或是 Javascript 或甚至是瀏覽器。而該如何設計這些架構就可以由我們自行決定
- GraphQL用戶端
  + GraphQL用戶端旨在加速開發團隊的工作流程,並改善app的效率與性能。它們可處理諸如網路請求、資料快取,以及將資料注入使用者介面等工作
  + 常見的Graph Client有以下2種
    * [Relay.js---The production-ready GraphQL client for React.](https://relay.dev/)
      * Relay是Facebook製作的用戶端,它是與React、React Native一起運作的
      * Relay是React元件與GraphQL伺服器端回傳的資料之間的連接組織
      * Facebook、GitHub、Twitch以及許多其他公司都有在使用Relay
    * [Apollo Client (React)](https://www.apollographql.com/docs/react/)
      * Apollo client是社群團體Meteor Development Group為了建立更全面的GraphQL周邊工具而開發的
      * Apollo client支援所有主要的前端開發平台,而不限定任何特定的框架









Resource Links
------

### GraphQL Official 
* [GraphQL](http://www.graphql.org): The main website for the GraphQL project.
* [GraphQL on GitHub](https://github.com/graphql/): The main GitHub repo for GraphQL's documentation, reference implementation (GraphQL.js), and other related projects
* [GraphQL Spec](http://facebook.github.io/graphql): GraphQL's specification
* [GraphQL Community Resources](https://graphql.org/community/): Links to conference talks, Slack channels, Twitter accounts, blogs, and more, curated by the GraphQL community

### GraphQL APIs
* [GitHub API](https://developer.github.com/v4/): GitHub's public API
* [SWAPI](https://graphql.org/swapi-graphql/): The Star Wars API
* [Public GraphQL APIs](https://graphql.org/community): A list of public APIs that can be queried with GraphQL

### GraphQL Clients
* [Apollo Client](https://www.apollographql.com/docs/react/): The GraphQL client developed by Meteor Development Group
* [Relay](https://facebook.github.io/relay/): Facebook's GraphQL client library
* [urql](https://github.com/FormidableLabs/urql): Formidable Labs's minimal React Query Library

### 補充資料
* [GraphQL Design: 使用 DataLoader 提升效能 !](https://ithelp.ithome.com.tw/articles/10207606)

