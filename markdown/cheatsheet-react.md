# Cheatsheet React

### Components

```jsx
import React from "react";
import ReactDOM from "react-dom";

class Hello extends React.Component {
  render() {
    return <div className="message-box">hello {this.props.name}</div>;
  }
}

const el = document.body;
ReactDOM.render(<Hello name="Carlos" />, el);
```

### Import multiple export

```jsx
import React, { component } from "react";
import ReactDOM from "react-dom";

class Hello extends Component {
  /* ... */
}
```

### Properties

```jsx
<Video fullscreen={true} autoplay={false}/>
render (){
    this.props.fullscreen
    const {fullscreen,autoplay} = this.props
    /*...*/
}
```

- Usar _this.props_ para acceder a propiedades pasadas al componente.

### States

```jsx
constructor(props) {
    super(props);
    this.state = {
        username: undefined
    }
}
this.setState({username: "herculeskan"})

render(){
    this.state.username
    const {username} = this.state
    /*...*/
}
```

use _(this.state)_ para manejar data dinámica.
Con babel puedes usar proposal-class-fields y deshacerse del constructor.

```jsx
class Hello extends Component {
  state = { username: undefined };
  /*...*/
}
```

### Nesting

```jsx
class Info extends Component {
  render() {
    const { avatar, username } = this.props;
    return (
      <div>
        <UserAvatar src={avatar} />
        <UserProfile username={username} />
      </div>
    );
  }
}
```
