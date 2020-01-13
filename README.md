# Installation

You need to install the following packages in order to use ebay skin:

```
yarn add @ebay/skin @ebay/browserslist-config
```

## Bundling

We will be loading

### Webpack configuration

yarn add -D less less-loader # Optionally install arc-webpack if you need

Then, in your webpack configuration:

```
module.exports = {
  module: {
    rules: [
      {
        test: /\.less$/,
        loader: 'less-loader', // compiles Less to CSS
      },
    ],
  },
};
```

Optionally, if you also want arc-webpack check https://github.com/eBay/arc/tree/master/packages/arc-webpack

## Usage

```
import "@ebay/skin/button.less";

function App() {
  return (
    <div className="App">
      <button className="btn btn--primary">Button</button>
    </div>
  );
}
```

## Example

If you are using create-react-app then you need to eject it (Unless you want to use customize-cra) and then update the webpack config like:

```
const lessRegex = /\.less$/;
...
...

    module: {
        rules: {
            ...
            {
              test: lessRegex,
              use: getStyleLoaders(
                {
                  importLoaders: 2,
                  sourceMap: isEnvProduction && shouldUseSourceMap
                },
                "less-loader"
              ),
              sideEffects: true
            },
            ...
```
