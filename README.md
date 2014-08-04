# react-layout

Dynamic subview layout for [React](http://facebook.github.io/react/)

### example

```html
React = require('react');
Layout = require('react-layout');

var AppLayout = React.createClass({
  getInitialState: function() {
    return { sidebarWidth: 330 };
  },
  render: function() {
    var regions = this.props.regions;
    var sidebarWidth = this.state.sidebarWidth;

    var scrollable = {
      'overflow-y': 'scroll',
      'overflow-x': 'hidden',
    };

    return (
      <Layout className="app" layoutWidth="inherit" layoutHeight="inherit">
        <Layout className="sidebar" layoutWidth={sidebarWidth} layoutHeight="inherit" style={scrollable}>
          {regions.sidebar}
        </Layout>
        <Layout className="main" layoutWidth="flex" layoutHeight="inherit">
          {regions.main}
        </Layout>
      </Layout>
    );
  },
});
```

