# Bootforce
Bootforce lets you embed Bootstrap and JQuery frameworks and libraries into your Visualforce pages, making it easy to build visually striking Salesforce applications.

## What's Included

Bootforce is packaged as a static resource, within which you'll find the following directories and files, logically grouping common resources and providing both compiled and minified variations.

## Directories & Files

```java
bootforce/
    +-- css/
    ¦   +-- bootforce.css
    ¦   +-- bootforce.min.css
    ¦   +-- bootforce-theme.css
    ¦   +-- bootforce-theme.min.css
    +-- fonts/
    ¦   +-- glyphicons-halflings-regular.eot
    ¦   +-- glyphicons-halflings-regular.svg
    ¦   +-- glyphicons-halflings-regular.ttf
    ¦   +-- glyphicons-halflings-regular.woff
    +-- js/
        +-- bootstrap.js
        +-- bootstrap.min.js
        +-- jquery-1.11.1.js
        +-- jquery-1.11.1.min.js
        +-- jquery-2.1.1.js
        +-- jquery-2.1.1.min.js
```

Precompiled files for quick drop-in usage in nearly any Visualforce project. We provide compiled CSS and JS (`bootforce.*`), as well as compiled and minified CSS and JS (`bootforce.min.*`). Fonts from Glyphicons are included, as is the optional Bootstrap theme.

## Basic Template

Copy the Visualforce page below to begin working with minimal Bootstrap functionality.

```HTML
<apex:page docType="html-5.0">
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce.min.css')}"></apex:stylesheet>
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce-theme.min.css')}"></apex:stylesheet>
    <apex:pageMessages></apex:pageMessages>
    <div class="bootforce">
        <!--All content here -->
    </div>
    
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/jquery-2.1.1.min.js')}"></apex:includeScript>
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/bootstrap.min.js')}"></apex:includeScript>
</apex:page>
```

## Template with Glyphicons

Copy the Visualforce page below to begin working with Bootstrap functionality including glyphicons.
```HTML
<apex:page docType="html-5.0">
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce.min.css')}"></apex:stylesheet>
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce-theme.min.css')}"></apex:stylesheet>
<style type="text/css">
/* USING GLYPHS? You need to include these lines in order to display them properly in your Visualforce pages */
/* START: Glyph requirement */
@font-face {
    font-family: 'Glyphicons Halflings';
    src: url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.eot')}');
    src: url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.eot?#iefix')}') format('embedded-opentype'), url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.woff')}') format('woff'), url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.ttf')}') format('truetype'), url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular')}') format('svg');
}
/* END: Glyph requirement */
</style>
    <apex:pageMessages></apex:pageMessages>
    <div class="bootforce">
        <!--All content here -->
    </div>
    
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/jquery-2.1.1.min.js')}"></apex:includeScript>
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/bootstrap.min.js')}"></apex:includeScript>
</apex:page>
```

## Template with Popovers & Tooltips

Copy the Visualforce page below to work with Bootstrap including the ability to use popovers and tooltips.

```
<apex:page docType="html-5.0">
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce.min.css')}"></apex:stylesheet>
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce-theme.min.css')}"></apex:stylesheet>
<script language="JavaScript" type="text/javascript">
$(document).ready(function(){
    //For performance reasons, the Tooltip and Popover data-apis are opt-in, meaning you must initialize them yourself.
    $("[data-toggle=tooltip").tooltip(); //not using tooltips... simply remove this line
    $("[data-toggle=popover").popover(); //not using popovers... simply remove this line
});
</script>
    <apex:pageMessages></apex:pageMessages>
    <div class="bootforce">
        <!--All content here -->
    </div>
    
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/jquery-2.1.1.min.js')}"></apex:includeScript>
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/bootstrap.min.js')}"></apex:includeScript>
</apex:page>
```

## Combined Template

Copy the Visualforce page below to begin working with more advanced Bootstrap functionality.

```
<apex:page docType="html-5.0">
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce.min.css')}"></apex:stylesheet>
    <apex:stylesheet value="{!URLFOR($Resource.bootforce, '/css/bootforce-theme.min.css')}"></apex:stylesheet>
<style type="text/css">
/* USING GLYPHS? You need to include these lines in order to display them properly in your Visualforce pages */
/* START: Glyph requirement */
@font-face {
    font-family: 'Glyphicons Halflings';
    src: url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.eot')}');
    src: url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.eot?#iefix')}') format('embedded-opentype'), url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.woff')}') format('woff'), url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.ttf')}') format('truetype'), url('{!URLFOR($Resource.bootforce, '/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular')}') format('svg');
}
/* END: Glyph requirement */
</style>
<script language="JavaScript" type="text/javascript">
$(document).ready(function(){
    //For performance reasons, the Tooltip and Popover data-apis are opt-in, meaning you must initialize them yourself.
    $("[data-toggle=tooltip").tooltip(); //not using tooltips... simply remove this line
    $("[data-toggle=popover").popover(); //not using popovers... simply remove this line
});
</script>
    <apex:pageMessages></apex:pageMessages>
    <div class="bootforce">
        <!--All content here -->
    </div>
    
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/jquery-2.1.1.min.js')}"></apex:includeScript>
    <apex:includeScript value="{!URLFOR($Resource.bootforce, '/js/bootstrap.min.js')}"></apex:includeScript>
</apex:page>
```

## Designed for Salesforce

Bootforce makes front-end Salesforce development faster and easier. It's made for developers of all skill levels, devices of all shapes, and projects of all sizes.