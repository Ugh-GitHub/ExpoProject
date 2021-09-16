https://cheesecakelabs.com/blog/efficient-way-structure-react-native-projects/

Structure Overview

├── src
│   ├── assets
│   │  ├── fonts
│   │  ├── images
│   ├── components
│   │  ├── atoms
│   │  ├── molecules
│   │  ├── organisms
│   ├── navigations
│   │  ├── index.js            // RootNavigator
│   │  ├── auth-navigator.js   // AuthNavigator
│   │  ├── app-navigator.js    // AppNavigator
│   ├── scenes
│   │  ├── login
│   │  │	 ├── index.js // LoginScreen
│   │  ├── home
│   │  │	 ├── index.js // HomeScreen
│   │  ├── about
│   │  │	 ├── index.js // AboutScreen
│   ├── styles
│   │  ├── index.js        // Export all
│   │  ├── colors.js       // Colors pallet
│   │  ├── mixins.js       // Mixins to use CSSinJS
│   │  ├── spacing.js      // Paddings, margins and scale
│   │  ├── typography.js   // Fonts types and sizes
│   ├── utils
│   ├── index.js

Steps:
1. $ yarn add -D eslint-import-resolver-babel-module@^5.1.0
eslint-plugin-import@^2.18.2 babel-plugin-module-resolver@^3.2.0

# Note: : investigate the packages and find the node installs#

2. Edit the *.babelrc* & *.eslintrc.js*

3. Create the *jsconfig.json* file and use the same alias defined in *.babelrc*

```
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "_assets": ["src/assets/*"],
      "_components": ["src/components/*"],
      "_atoms": ["src/components/atoms/*"],
      "_molecules": ["src/components/molecules/*"],
      "_organisms": ["src/components/organisms/*"],
      "_navigations": ["src/navigations/*"],
      "_scenes": ["src/scenes/*"],
      "_services": ["src/services/*"],
      "_styles": ["src/styles/*"],
      "_utils": ["src/utils/*"]
    }
  }
}
```

4. Add a test component (example below) in *src/index.js*

```javascript
import React from 'react';
import {View,Text} from 'react-native';

const App = () => (
  <View>
    <Text>Hello World</Text>
  </View>
);

export default App;
```

5. Import the App component.
```javascript
import App from './src';
```

6. Setup the *index.js* files in the *atoms*, *molecules*, *organisms*, *login*, *home*, *about*

Key terms:
* pillars:  
* Atoms:        Smallest possible components, such as buttons, titles, inputs, or even color pallets, animations, and fonts.
* Molecules:    Compositions of one or more components of atoms.
* Organisms:    Combination of molecules that work together or groups of atoms in more elaborate interfaces.
* Templates:    Special component that acts like a placeholder to render a uniform looking page across all the application.
* Pages:        Specific iteration of a specific template with corresponding components. Connected with the whole app
* Styles:       stylistic files
* Services:     Commonly used to create services that make contact with external APIs and use the axios library
* Navigations:  https://reactnavigation.org/docs/getting-started/
* Utils:        Reusable methods, hooks, etc. that can be shared across the entire project.

Also useful:
https://cheesecakelabs.com/blog/atomic-design-react/

https://medium.com/engineering-zemoso/atomic-design-in-react-react-native-using-a-theming-library-part-1-4fc2e0e2ccc8



markdown tutorial
https://guides.github.com/features/mastering-markdown/

It's very easy to make some words **bold** and other words *italic* with Markdown. You can even [link to Google!](http://google.com)

Sometimes you want numbered lists:

1. One
2. Two
3. Three

Sometimes you want bullet points:

* Start a line with a star
* Profit!

Alternatively,

- Dashes work just as well
- And if you have sub points, put two spaces before the dash or star:
  - Like this
  - And this

If you want to embed images, this is how you do it:

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)

# Structured documents

Sometimes it's useful to have different levels of headings to structure your documents. Start lines with a `#` to create headings. Multiple `##` in a row denote smaller heading sizes.

### This is a third-tier heading

You can use one `#` all the way up to `######` six for different heading sizes.

If you'd like to quote someone, use the > character before the line:

> Coffee. The finest organic suspension ever devised... I beat the Borg with it.
> - Captain Janeway

There are many different ways to style code with GitHub's markdown. If you have inline code blocks, wrap them in backticks: `var example = true`.  If you've got a longer block of code, you can indent with four spaces:

    if (isAwesome){
      return true
    }

GitHub also supports something called code fencing, which allows for multiple lines without indentation:

```
if (isAwesome){
  return true
}
```

And if you'd like to use syntax highlighting, include the language:

```javascript
if (isAwesome){
  return true
}
```

GitHub supports many extras in Markdown that help you reference and link to people. If you ever want to direct a comment at someone, you can prefix their name with an @ symbol: Hey @kneath — love your sweater!

But I have to admit, tasks lists are my favorite:

- [x] This is a complete item
- [ ] This is an incomplete item

When you include a task list in the first comment of an Issue, you will see a helpful progress bar in your list of issues. It works in Pull Requests, too!

And, of course emoji!