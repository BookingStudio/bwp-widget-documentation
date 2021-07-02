# SearchResultList widget

This widget displays a grid of search results or, in headless mode, provides data for drawing your own custom search results.

## Example 1 (using standard grid rendering)

Search result list using the standard widget rendering of the search results.

```html
<div id="mySearchResults" class="bwp-widget"></div>
<script>
    (function () {
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {
            let props = {
                "lodgingUrlPattern": "/cottages/{lodging:area}/{lodging:name}/",
                "includeLodgingIdInUrl": true,
                "emptyResultHtmlContent": "There no cottages matching your search query. Please try other dates or contact us."
            };
            BookingStudio.show(
                document.getElementById("mySearchResults"),
                "SearchResultList",
                props
            );
        }
    })();
</script>
```

## Example 2 (using headless mode with custom rendering)

Search result list running in headless mode. Results are drawn using custom logic (not shown here).

```html
<div id="customSearchResults"></div>
<div id="mySearchResults" class="bwp-widget"></div>
<script>
    (function () {        
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {
            let props = {
                "lodgingUrlPattern": "/cottages/{lodging:area}/{lodging:name}/",
                "includeLodgingIdInUrl": true,
                "headlessMode": true,
                "headlessDataFormat": "standard"
            };
            BookingStudio.show(
                document.getElementById("mySearchResults"),
                "SearchResultList",
                props
            );
        }

        function createLodgingCard(result) {
            /* TODO: 
             * Add custom drawing logic.
             * Return node or document fragment to be 
             * inserted into the DOM i.e. using the
             * HTML <template> tag.            
             */
        }

        window.addEventListener("BookingStudio:searchResultsUpdated", function (e) {
            const results = e.detail;        
                        
            const container = document.getElementById("customSearchResults");
            const lodgingCards = [];
            results.forEach(function (result) {
                lodgingCards.push(createLodgingCard(result));
            });
            container.replaceChildren(...lodgingCards);
        });
    })();
</script>
```

## Settings

| Property                | Type                    | Description                                              |
|-------------------------|-------------------------|----------------------------------------------------------|
| ```lodgingUrlPattern``` | string | The url for property presentation page. Certain values from the property can be merged into the url. These are ```{lodging:area}```, ```{lodging:name}```, ```{lodging:id}``` and ```{lodging:address}```. The search query will be automatically appended. |
| ```includeLodgingIdInUrl``` | boolean | Set this to true if you want the ```lod=[PROPERTY ID]``` as part of the search query. The default is set to false. |
| ```emptyResultHtmlContent``` | string | HTML to be shown in case the search result is empty. |
| ```defaultOrderBy``` | string | The initial sort order before the user selects a specific sort order. The possible values are ```Random```, ```PriceLowToHigh```, ```PriceHighToLow```, ```Standard```.  |
| ```headlessMode``` | boolean | Set this to true and the widget will not render anything. Instead it will generate an event called ```BookingStudio:searchResultsUpdated``` with the search result data inside. See example. |
| ```headlessDataFormat``` | string | This determines the data included in the event containing the search results. The values are ```simple```, ```standard``` and ```full```. The ```standard``` set of properties is a subset of ```full``` and the ```simple``` set is a subset of ```standard```. |

## Events

To listen for and react to events add an event listener to the ```window``` object on the page.

| Event                   | Event Payload Type      | Description                                              |
|-------------------------|-------------------------|----------------------------------------------------------|
| ```BookingStudio:searchResultsUpdated``` | WidgetSearchResult[] | This event is fired anytime the search results change. The payload is an array of search results. The data included in each search result depends on the ```headlessDataFormat``` prop. It always includes the booking option that best matches the search, the lodging id and the url for the next page (the cottage presentation). |
| ```BookingStudio:numberOfSearchResultsUpdated``` | number | This event is fired anytime the search results change. The payload is just the number of search results found. |

*Example*

```html
<script>
window.addEventListener("BookingStudio:searchResultsUpdated", function(e) {
    let results = e.detail;

    // TODO: Do something with the search results.
});
</script>
```

## Event payload data types

### WidgetSearchResult

A single item in the search result.

| Property | Type | Description |
|----------|------|-------------|
| ```lodging```  | WidgetLodgingFull \| WidgetLodgingSimple | Information about the property (cottage)
| ```selectedBookingOption``` | WidgetBookingOption | Information about the specific stay that was searched for |
| ```url``` | string | The url for the presentation page for this property with the right search context appended |

### WidgetLodgingFull / WidgetLodgingSimple

Information about a single property. How much information is available is determined by the ```headlessDataFormat``` prop.

| Property | Type | Available in data format | Description |
|----------|------|--------------------------|-------------|
| ```id``` | number | *all* | The property id |
| ```name``` | string | *all* | The name of the property |
| ```nameSlug``` | string | *all* | The name of the property suitable for a URL |
| ```longitude``` | number | ```full``` | Geo-coordinate for location of the property |
| ```latitude``` | number | ```full```| Geo-coordinate for location of the property |
| ```address1``` | string | ```full``` | Address of the property |
| ```address1slug``` | string | ```full``` | Address suitable for a URL |
| ```location``` | WidgetLocation | ```full``` and ```standard``` | Object with the name of the location |
| ```maxPeople``` | number | ```full``` and ```standard``` | The max. no. of people that the property can accommodate |
| ```petsAllowed``` | boolean | ```full``` and ```standard``` | True if pets are allowed during the stay |
| ```images``` | WidgetImage[] | ```full``` and ```standard``` | Array of images of the property |
| ```facilityValues``` | WidgetFacilityValue[] | ```full``` and ```standard``` | Array of amenities and their values for the property |
| ```description``` | WidgetDescription | ```full``` and ```standard``` | An object with the title and summary of the property |
| ```stars``` | number | ```full``` and ```standard``` | Rating (i.e. stars 1 to 5) |
| ```starsPostText``` | string | ```full``` and ```standard``` | Rating modifier (i.e. "+") |

### WidgetLocation

Represents a location defined in BookingStudio

| Property | Type | Description |
|----------|------|-------------|
| ```name``` | string | The name of the location |
| ```slug``` | string | The name of the location suitable for a URL |

### WidgetImage 

Represents an image belonging to a property

| Property | Type | Description |
|----------|------|-------------|
| ```url``` | string | The URL of the image. This is the full resolution image that might not be suaitable for direct use. Consider sending through a resizer or online image service. |

### WidgetFacilityValue

Represents a amenity or facility value for a property (i.e. "number of bedrooms" or "swimmingpool").

| Property | Type | Description |
|----------|------|-------------|
| ```facilityId``` | number | The facility id |
| ```facility``` | WidgetFacility | An object with information about the facility |
| ```value``` | string | The raw value as a string |
| ```displayValueAndName``` | string | A formatted string with the value and the name |
| ```displayValue``` | string | A formatted string with the value |

### WidgetFacility

Represents a facility or amenity defined in BookingStudio.

| Property | Type | Description |
|----------|------|-------------|
| ```name``` | string | The facility name |


### WidgetDescription

Represents the texts for a property. 

| Property | Type | Description |
|----------|------|-------------|
| ```title``` | string | The title for the property |
| ```summary``` | string | The short summary for the property |



## Translations

Uses the following translations:

* [SearchResultList](../translations/SearchResultList.md)
* [Favourites](../translations/Favourites.md)
* [LodgingCard](../translations/LodgingCard.md)
