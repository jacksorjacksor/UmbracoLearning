

To use `Where.IsVisible()` in a LINQ query you have to have a bool umbracoNaviHide property:

https://docs.umbraco.com/umbraco-cms/reference/querying/ipublishedcontent/collections#.isvisible


Sample from navigation.cshtml:

```razor
@inherits UmbracoViewPage

@{
    var homePage = Umbraco.AssignedContentItem.AncestorOrSelf<HomePage>();
    var children = homePage?.Children?.Where(x => x.IsVisible()) ?? Enumerable.Empty<IPublishedContent>();
}
```