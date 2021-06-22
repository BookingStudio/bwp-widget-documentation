# BookingStudio Web Platform Widgets (currently in BETA)

BookingStudio Web Platform (BWP) widgets are a set of widgets that can be used to build online booking websites on top of BookingStudio using any type of content management system such as [Wordpress](https://wordpress.org).

## Table of content

1. [Prerequisites](#prerequisites)
1. [Setup](#setup)
1. [Widgets](#widgets)
1. [Hosted checkout](#hosted-checkout)

<a name="prerequisites"></a>
## Prerequisites 

You need a BookingStudio account with bookable properties. A property is bookable when it has been created with the required contents, prices and availability. If a property is bookable internally in the BookingStudio system and enabled for use on the website, then it should be showing up through the widgets as well.

**AT THE MOMENT YOU NEED TO CONTACT BOOKINGSTUDIO SUPPORT TO ENABLE WIDGETS FOR YOUR SOLUTION.**

<a name="setup"></a>
## Setup

Once the widgets are enabled for your BookingStudio account you can include the stylesheet and javascripts needed.

### **The widgets stylesheet**
This stylesheet contains the css used by the widgets.

```
<link href="https://bwp.bookingstudio.com/[YOUR WIDGETS INSTALLATION ID]/widgets.css" rel="stylesheet">
```

### **The widgets javascript**

We provide two javascripts to be included:

1. **Translations** - The default phrases used by the widgets. This file is named ```translations.[culture].js``` where ```[culture]``` can be either ```en-GB```, ```da-DK```, ```de-DE``` or ```sv-SE```. You should include this before the widgets.

2. **Widgets** - The widgets bundle with all available widgets. This file is named ```widgets.js```. 

### *Example*

```
<script src="https://bwp.bookingstudio.com/[YOUR WIDGETS INSTALLATION ID]/translations.en-GB.js"></script>
<script src="https://bwp.bookingstudio.com/[YOUR WIDGETS INSTALLATION ID]/widgets.js"></script>
```

### **Global settings**

You need to set a few global settings that will be used by the widgets.

**Culture**

You need to tell the widgets what culture you want your widgets to follow. The culture determines language for phrases and data and also how numbers and dates are formatted.

To set the culture you need to set a global variable on the ```window``` object like this:

### *Example*

```
<script>
window["BookingStudio_culture"] = "en-GB";
</script>
```

**BETA SETTINGS**

While this project is in beta you need to set two additional settings:

* ```BookingStudio_remoteApiHost``` - the baseUrl of the api host used by the widgets
* ```BookingStudio_client``` - the widgets installation name used by the widgets

### *Example*

```
<script>
    window["BookingStudio_remoteApiHost"] = "https://bwp.bookingstudio.com";
    window["BookingStudio_client"] = "my-installation-name";
</script>
```

**BookingStudio will provide you with these settings.**

Here is a complete example:

### *Example*

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BWP Widgets template</title>
    <link href="https://bwp.bookingstudio.com/your-installation-id/widgets.css" rel="stylesheet">
    <script>
        window["BookingStudio_culture"] = "en-GB";
        window["BookingStudio_remoteApiHost"] = "https://bwp.bookingstudio.com";
        window["BookingStudio_client"] = "YOUR INSTALLATION ID";
    </script>
    <script src="https://bwp.bookingstudio.com/your-installation-id/translations.en-GB.js"></script>
    <script src="https://bwp.bookingstudio.com/your-installation-id/widgets.js"></script>
</head>
<body>
    <!-- Insert your html and widgets here -->
</body>
</html>
```

<a name="widgets"></a>
## Widgets

The current version contains these widgets:

* [**HeroSearchSearchBox**](./widgets/HeroSearchSearchBox.md) - Displays a frontpage search box
* [**LodgingBookingBox**](./widgets/LodgingBookingBox.md) - Displays a booking box on a cottage presentation page

<a name="hosted-checkout"></a>
## Hosted checkout

BookingStudio provides a hosted checkout service. Like with the widgets you will currently need BookingStudio to set it up for you.

Once it is set up, all you need is to link to it with the right set of query string arguments.

### **Base url**

The hosted checkout has a base url of

```https://checkout.bookingstudio.com/[YOUR INSTALLATION ID]/```

### **Required arguments**

| Argument name | Type   | Description | Example |
|---------------|--------|-------------|---------|
|```lod```      | number | The property id | ```lod=1```             |
|```ari```      | date string | The arrival date formatted as MM-DD-YYYY | ```ari=06-25-2021``` |
|```dur```      | number | The of nights for the stay (i.e. 7 for one week) | ```dur=7``` |
|```adu```      | number | The number of adults staying                     | ```adu=2``` |

### **Optional arguments**

| Argument name | Type   | Description | Example | Default value (if omitted) |
|---------------|--------|-------------|---------|----------------------------|
|```chi```      | number | The number of children staying  | ```chi=0```  | 0 |
|```inf```      | number | The number of infants taying    | ```inf=1```  | 0 |
|```pet```      | number | The number of pets coming along | ```pet=0```  | 0 |


### *Example*

```
https://checkout.bookingstudio.com/[YOUR INSTALLATION ID]/?lod=1&ari=06-25-2021&dur=7&adu=2&chi=0&inf=0&pet=0
```

Please note that that ```LodgingBookingBox``` will automatically append the correct query string given the base checkout url ```https://checkout.bookingstudio.com/[YOUR INSTALLATION ID]/```

