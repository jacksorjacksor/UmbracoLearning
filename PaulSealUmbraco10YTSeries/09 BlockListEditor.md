


[Content Grid](https://docs.umbraco.com/umbraco-cms/v/10.latest-lts/fundamentals/backoffice/property-editors/built-in-umbraco-property-editors/grid-layout) -> [Block Grid](https://docs.umbraco.com/umbraco-cms/v/10.latest-lts/fundamentals/backoffice/property-editors/built-in-umbraco-property-editors/block-editor/block-grid-editor)


## Order of creation

1. Document Types>Elements>Content Blocks>Content Models>[Element]"Rich Text Row"
   - Create

2. Data Types>[Data Type]"[BlockList] Main Content"
   - Create
   - Holds the available blocks (i.e. "Rich Text Row")

3. Document Types>Compositions>[Composition]"Content Properties"
   - Add "[BlockList] Main Content" DT

Means all [Pages] which inherit [Composition]"Content Properties"