Chapter 3 - The GraphQL Language
==================
In this chapter, we'll start writing GraphQL queries using the GraphQL query language. The query string syntax is consistent for all GraphQL APIs, regardless of what language the service is written in. Throughout this chapter, we'll explore the ins-and-outs of the query language and how a GraphQL operation is parsed by a GraphQL server.


GraphQL 查詢語言
----
- SQL(Structured Query Language)是結構化查詢語言,是用來存取、管理與操作資料庫內資料的領域專用語言
  + SQL可執行的指令相當簡單: `SELECT`、`INSERT`、`UPDATE`、`DELETE`,你只能對資料做這些事情
  + 使用SQL時,我們可以編寫一條查詢指令來取得在資料庫的資料表內互相連接的資料
  + REST架構就是基於以上4種基本的資料操作方法來使用不同的HTTP方法: `GET`、`POST`、`PUT`、`PUT`。但是,如果你想要指定用REST來讀取或改變哪一種類型的資料,唯一的方式就是透過端點URL,不能用實際的查詢語言
- GraphQL將原本用來查詢資料庫的概念應用在網際網路上。我們只要用一個GraphQL query就可以回傳彼此相連的資料
- GraphQL有三種主要類型
  + `query`
  + `mutation`
  + `subscription`
- SQL與GraphQL都是查詢語言,但它們完全不同。它們適用於完全不同的環境
  + **SQL query是傳給資料庫的,而GraphQL query是傳給API的**
  + SQL資料存放在資料表內,而GraphQL資料可存放在任何地方: 資料庫、多個資料庫、檔案系統、REST API、WebSocket,甚至是其它的GraphQL API
  + GraphQL與SQL的語法也完全不同。GraphQL使用`Query`來請求資料,而不是SELECT,這項操作是GraphQL完成每項工作的核心
    * GraphQL將所有的資料改變都包裝成一種型態: `Mutation`,而不是使用`INSERT`、`UPDATE`、`DELETE`
    * 因為GraphQL是讓網際網路所使用的,它有一種Subscription型態可用來監聽通訊端連結上的資料變動; 而在SQL並沒有類似訂閱的東西
  + 結論: SQL是資料庫的查詢語言,而GraphQL是網際網路的查詢語言
- GraphQL是按照規格來標準化的。無論你使用哪一種程式語言都可以實作
  + 其實`query`只是放在POST請求的內文中送給GraphQL端點的字串
  + 下面是一個GraphQL query,它是用GraphQL查詢語言寫成的字串
    * ```javascript
        {
          allLifts {
            name
          }
        }
      ```
    * 也可以在終端機透過`curl`指令直接發送這個POST請求給GraphQL伺服器,來收到一個JSON回應
    * ```console
        curl 'http://snowtooth.herokuapp.com/' -H 'Content-Type: application/json' --data '{"query":"{ allLifts { name }}"}'
      ```
  + 若要修改資料,你可以傳送mutation(變動)。`Mutation`的目的是改變關於app整體狀態的事物。我們可以使用mutation直接傳送執行改變所需的資料
    * 範例: 若我們希望用mutation來將id為panorama的纜椅改為open狀態
      * ```javascript
          mutation {
            setLiftStatus(id: "panorama" status: OPEN) {
              name
              status
            }
          }
          ```
      * 我們一樣可以用`curl`指令將這項操作傳送給GraphQL伺服器
      * ```console
          curl 'http://snowtooth.herokuapp.com' -H 'Content-type: application/json' --data '{"query":"mutation {setLiftStatus(id: \"panorama\" status: OPEN) {name status}}"}'
        ```


GraphQL API 工具
----
- GraphQL社群建立了一些可用來和GraphQL API互動的開放原始碼工具。這些工具可讓你用GraphQL查詢語言來編寫query、將這些query送到GraphQL端點,以及查看JSON回應
- 接下來將介紹2種可對著GraphQL API測試GraphQL query的熱門工具
  + [GraphiQL](https://www.electronjs.org/apps/graphiql)
    * GraphiQL是Facebook建造的瀏覽器內部整合式開發環境(IDE),可用來查詢與瀏覽GraphQL API
    * 有許多的公用API都有提供GraphiQL介面以供查詢即時資料
    * ![GraphiQL介面](./GraphiQL介面.png)
      * GraphiQL的操作介面非常簡單,裡面有一個可讓你編寫`query` or `mutation` or `subscription`的面板、一個用來執行它的播放按鈕,以及一個顯示回應的面板。當按下Play按鈕來執行這個查詢之後,我們就會在右側面板上收到一個JSON格式的回應
      * 我們也可以點開右上角的Docs視窗,它裡面定義了與目前的服務互動時需要知道的每一件事。這個文件是自動被加入GraphiQL的,因為它是從服務(daemon)的schema讀出來的。schema定義了服務可提供的資料,而GraphiQL會對schema執行一個自我查詢來自動建構文件
      * 我們通常會用提供GraphQL 
  + [GraphQL Playground](https://www.apollographql.com/docs/apollo-server/testing/graphql-playground/)
    * 




Resource Links
----

### Query Language Tools
* [GraphiQL](https://github.com/graphql/graphiql): An in-browser IDE for exploring GraphQL APIs.
* [GraphQL Playground](https://github.com/prismagraphql/graphql-playground): A GraphQL IDE for writing queries in the GraphQL Query Language.
* [GraphQL Bin](https://www.graphqlbin.com/v2/new): An online version of GraphQL Playground. Simply enter a GraphQL endpoint, and all of the schema documentation will be present in the `schema` tab. 
* [GraphQL Bin - SWAPI](https://www.graphqlbin.com/RVIn): This link takes you to a SWAPI example in GraphQL Bin.
* [Apollo Launchpad](https://launchpad.graphql.com/new): Apollo's GraphQL Server demo platform
* [什麼是REST? 認識 RESTful API 路由語義化設計風格](https://tw.alphacamp.co/blog/rest-restful-api)
* [[筆記] REST 到底是什麼?](https://medium.com/@jinghua.shih/%E7%AD%86%E8%A8%98-rest-%E5%88%B0%E5%BA%95%E6%98%AF%E4%BB%80%E9%BA%BC-170ad2b45836)
* [Linux Curl Command 指令與基本操作入門教學](https://blog.techbridge.cc/2019/02/01/linux-curl-command-tutorial/)

### Chapter Examples
* [Snowtooth API](http://snowtooth.moonhighway.com): The Snowtooth Mountain GraphQL API
* [Union Types](https://codesandbox.io/s/72kppqr7kq?fontsize=14): Union types sample 
* [Interfaces](https://codesandbox.io/s/p79k2n635x?fontsize=14): Interfaces sample 
