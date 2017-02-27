---
title: Routing
---

Here's how you can add child routes to your app (using React Router):

```js
import Foo from './foo.jsx';

addRoute({
  name: 'foo',
  path: '/foo',
  component: Foo
});
```

If on the other hand you've previously registered a component with `registerComponent`, you can simply specify the `componentName` property instead:

```js
addRoute({
  name: 'foo',
  path: '/',
  componentName: 'Foo'
});
```

Finally, to change the index (`/`) route, you can just do:

```js
addRoute({
  name: 'foo',
  path: '/',
  component: Foo
});
```

For more complex router customizations, you can also disable the `nova:routing` package altogether and replace it with your own React Router code. 

### Using React Router In Your Components

If you need to access router properties (such as the current route, path, or query parameters) inside a component, you'll need to wrap that component with the `withRouter` HoC (higher-order component):

```js
import React, { PropTypes, Component } from 'react';
import { withRouter } from 'react-router'

class SearchForm extends Component{

  render() {
    // this.props.router is accessible
  }
}

export default withRouter(SearchForm);
``` 
