# react-native-image-progress
*Progress indicator for networked images in React Native*

## Installation

```
npm install --save react-native-image-progress
```

**Note: Progress indicators has been broken out to a separate component; [react-native-progress](https://github.com/oblador/react-native-progress). To use them, please follow installation instructions for that package.**


## Usage

```js
var Image = require('react-native-image-progress');
var ProgressBar = require('react-native-progress/Bar');
<Image 
  source={{ uri: 'http://loremflickr.com/640/480/dog' }} 
  indicator={ProgressBar} 
  style={{
    width: 320, 
    height: 240, 
  }}/>
```

## Properties

Any [`Image` property](http://facebook.github.io/react-native/docs/image.html) and the following:

| Prop | Description | Default |
|---|---|---|
|**`indicator`**|A component to display progress, will be passed a `progress` prop with a number between 0 and 1 and `indeterminate` a boolean wether or not component has started recieveing data.|`ActivityIndicatorIOS`|
|**`indicatorProps`**|An object of props being passed to the `indicator` component. To disable indeterminate state, pass `{indeterminate: false}`.|*None*|
|**`renderIndicator(progress, indeterminate)`**|Function to render your own custom indicator, useful for something very simple. If not, consider breaking it out to a separate component and use `indicator` prop instead.|*None*|
|**`threshold`**|Number of milliseconds after mount to wait before displaying the indicator. Basically a workaround for cached images not to flash a spinner. Set to `0` to disable.|`50`|

Note: `onLoad*` events are bubbled up, so if you wan't to do some custom thing when the image is loaded for example. 

## Demo

![image-progress-demo](https://cloud.githubusercontent.com/assets/378279/10882718/0f33e7b4-813b-11e5-9f6c-90df8b9050b8.gif)

## Example 

Check full example in the `Example` folder. 

### Pie

```js
var Image = require('react-native-image-progress');
var Progress = require('react-native-progress');
<Image 
  source={{ uri: 'http://loremflickr.com/640/480/dog' }} 
  indicator={Progress.Pie}
  indicatorProps={{
    size: 80,
    borderWidth: 0,
    color: 'rgba(150, 150, 150, 1)',
    unfilledColor: 'rgba(200, 200, 200, 0.2)'
  }}
  style={{
    width: 320,
    height: 240,
  }}/>
```


## License

[MIT License](http://opensource.org/licenses/mit-license.html). © Joel Arvidsson

