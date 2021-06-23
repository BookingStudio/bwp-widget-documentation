# LodgingCard translations

These are the standard phrases for the lodging card widget.

**Translation table: ```LodgingCard```**

| Property | Type | Standard phrase |
|----------|------|-----------------|
| arrival | string | Arrival |
| canBeReserved | string | Can reserve |
| cleaningIncluded | string | Cleaning incl. |
| fromPricePerPeriod | string | From {price} {period} |
| houseNumber | string | House num. |
| imageMissing | string | Updated photos on the way |
| nextImage | string | Next image |
| perDay | string | per day |
| period | string | {from} to {to} |
| perWeek | string | per week |
| petsAllowed | string | Pets allowed |
| petsNotAllowed | string | Pets not allowed |
| previousImage | string | Previous image |
| person | Pluralizable | { \"one\": \"{0} person\", \"other\": \"{0} persons\",  } |

### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.