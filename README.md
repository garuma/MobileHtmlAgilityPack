Mobile HtmlAgilityPack
======================

A PCL+Xamarin port of the infamous [HtmlAgilityPack](http://htmlagilitypack.codeplex.com/). The port mainly consisted of removing legacy code and unavailable things like explicit usage of file IO API.

The library targets **Profile 78** which includes:

- Xamarin.Android
- Xamarin.iOS
- .NET Framework 4.5
- Windows Phone 8
- .NET for Windows Store apps

### Usage

Apart from the changes introduced by a blander PCL profile, the API is the same than the official library.

Example usage with the XML to LINQ-inspired API:

``` csharp
var doc = new HtmlDocument ();
doc.LoadHtml (answer);
var div = doc.GetElementById ("content");
var table = div.Element ("table");
return table.Element ("tbody").Elements ("tr").Select (row => {
	var items = row.Elements ("td").ToArray ();
	return new Person {
		FirstName = items[0].InnerText.Trim (),
		LastName = items[1].InnerText.Trim (),
	};
});
```
