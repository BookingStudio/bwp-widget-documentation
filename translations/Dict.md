# Dict translations

These are standard phrases in general use.

**Translation table: ```Dict```**

| Property | Type | Standard phrase |
|----------|------|-----------------|
| bathroom | Pluralizable | { \"one\": \"bathroom\", \"other\": \"bathrooms\",  } |
| bedroom | Pluralizable | { \"one\": \"bedroom\", \"other\": \"bedrooms\",  } |
| no | string | No |
| yes | string | Yes |

### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.