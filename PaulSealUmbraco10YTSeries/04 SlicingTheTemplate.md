
- Templates exist as both files and are registered in the database
- Partial templates only exist as files, not in the database


When making master templates need to be aware of @using specific composition models:

Razor snippet for pulling in partials:
    `@await Html.PartialAsync("~/Views/Partials/NameOfPartial.cshtml")`


.css and .js need leading / added to help deal with different file paths:

`<link href="/css/styles.css" rel="stylesheet"/>`
`<script src="/js/scripts.js"></script>`

### Overview of Umbraco 10 site - v1
Flowchart of site after Paul Seal's "How to build a website with Umbraco 10 - Part 4 - Slicing the Templates"

```mermaid

flowchart TB
    %% Subgraphs

    subgraph "Document Types"
        HomePageDocType["Home Page"]
        ContentPageDocType["Content Page"]

    end
    subgraph "Templates"
    ContentPageTemplate["Content Page"]
        HomePageTemplate["Home Page"]
        MasterPageTemplate["Master Page"]
    end
    subgraph "Compositions"
        HeaderProperties["Header Properties"]
        ContentProperties["Content Properties"]
    end
    subgraph "Partials"
        footer
        header
        metaData
        navBar
    end
    subgraph "Content Tree"
        HomePageNode["Home Page"]
        AboutPageNode["About Page"]
    end

    %% Relationships
    ContentPageTemplate-->MasterPageTemplate
    HomePageTemplate-->MasterPageTemplate
    
    MasterPageTemplate-->footer
    MasterPageTemplate-->header
    MasterPageTemplate-->metaData
    MasterPageTemplate-->navBar

    HomePageDocType-->HomePageTemplate
    ContentPageDocType-->ContentPageTemplate

    HomePageDocType-->HeaderProperties
    ContentPageDocType-->HeaderProperties
    ContentPageDocType-->ContentProperties

    HomePageNode-->HomePageDocType
    AboutPageNode-->ContentPageDocType

    metaData-->HeaderProperties
    header-->HeaderProperties
```