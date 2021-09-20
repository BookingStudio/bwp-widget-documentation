# MultiLodgingCalendar translations

These are the standard phrases for the multi lodging calendar widget.

**Translation table: ```MultiLodgingCalendar```**

| Property | Type | Standard phrase |
|----------|------|-----------------|
| arriveOnDate | string | Arrive on &lt;strong&gt;{0}&lt;/strong&gt; |
| selectYourStay | string | Select your stay |
| noBookingOptionsForSelectedDate | string | There are no available stays starting on this date for this cottage. |
| clickToSeeMoreStays | string | Click here to see more stays |
| day | Pluralizable | { \"one\": \"{0} night\", \"other\": \"{0} nights\",  } |

### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.