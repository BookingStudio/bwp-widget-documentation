# LodgingPage translations

These are the standard phrases for lodging page widgets.

| Property | Type | Standard phrase |
|----------|------|-----------------|
| book | string | Book |
| chooseAnotherArrivalDate | string | Choose Another Arrival Date |
| closeVideo | string | Close |
| lodgingDescription | string | Description |
| lodgingNamePrefix | string | Home |
| noAvailableBookingOption | string | There is nothing available on the selected arrival date. |
| periodPrice | string | Rent {0} to {1} |
| petsAllowed | string | Pets Allowed |
| petsNotAllowed | string | Pets Not Allowed |
| price | string | Price |
| reserve | string | Reserve |
| reviewPeriod | string | Stayed in this vacation home in {0} |
| reviews | string | Reviews |
| showFloorPlan | string | Show Floor Plan |
| showImages | string | Show Images |
| theHouseMayNotBeAvailableForTheSelectedNumberOfPeople | string | The house may not be available for the selected number of people |
| video | string | Video |
| person | Pluralizable | { \"one\": \"{0} person\", \"other\": \"{0} persons\",  } |

### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.