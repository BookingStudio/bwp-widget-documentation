# LodgingBookingBox widget

This widget display a booking box for a single property.

## Example

```html
<div id="myBookingBox"></div>
<script>
    (function() {
        const BookingStudio = window["BookingStudio"];
        if (BookingStudio) {                			
            const props = {
                "searchBoxSettings": {
                    "maxPeople":10,
                    "maxPets":2,
                    "booleanFacilities": [],
                    "rangeFacilities": [],
                    "availableDurations":[2,3,4,5,6,7,8,9,10,11,12,13,14]
                },
                "culture":"en-GB",
                "nextUrl":"https://checkout.bookingstudio.com/grove-cottages/"
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
