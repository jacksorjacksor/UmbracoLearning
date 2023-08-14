
## appsettings adjustments

Within Umbraco.CMS:

- Runtime.Mode:Development ([docs](https://docs.umbraco.com/umbraco-cms/v/10.latest-lts/fundamentals/setup/server-setup/runtime-modes))

- ModelsBuilder.ModelsMode:SourceCodeManual ([docs](https://docs.umbraco.com/umbraco-cms/v/10.latest-lts/fundamentals/setup/server-setup/runtime-modes))

```json
  "Umbraco": {
    "CMS": {
      "ModelsBuilder": { "ModelsMode": "SourceCodeManual" },
      "Runtime": { "Mode": "Development" },
    }
  }
```

## ModelsBuilder details:

- Specifies how the models builder will generate models and when to generate them.

-- [Default] InMemoryAuto - Models will automatically be generated each time a content type change occurs, and will then be compiled, and loaded into memory dynamically. This means that the models are only available in views, however they will be available instantly.

-- SourceCodeManual - Models will be generated as .cs files whenver a users clicks the "Generate models" button on the models builder dashboard, the models however will not be compiled and loaded into memory dynamically. This means that models are available everywhere, however the project needs to be recompiled and restarted for the new models, or model changes, to take effect.

-- SourceCodeAuto - This mode behaves the same as SourceCodeManual with one difference, the generation of models happens automatically every time a content type change occurs.

## Unattended install

- Only needed first time you set-up a site, can then be removed from appsettings.json (if used)

## dotnet watch

- Can be useful to run the site with Hot Reload enabled, through `dotnet watch run` command.


## Recommended Document Types folder structure

![Alt text](/imgs/DocumentTypesFolders.png)

- Components
- Compositions
- Elements
- Folders
- Pages


## Document Types

- Document Type with Template
  - Data definition for a content page, created by editors in a content tree, has URL, has .cshtml template
- Document Type
  - Same as above, without .cshtml template
- Element Type
  - Schema for repeating sets of properties (i.e. "Block List" or "Nested Content")
- Composition
  - Reusable set of properties for use in other Document types (i.e. "Title", which would then appear on multiple pages)


## Naming practices

- Document Types
  - [Name of page] Page
    - i.e. "Home Page"


