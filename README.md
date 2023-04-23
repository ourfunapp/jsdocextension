# jsdocextension

> A simple extension for JSDoc that adds the ability to use category and subcategory tags in documentation. It also makes slight modifications to the default HTML template.

## Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Category Plugin](#category-plugin)
- [HTML Template](#html-template)
- [About](#about)

## Installation

JSDoc 3.6 or higher is a peer dependency and is required to utilize this extension.

To install run:

```
npm install git@github.com:ourfunapp/jsdocextension.git
```

## Configuration

In your jsdoc config file (ex. 'jsdoc.conf.json') update the following:

```
{
  "plugins": [
    "node_modules/jsdocextension/plugins/categoryPlugin"   // if you wish to use category plugin
    ],
  "tags": {
    "allowUnkownTags": true, // if you wish to use category plugin
  }
  "opts": {
    "template": "node_modules/jsdocextension/extendedDefaultTemplate"
  }
  ""
}
```

## Category Plugin

The "categoryPlugin" allows you to nest your documentation into categories and subcategories in the sidebar menu.
This is functionality is inspired by and based off the category functionality of the [better-docs](https://github.com/SoftwareBrothers/better-docs) package.

Use `@category` and `@subcategory` in your JSDoc comments as below:

```

/**
* Description of a function
*
* @param {string} myParam Very concise description
* @returns {boolean} Returns the truth
* @async
* @memberof module:crudService
* @category MyFeature
* @subcategory Services
*/
const createService = async (myParam) => {
  ...
}

```

## HTML Template

The template included is a modified version of the default template.

Major differences include:

- Categories and subcategories in the navbar

#### Template configuration options

The template allows for the following configuration options:

- option

The following default template options are also applicable and/or impact the template:

- cleverLinks
- monospaceLinks
- useLongnameInNav
- outputSourceFiles

To set these configuration update your jsdoc config file. Below is an example:

```
{
  "opts": {
    "template": "node_modules/jsdocextension/extendedDefaultTemplate"
  },
  "templates": {
    "cleverLinks": false,
    "monospaceLinks": false,
    "search": true,
    "default": {
      "useLongnameInNav": true,
      "outputSourceFiles": true
    }
    "extendedTemplate": {

    }

  }
}
```

## About

**Version:** 1.0.0
**License:** MIT
