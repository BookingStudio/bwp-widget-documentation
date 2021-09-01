# HeroSearchSearchBox

Displays a frontpage style search box.

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
                    "highlightDays":[0,1,5]
                },
                "lodgingUrlPattern":"/cottage/{lodging:area}/{lodging:name}/",
                "defaultValues": {
                    "duration": 2
                }
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

## Screenshot

![HeroSearchSearchBox](https://user-images.githubusercontent.com/18358/123077021-f5eaaa80-d419-11eb-9382-3e99d7ba4168.png)


## Settings

| Property                | Type                             | Description                                              |
|-------------------------|----------------------------------|----------------------------------------------------------|
|```searchBox```          | SearchBoxProps                   | Object with settings for the search box.                 |
|```lodgingUrlPattern```  | string (optional)                | The url pattern for linking directly to property.        |
| ```defaultValues```     | SearchContextProps (optional)    | Set the initial values for the search box such as arrival date, duration and number of people |

### **SearchBoxProps**

| Property            | Type                    | Description                                              |
|---------------------|-------------------------|----------------------------------------------------------|
|```searchUrl```      | string                  | The url of the search result page                        |
|```locations```      | SelectItem[]            | Array of locations for the locations picker.             |
|```durations```      | number[]                | Array of number of nights for the durations picker.      |
|```maxPeople```     | number                  | The max. no. of people allowed for the people picker.    |
|```maxPets```        | number                  | The max. no. of pets allowed for the pet picker.         |
|```highlightDays```  | number[] (optional)     | Array of weekdays to highlight. Sunday is 0, Monday is 1 and so on up to Saturday being 6 |

### **SearchContextProps**

All properties are optional.

| Property            | Type                    | Description                                              |
|---------------------|-------------------------|----------------------------------------------------------|
| ```adults```        | number                  | The initial number of adults selected |
| ```arrival```       | string                  | The initial arrival date for the box in the format MM-dd-yyyy |
| ```children```      | number                  | The initial number of children selected |
| ```duration```      | number                  | The initial length of stay selected |
| ```infants```       | number                  | The initial number of infants selected |
| ```pets```          | number                  | The initial number of pets selected |

### **SelectItem**

This is a simple javascript object with two properties ```text``` for the display value and ```value``` for the selected value.

*Example*
```javascript
// SelectItem object
let item = {
    "text": "The display value",
    "value": "42"
};
```

## Translations

Uses the following translations:

* [SearchBox](../translations/SearchBox.md)
* [DatePicker](../translations/DatePicker.md)
