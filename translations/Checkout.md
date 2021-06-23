# Checkout translations

These are the standard phrases of the checkout widget.

**Translation table: ```Checkout```**

| Property | Type | Standard phrase |
|----------|------|-----------------|
| address | string | Address |
| adultsAndChildren | string | {0}, {1} |
| allExtrasTotal | string | All Extras Total |
| backToExtras | string | Back to Extras |
| birthyear | string | Birth Year |
| birthyearPlaceholder | string | (for example 1961) |
| book | string | Book |
| bookingLine | string | Home {0} |
| catalogueDescription | string | Please choose below if you would like to receive our catalog. |
| cellphone | string | Cellphone |
| changeItems | string | Change Extras |
| city | string | City |
| communicationFormTitle | string | Communication |
| contactDetailsFormTitle | string | Your Details |
| country | string | Country |
| dateRange | string | {0} to {1} |
| descriptionLastMinute | string | Payment is due soon and you can pay by bank transfer: |
| descriptionWithOneRate | string | You can pay by bank transfer: |
| descriptionWithTwoRates | string | Pay by bank transfer in two payment installments: |
| email | string | E-mail |
| facilityHeadline | string | Facts about the house |
| firstname | string | First Name |
| guestNumber | string | Guest {0} |
| guestsFormAutoFill | string | Fill in the booker's name automatically |
| guestsFormDescription | string | The names of the guests must be filled in in the fields below. |
| guestsFormDescriptionOptional | string | The names of the guests can be filled in in the fields below. |
| guestsFormTitle | string | Guests |
| information | string | Information |
| internet | string | Internet |
| isDueOn | string | due on {0} |
| itemSelectorHeadline | string | Choose Extras |
| lastname | string | Last Name |
| lodgingPrefix | string | House {0} |
| maxPeople | string | Max. {0} persons |
| newslettersDescription | string | Please choose below whether you would like to subscribe to our newsletter. |
| nextStep | string | Next Step |
| notes | string | Notes |
| notesFormTitle | string | Any Comments? |
| payRatesTitle | string | Payment |
| perItem | string | {0} Per  Item |
| petsAllowed | string | Pets allowed |
| petsNotAllowed | string | Pets not allowed |
| postalCode | string | Postal Code |
| priceInformation | string | Price Information |
| rateLabel | string | {0}. Rate |
| reserve | string | Reserve |
| stepDone | string | Completed |
| stepDoneUrlName | string | completed |
| stepExtras | string | Extras |
| stepExtrasUrlName | string | extras |
| stepYourDetails | string | Your Details |
| stepYourDetailsUrlName | string | details |
| streetAndArea | string | {0} - {1} |
| telephone | string | Telephone |
| termsFormClose | string | Close |
| termsFormDescription | string | Read and accept our rental terms. |
| termsFormModelTitle | string | Terms & Conditions |
| termsFormReadTheTerms | string | Read our rental terms |
| termsFormTitle | string | Terms & Conditions |
| termsFormYesIAcceptTheTerms | string | Yes, I have read and accepted the rental conditions |
| thePriceIncludes | string | The Price Includes |
| totalPrice | string | Total Price |
| workPhone | string | Work Phone |
| yourStay | string | Your stay |
| adult | Pluralizable | { \"one\": \"{0} Adult\", \"other\": \"{0} Adults\",  } |
| bathroom | Pluralizable | { \"one\": \"{0} Bathroom\", \"other\": \"{0} Bathrooms\",  } |
| bedroom | Pluralizable | { \"one\": \"{0} Bedroom\", \"other\": \"{0} Bedrooms\",  } |
| child | Pluralizable | { \"one\": \"{0} Child\", \"other\": \"{0} Children\",  } |
| maxPets | Pluralizable | { \"one\": \"Max. 1 pet\", \"other\": \"Max. {0} pets\", \"zero\": \"Pets now allowed\",  } |
| pet | Pluralizable | { \"one\": \"{0} Pet\", \"other\": \"{0} Pets\", \"zero\": \"No Pets\",  } |

### **Pluralizable**

This a simple javascript object with the properties "zero", "one" and "other". Only "other" is required and the others are only there if there is a pluralization rule for that case. The string "{0}" is a placeholder where the number (quantity, amount and so on) is inserted.