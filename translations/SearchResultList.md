# SearchResultList translations

These are the standard phrases for the search result list widgets.

**Translation table: ```SearchResultList```**

| Property | Type | Standard phrase |
|----------|------|-----------------|
| chooseSorting | string | Choose Sorting |
| discountsWithArrival | string | Offers with arrival at {date} |
| noArrivalsOnDateShowsOtherDates | string | No available homes on arrival date. Shows other possible arrival dates. |
| resultsOnOtherArrivalDates | string | Other possible arrival dates |
| showAsList | string | Show as List |
| showOnMap | string | Show on Map |
| sortingPrice | string | Price |
| sortingStandard | string | Default |
| numberOfResultsFound | Pluralizable | { \"one\": \"We have found one vacation home\", \"other\": \"We have found {0} vacation homes\",  } |

### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.