# Chromatic
Explore, visualize, and prototype your UI components.

You can use Chromatic component explorer in your Meteor + React app with meteor add mdg:chromatic. Similar projects built in React are UI Harness(http://www.uiharness.com/) by Phil Cockfield and React Storybook by Arunoda Susiripala (https://github.com/kadirahq/react-storybook).

Meteor guide (https://guide.meteor.com)


## Demo
[![Chromatic demo video](https://raw.githubusercontent.com/meteor/chromatic/dom/more-documentation/thumbnail-video.png)](https://www.youtube.com/watch?v=dlMe7u02m50)

## Usage

```bash
meteor add mdg:chromatic
```
Make Chromatic available at `/styleguide` in your app in development mode:
```js
const {ChromaticExplorer} = Package['mdg:chromatic-explorer'] || {};
```

## Importing Chromatic
Versions 0.0.x of these packages are compatible with Meteor 1.2
```js
const { Chromatic } = Package['mdg:chromatic-api'] || {};
```
Versions 0.1.x are compatible with Meteor 1.3
```js
import { Chromatic } from 'meteor/mdg:chromatic';
```

## Installing Component Explorer
Configure the URL:
```js
import { ChromaticExplorer } from 'meteor/mdg:chromatic';

if (ChromaticExplorer) {
  ChromaticExplorer.configure({ basePath: '/styleguide' });
}
```

## Write Component Specs
=======
```js
import { Chromatic } from 'meteor/mdg:chromatic';

ComponentName = React.createClass({
  // code
});

if (Chromatic) {
  Chromatic.add(ComponentName, {
    specs: [
      new Chromatic.Spec('specName1', { 
        props: {
          // props used by your component
        }
      }),
      new Chromatic.Spec('specName2', {
        props: {
          // props used by your component
        }
      })
    ]
  });
}
```

## Component packages
```bash
mdg:animations
mdg:buttons
mdg:callout
mdg:code-block
mdg:color-grid
mdg:date-components
mdg:form-components
mdg:list
mdg:loading-spinner
mdg:overlays
mdg:sortable
mdg:tooltips
mdg:outlines
```

## Circular references
When extending Chromatic itself you may need to import the API directly to avoid circular references:
```js
import { Chromatic } from 'meteor/mdg:chromatic-api';
```
