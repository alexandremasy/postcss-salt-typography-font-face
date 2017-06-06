# [WIP] Salt - Typography Importer

> Declare and import your fonts automatically. This plugin is part of [Salt](https://github.com/alexandremasy/salt), a collection of tool to help you enforce a set of rule througout your application.



## Getting started

Installation is as easy as:

```shell
npm install postcss-salt-typography-importer
```



**PostCSS**

Include the plugin in you build process:

```
@TODO

```

**Gulp**

Include the plugin in your build process:

```
@TODO
```



This plugins depends on :

- [PostCSS](https://github.com/postcss/postcss)





## Functionalities

Once your have provided your [font definition](https://github.com/alexandremasy/postcss-salt-typography#configuration), we'll generate the appropriate @font-face rules.

We'll handle:

- [Local fonts](#local): Font from the local system of the user;
- [Hosted font](#self-hosted): Self hosted from your own server;
- [Google Font](#google-font)
- [Adobe Typekit](#adobe-typekit)

------



## Configuration

### Local

**CSS**

```css
*>font{
  name: heading;
  family: Roboto;
  fallback: Arial, Helvetica;
  typefaces: regular local('Roboto-Regular'), bold local;
}
```



**JSON**

```json
{
  name: "heading",
  family: "Roboto",
  fallback: "Arial, Helvetica",
  typefaces:[
    "regular local('Roboto-Regular')",
    "bold local"
  ]
}
```



**Yield**

```css
@font-face{
  font-family: Roboto Arial Helvetica;
  font-weight: 400;
  font-style: normal;
  
  src: local('Roboto-Regular');
}

@font-face{
  font-family: Roboto Arial Helvetica;
  font-weight: 600;
}
```



------



### Self hosted

**CSS configuration** 

```css
*>font{
  name: heading;
  family: Roboto;
  fallback: Arial, Helvetica;
  typefaces: regular url('/path/to/your/font/Roboto-Regular'), 
    		bold url('/path/to/your/font/Roboto-Bold');
}
```



**JSON configuration**

```json
{
  name: "heading",
  family: "Roboto",
  fallback: "Arial, Helvetica",
  typefaces:[
    "regular url('/path/to/your/font/Roboto-Regular')",
    "bold url('/path/to/your/font/Roboto-Regular')"
  ]
}
```



**Yield**

```css
@font-face{
  font-family: Roboto Arial Helvetica;
  font-weight: 400;
  font-style: normal;
  
  src: local('Roboto-Regular');
  src: url("Roboto-Regular.eot");
  src: url("Roboto-Regular.eot?#iefix") format("embedded-opentype"),
    url("Roboto-Regular.woff") format("woff"),
    url("Roboto-Regular.ttf") format("truetype"),
    url("Roboto-Regular.svg") format("svg");
}

@font-face{
  font-family: Roboto Arial Helvetica;
  font-weight: 600;
  
  src: local('Roboto-Bold');
  src: url("Roboto-Bold.eot");
  src: url("Roboto-Bold.eot?#iefix") format("embedded-opentype"),
    url("Roboto-Bold.woff") format("woff"),
    url("Roboto-Bold.ttf") format("truetype"),
    url("Roboto-Bold.svg") format("svg");
}
```



#### Font Format

Use the `format` property.

```css
*>font{
  name: heading;
  family: Roboto;
  fallback: Arial, Helvetica;
  format: eot, woff, ttf, svg;
  typefaces: regular url('/path/to/your/font/Roboto-Regular'), 
    		bold url('/path/to/your/font/Roboto-Bold');
}
```





------



### Google Font

@TODO



------



### Adobe Typekit

@TODO
