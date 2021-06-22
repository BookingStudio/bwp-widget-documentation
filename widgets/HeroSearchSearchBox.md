# HeroSearchSearchBox

Display a frontpage style search box.

## Example

```html
<div id="mySearchBox" class="bwp-widget"></div>
<script>
    (function() {
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {
            const props = {
                "searchBox": {
                    "searchUrl":"/cottages/available",
                    "locations": [
                        { "text": "All locations", "value": null},
                        { "text": ". London", "value": "8"},
                        { "text": ".. Camden", "value": "3"},
                        { "text": ".. City", "value":"5" },
                        { "text": ".. Westminster", "value":"9" },
                        { "text": ". Berlin", "value":"10" },
                        { "text": ".. Friedrichshain-Kreuzberg", "value": "11" },
                        { "text": ".. Mitte", "value":"6" },
                        { "text": ".. Charlottenburg-Wolmersdorf", "value": "16" }
                    ],
                    "durations": [2,3,4,5,6,7,8,9,10,11,12,13,14,21,28],
                    "maxPersons": 10, 
                    "maxPets": 1,                     
                    "culture":"en-GB",
                    "highlightDays":[5,6]
                },
                "lodgingUrlPattern":"/cottage/{lodging:area}/{lodging:name}/"
            };
            BookingStudio.show(
                document.getElementById("mySearchBox"),
                "HeroSearchSearchBox",
                props
            );
        }
    })();
</script>
```

## Settings

| Property                | Type                    | Description                                              |
|-------------------------|-------------------------|----------------------------------------------------------|
|```searchBox```          | SearchBoxProps          | Object with settings for the search box.                 |
|```lodgingUrlPattern```  | string (optional)       | The url pattern for linking directly to property.        |

### **SearchBoxProps**

| Property            | Type                    | Description                                              |
|---------------------|-------------------------|----------------------------------------------------------|
|```searchUrl```      | string                  | The url of the search result page                        |
|```locations```      | SelectItem[]            | Array of locations for the locations picker.             |
|```durations```      | number[]                | Array of number of nights for the durations picker.      |
|```maxPersons```     | number                  | The max. no. of people allowed for the people picker.    |
|```maxPets```        | number                  | The max. no. of pets allowed for the pet picker.         |
|```culture```        | string                  | Array of number of nights for the durations picker.      |
|```highlightDays```  | number[] (optional)     | Array of number of nights for the durations picker.      |

## Translations

Uses the following translations:

* [SearchBox](../translations/SearchBox.md)
* [DatePicker](../translations/DatePicker.md)