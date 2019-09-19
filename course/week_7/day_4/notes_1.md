# Week 7 - Day 3

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK7-DAY4-green)

<img src="https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png" width="100" height="100" /> 

## Using className and styles

[CodeSandbox](https://codesandbox.io/s/css-s3zdn)

[Docs](https://reactjs.org/docs/dom-elements.html#style)

![Image](https://i.imgur.com/m7dxOSQ.png)

```javascript

var style = "class3";
var style2 = "class4";
function App() {
  return (
    <div className="App">
      <div>
        <button style={{ background: "red" }}>ONE</button>
      </div>
      <div>
        <button style={{ background: "blue", fontSize: 30 }}>TWO</button>
      </div>
      <div>
        <button style={{ background: "blue", fontSize: "30px" }}>THREE</button>
      </div>
      <div>
        <button className="class1">FOUR</button>
      </div>
      <div>
        <button className="class1 class2">FIVE</button>
      </div>
      <div>
        <button className={`${style}`}>SIX</button>
      </div>
      <div>
        <button className={`${style} ${style2}`}>SIX</button>
      </div>
    </div>
  );
}
```

CSS FILE:
```css
.App {
  font-family: sans-serif;
  text-align: center;
}

button {
  width: 100px;
  height: 50px;
  margin: 10px;
}

.class1 {
  font-size: 20px;
  background: green;
}

.class2 {
  background: yellow;
  font-weight: bold;
}

.class3 {
  background: gray;
  font-size: 30px;
}

.class4 {
  background: aqua;
}
```

## Handling Props and State

![Props](https://i.imgur.com/8GoGmTa.png)

[CodeSandbox](https://codesandbox.io/s/props-state-child-0tjcv)

Props are read only. If you pass props into your child, and store that information in the state, it will not re-render the app if the the props data change. 

```javascript
// In the example provided you can see that we are passing information
// from 

  render() {
    return (
      <div>
        <Child data={this.state.data} data2={this.data} />
        <button onClick={() => this.addToData()}>Add with setState</button>
        <br /> <br />
        <button onClick={() => this.addToDataWithoutSetState()}>
          Add without setState
        </button>
      </div>
    );

// 
```
