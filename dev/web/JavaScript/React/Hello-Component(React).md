---
layout: dev
title: Hello-Component(React)
---
앞서 만든 Hello World에 컴포넌트를 적용해서 다시 만든다.

main.js를 다음과 같이 고친다.

## main.js

```javascript
class Hello extends React.Component {
  render() {
    return (
      <h1>Hello {this.props.name}</h1>
    );
  }
}

ReactDOM.render(
  <Hello name="world!"/>,
  document.getElementById('hello')
);
```

웹서버에 올려서 웹브라우저로 확인한다.