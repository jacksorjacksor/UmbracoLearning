## Referencing compositions on Razor (.cshtml) pages

Is there a `@Model` attribute which recognises if a property comes from a Composition?

Example:
- Composition: "Header", has property "Title"

- Document Type: "MainPage", uses "Header" composition

When editing MainPage.cshtml, the "Header" composition's "Title" field is referenced as 

`@Model.Title`

Is there a way to reference the composition explicitly in your code, i.e.

`@Model.Header.Title`

Or to somehow display that "Title" belongs to the namespace of "Header"


