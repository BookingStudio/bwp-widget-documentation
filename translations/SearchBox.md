# SearchBox translations

These are the standard phrases of the search box widgets.

| Property | Type | Standard phrase  |
| ---------|------|----------------- |
| adult | Pluralizable | { "one": "{0} Adult", "other": "{0} Adults" } |
| adults | string | Adults |
| advancedSearchText | string | Show more search options |
| allLocations | string | All locations |
| arrivalLabel | string | Arrival |
| children | string | Children |
| chooseAdditionalFilters | string | Select additional filters for the search result |
| chooseFilters | string | Choose Filters |
| chooseSorting | string | Sorting of the search results |
| durationLabel | string | Duration |
| enterLodgingId | string | Enter the catalogue number of the house |
| loadingData | string | Loading data ... |
| locationLabel | string | Location |
| noLodgingsMatch | string | No lodgings match your search |
| personsLabel | string | Persons |
| petsLabel | string | Pets |
| petsNotAllowed | string | Not allowed |
| petsNotImportant | string | Not important |
| searchAvailableLodgings | string | Search available |
| searchButtonText | string | Search |
| searchLodging | string | Find specific house |
| setFilter | string | Set filter |
| sortingHelp | string | Here you can select the order in which the holiday homes are displayed. |
| sortingLabel | string | Select the sort order |
| child | Pluralizable | { "one": "{0} Child", "other": "{0} Children",  } |
| day | Pluralizable | { "one": "{0} day", "other": "{0} days",  } |
| person | Pluralizable | { "one": "{0} person", "other": "{0} persons",  } |
| pet | Pluralizable | { "one": "{0} pet", "other": "{0} pets",  } |
| sort | Options | { "price": "Price", "standard": "Standard",  } |
| week | Pluralizable | { "one": "{0} week", "other": "{0} weeks",  } |


### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.

### **Options**

This is a simple javascript object where the keys of the object are the values of options in a select box with the corresponding values.