# Golem Components
A Library of components for a full fledged Web development

> Golem Components support only for Vue 3.


## Prerequisites

This project requires NodeJS (version 14 or later) and a Vue 3.
[Node](http://nodejs.org/) and [NPM](https://npmjs.org/) are really easy to install.


## Table of contents

- [Project Name](#golem-components)
  - [Prerequisites](#prerequisites)
  - [Table of contents](#table-of-contents)
  - [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Usage](#usage)
    - [Registering with the app](#registering-with-the-app)
  - [Contributing](#contributing)
  - [Authors](#authors)
  - [Built With](#built-with)
  - [License](#license)

## Getting Started

Golem is an awesome library which is at seed level now. The goel is to roll over the web app like a golem to build robust strong components.

## Installation

**BEFORE YOU INSTALL:** please read the [prerequisites](#prerequisites)

Install Golem Components in your application:

Using npm
```sh
$ npm i golem-components
```
Using yarn
```sh
$ yarn add golem-components
```

## Usage

### Registering with the app

main.js
```js 
import GolemComponents from 'golem-components';
import 'golem-components/dist/style.css';

import App from './App.vue';

const app = createApp(App);

app.use(GolemComponents);

app.mount('#app');

```

### Using the components
Just start using the components here and thats it!!!!

App.vue
```html 
<GButton>Click me 🐷</GButton>

<GButton expanded>I am Fat 🐷</GButton>

<GInput />

<GInput placeholder='Secret here!! 🤫' type="password" />
```

## Contributing

1.  Fork it on [github](https://github.com/iamaravinds/golem-components)!
2.  Create your feature branch: `git checkout -b my-new-component`
3.  Add your changes: `git add .`
4.  Commit your changes: `git commit -am 'New component with details'`
5.  Push to the branch: `git push origin my-new-component`
6.  Submit a pull request :sunglasses:
## Authors

* **Aravind S** - *Initial work* - [iamaravinds](https://github.com/iamaravinds)

See also the list of [contributors](https://github.com/iamaravinds/golem-components/graphs/contributors) who participated in this project.
## Built With

* [Vue 3](https://vuejs.org/)
* [Tailwind CSS](https://tailwindcss.com/)
* [VS Code](https://code.visualstudio.com/)
* and Love ❤️

## License
MIT