# 🍱 create-store

Tiny ([<300B minified + gzipped](https://bundlephobia.com/result?p=create-store)) state atoms that are updated via reducers.

```js
import createStore from "create-store";

const initialState = { count: 0 };
function reducer(state, action) {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + 1 };
    case "DECREMENT":
      return { count: state.count - 1 };
  }
}
const store = createStore(reducer, initialState);

console.log(store.getState().count); // => 0

store.dispatch({ type: "INCREMENT" });

console.log(store.getState().count); // => 1
```

`create-store` is a lightweight implementation of a [Redux][] store without advanced concepts like middleware.

[![Edit create-store](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/7ylpxm0xn0)

## Installation

```bash
npm install --save create-store
```

## Using With React

The best way to use create-store state atoms with React is to use [useSubstate](https://github.com/philipp-spiess/use-substate). You can find more information in the [README](https://github.com/philipp-spiess/use-substate/blob/master/README.md) of that library.

## Contributing

Every help on this project is greatly appreciated. To get you started, here's a quick guide on how to make good and clean pull-requests:

1.  Create a fork of this [repository](https://github.com/philipp-spiess/create-store), so you can work on your own environment.
2.  Install development dependencies locally:

    ```bash
    git clone git@github.com:<your-github-name>/create-store.git
    cd create-store
    yarn install
    ```

3.  Make changes using your favorite editor.
4.  Commit your changes ([here](https://chris.beams.io/posts/git-commit/) is a wonderful guide on how to make amazing git commits).
5.  After a few seconds, a button to create a pull request should be visible inside the [Pull requests](https://github.com/philipp-spiess/create-store/pulls) section.

## Future Improvements

- [ ] Add Flow and TypeScript types. This is actually very important for this library: Actions must be typed as an enum such that the type system can find out if we use the wrong type.
- [ ] Improve test harness.

## License

[MIT](https://github.com/philipp-spiess/create-store/blob/master/README.md)

[Redux]: https://redux.js.org/introduction
