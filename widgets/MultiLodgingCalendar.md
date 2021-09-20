# MultiLodgingCalendar

Displays availability calendars for all lodgings in a list.

## Example

```html
<div id="myMultiCalendar" class="bwp-widget"></div>
<script>
    (function() {
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {
            const props = {
                "defaultMonth": (new Date()).getMonth(),
                "defaultYear": (new Date()).getFullYear(),
                "changeDays": [0,1,5],
                "lodgingUrlPattern": "/cottage/{lodging:name}/", 
                "minimumNights": 2,
                "preferredDurations": [2,3,7],
                "scaffoldLodgings": 30,
                "defaultValues": {
                    "adults": 2,
                    "children": 0,
                    "infants": 0,
                    "pets": 0,
                    "durations": [2,3,4,5,6,7,8,9,10,11,12,13,14]
                }
            };
            BookingStudio.show(
                document.getElementById("myMultiCalendar"),
                "MultiLodgingCalendar",
                props
            );
        }
    })();
</script>
```

## Settings

| Property                | Type                             | Description                                              |
|-------------------------|----------------------------------|----------------------------------------------------------|
|```defaultMonth```          | number                   | The default starting month.                 |
|```defaultYear```          | number                   | The default starting year.                 |
| ```defaultValues```     | SearchContextProps    | Set the initial values for the search box such as arrival date, durations to search for and number of people |
|```lodgingUrlPattern```  | string                | The url pattern for linking directly to the property.        |
|```changeDays```  | number[]                | Array of weekdays to highlight as changeover days (0 = Sunday, 1 = Monday, ... 6 = Saturday)        |
|```minimumNights```  | number (optional)               | Set a minimum number of nights. Setting this will discard stays shorter than the set value minimum nights        |
|```preferredDurations```  | number[] (optional)               | Array for preferred durations to display in the stays popup when a day is clicked. Only 3 stays will be shown and this allows certain stay to be favoured over others.        |
|```scaffoldLodgings```  | number (optional)               | Number of lodging calendars to show while data is being loaded. After the first data has been fetched the lodging count is set by number of lodgings in the data fetched.        |

### **SearchContextProps**

All properties are optional.

| Property            | Type                    |Description                                   |
|---------------------|-------------------------|----------------------------------------------|
| ```durations```      | number[]               | Array of lengths of stay to fetch prices for |
| ```adults```        | number                  | The number of adults selected |
| ```children```      | number                  | The number of children selected |
| ```infants```       | number                  | The number of infants selected |
| ```pets```          | number                  | The number of pets selected |

## Translations

Uses the following translations:

* [MultiLodgingCalendar](../translations/MultiLodgingCalendar.md)
* [DatePicker](../translations/DatePicker.md)
