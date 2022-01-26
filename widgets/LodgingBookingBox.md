# LodgingBookingBox widget

This widget display a booking box for a single property.

## Example

Shows the lodging booking box for the property with id 12, allowing max 10 people and max 2 pets.

```html
<div id="myBookingBox"></div>
<script>
    (function() {
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {                            			
            const props = {
                "searchBoxSettings": {
                    "availableDurations":[2,3,4,5,6,7,8,9,10,11,12,13,14],
                    "maxPeople":10,
                    "maxPets":2
                },
                "nextUrl":"https://checkout.bookingstudio.com/[YOUR INSTALLATION ID/",
                "presets": {
                    "lodgingId": 12
                },
                "defaultValues": {
                    "arrival": "06-30-2021",
                    "duration": 7,
                    "adults": 2
                },
                "showInfants": false
            };
            
            BookingStudio.show(
                document.getElementById("myBookingBox"),
                "LodgingBookingBox",
                props
            );
        }
    })();
</script>
```
## Screenshot

![LodgingBookingBox](https://user-images.githubusercontent.com/18358/123067415-43aee500-d411-11eb-9738-e2b559a5ff6d.png)

## Settings

| Property                | Type                    | Description                                              |
|-------------------------|-------------------------|----------------------------------------------------------|
| ```defaultValues``` | SearchContextProps | Set the initial values for the lodging booking box such as arrival date, duration and number of people |
| ```nextUrl``` | string | The url for the checkout page |
| ```presets``` | SearchContextProps | Set the context for the lodging booking box such as which property to show the box for |
| ```searchBoxSettings``` | SearchBoxSettings | The settings used by the search engine for the booking box |
| ```showInfants``` | boolean | If set to true, the guest can select number of infants in the people selector |

### **SearchBoxSettings**

| Property            | Type                    | Description                                              |
|---------------------|-------------------------|----------------------------------------------------------|
|```availableDurations```      | number[]                | Array of number of nights for the durations picker.      |
|```maxPeople```      | number                  | The max. no. of people allowed for the people picker.    |
|```maxPets```        | number                  | The max. no. of pets allowed for the pet picker.         |

### **SearchContextProps**

All properties are optional.

| Property            | Type                    | Description                                              |
|---------------------|-------------------------|----------------------------------------------------------|
| ```adults```        | number                  | The initial number of adults selected |
| ```arrival```       | string                  | The initial arrival date for the box in the format MM-dd-yyyy |
| ```children```      | number                  | The initial number of children selected |
| ```duration```      | number                  | The initial length of stay selected |
| ```infants```       | number                  | The initial number of infants selected |
| ```lodgingId```     | number                  | Id of the property to show the booking box for           |
| ```pets```          | number                  | The initial number of pets selected |

## Translations

Uses the following translations:

* [LodgingPage](../translations/LodgingPage.md)
* [SearchBox](../translations/SearchBox.md)
* [DatePicker](../translations/DatePicker.md)
