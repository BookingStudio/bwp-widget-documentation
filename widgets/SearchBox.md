# SearchBox widget

This widget displays a vertical search box used to refine search criteria on search results page.

## Example

Displays a simple search box that allows the user to change their current search criteria on a search result page.

```html
<div id="mySeachBox" class="bwp-widget"></div>
<script>
    (function () {
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {
            let props = {
                "searchBox": {
                    "maxPeople": 10,
                    "maxPets": 2,
                    "durations": [2,3,4,5,6,7,8,9,10,11,12,13,14],
                    "highlightDays": [0,1,5],
                    "locations": [
                        { "text": "All areas", "value": null},
                        { "text": ". London", "value": "8"},
                        { "text": ".. Camden", "value": "3"},
                        { "text": ".. City", "value":"5" },
                        { "text": ".. Westminster", "value":"9" },
                        { "text": ". Berlin", "value":"10" },
                        { "text": ".. Mitte", "value": "11" },
                        { "text": ".. Kreuzberg", "value":"6" },
                        { "text": ".. Charlottenburg", "value": "16" }
                    ]
                }
            };
            BookingStudio.show(
                document.getElementById("mySeachBox"),
                "SearchBox",
                props
            );
        }
    })();
</script>

```

## Screenshot

![SearchBox](https://user-images.githubusercontent.com/18358/124519958-40413380-ddeb-11eb-9e3c-9a5835a08d5f.png)

## Settings

| Property                | Type                    | Description                                              |
|-------------------------|-------------------------|----------------------------------------------------------|
|```searchBox```          | SearchBoxProps          | Object with settings for the search box.                 |

### **SearchBoxProps**

| Property            | Type                    | Description                                              |
|---------------------|-------------------------|----------------------------------------------------------|
|```locations```      | SelectItem[]            | Array of locations for the locations picker.             |
|```durations```      | number[]                | Array of number of nights for the durations picker.      |
|```maxPeople```     | number                  | The max. no. of people allowed for the people picker.    |
|```maxPets```        | number                  | The max. no. of pets allowed for the pet picker.         |
|```highlightDays```  | number[] (optional)     | Array of weekdays to highlight. Sunday is 0, Monday is 1 and so on up to Saturday being 6 |
|```booleanFacilities```  | BooleanFacility[] (optional)     | Array of yes/no facility filters |
|```rangeFacilities```  | RangeFacility[] (optional)     | Array of numeric range facility filters |

### BooleanFacility

Used only for true / false facilities. Puts a checkbox filter in the search box.

| Property           | Type          | Description                     |
|--------------------|---------------|---------------------------------|
| ```facilityId```   | number        | The facility id                 |
| ```displayName```  | string        | The label for yes / no checkbox |

### RangeFacility

Used only for numeric facilities. Puts a range picker in the search box.

| Property          | Type                | Description                     |
|-------------------|---------------------|---------------------------------|
| ```facilityId```        | number              | The facility id                 |
| ```displayName```       | string              | The label for range picker      |
| ```min```               | number              | The minimum value that user can select |
| ```max```               | number              | The maximum value that user can select |
| ```minName```           | string (optional)   | Label for when minimum value is selected |
| ```maxName```           | string (optional)   | Label for when maximum value is selected (i.e. "All") | 


## Translations

Uses the following translations:

* [SearchBox](../translations/SearchBox.md)
* [DatePicker](../translations/DatePicker.md)
