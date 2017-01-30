React is a JavaScript library for building user interfaces.

Inside ReactSettings.js in /node_modules/react/lib, you will find a setting for enabling strict propTypes by default.

This setting can be overrided on a per component bases by adding the strictPropTypes static variable to your react component classes:

```jsx
export default MyComponent {
  render() {
    return <span>my component value: {this.props.value}</span>
  }
  
  static strictPropTypes = false;
  
  static propTypes = {
    value: React.PropTypes.string.isRequired
  };
}
```

When a component is in strictPropTypes mode, it will throw errors instead of console warnings when proptypes do not match props.  It will also through an error if you pass in a prop that does not have a propType definition.

This feature will only be applied in development mode.  If node.env is set to production it will be ignored.