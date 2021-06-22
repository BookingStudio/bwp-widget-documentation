# BookingStudio Web Platform Widgets (currently in BETA)

BookingStudio Web Platform (BWP) widgets are a set of widgets that can be used to build online booking websites on top of BookingStudio using any type of content management system such as [Wordpress](https://wordpress.org).

## Table of content

1. Prerequisites
1. Setup
1. 

## Prerequisites 

You need a BookingStudio account with bookable properties. A property is bookable when it has been created with the required contents, prices and availability. If a property is bookable internally in the BookingStudio system and enabled for use on the website, then it should be showing up through the widgets as well.

**AT THE MOMENT YOU NEED TO CONTACT BOOKINGSTUDIO SUPPORT TO ENABLE WIDGETS FOR YOUR SOLUTION.**

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

```
<script>
window["BookingStudio_culture"] = "en-GB";
</script>
```

**BETA SETTINGS**

While this project is in beta you need to set two additional settings:

* ```BookingStudio_remoteApiHost``` - the baseUrl of the api host used by the widgets
* ```BookingStudio_client``` - the widgets installation name used by the widgets

```
<script>
    window["BookingStudio_remoteApiHost"] = "https://bwp.bookingstudio.com";
    window["BookingStudio_client"] = "my-installation-name";
</script>
```

**BookingStudio will provide you with these settings.**

Here is a complete example:

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

## Widgets

The current version contains these widgets:

* [**HeroSearchSearchBox**](./widgets/HeroSearchSearchBox.md) - Displays a frontpage search box