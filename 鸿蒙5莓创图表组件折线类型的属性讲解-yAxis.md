Hello everyone, welcome back to the special session on HarmonyOS 5 Meichuang chart components. In this episode, we'll explain the detailed usage of the `xAxis` property in the line chart component. `xAxis` is a crucial configuration object that controls the display and style of the X-axis. Mastering its properties is essential for customizing charts.  


## Basic Properties  

### `type`  
**Function**: Specifies the type of the X-axis.  
**Type**: String  
**Default**: `'data'`  
**Options**: `'data'` (data axis), `'category'` (category axis), `'value'` (numeric axis)  
**Scenario**: Use when explicitly specifying the X-axis type; the default value usually suffices.  
```typescript
xAxis: {
  type: 'data'
}
```  

### `name`  
**Function**: Sets the name of the X-axis.  
**Type**: String  
**Default**: `''` (empty string)  
**Scenario**: Add descriptive text to the X-axis.  
```typescript
xAxis: {
  name: 'Month'
}
```  

### `show`  
**Function**: Controls whether the X-axis is displayed.  
**Type**: Boolean  
**Default**: `true`  
**Scenario**: Set to `false` to hide the X-axis.  
```typescript
xAxis: {
  show: false // Hide the X-axis
}
```  

### `position`  
**Function**: Sets the position of the X-axis.  
**Type**: String  
**Default**: `'bottom'`  
**Options**: `'bottom'` | `'top'`  
**Scenario**: Control whether the X-axis appears at the top or bottom of the chart.  
```typescript
xAxis: {
  position: 'top' // Display X-axis at the top
}
```  

### `nameGap`  
**Function**: Sets the distance between the axis name and the axis line.  
**Type**: Number  
**Default**: `5`  
**Scenario**: Adjust the spacing between the axis name and the axis line.  
```typescript
xAxis: {
  nameGap: 15 // Increase distance between name and axis line
}
```  

### `nameLocation`  
**Function**: Sets the position of the axis name.  
**Type**: String  
**Default**: `'end'`  
**Options**: `'end'` | `'center'` | `'start'`  
**Scenario**: Control whether the axis name appears at the start, center, or end of the axis line.  
```typescript
xAxis: {
  nameLocation: 'center' // Display name centered
}
```  

### `nameTextStyle`  
**Function**: Sets the text style of the axis name.  
**Type**: Object  
**Default**: See sub-properties.  
**Scenario**: Customize the text style of the axis name.  

#### Sub-properties of `nameTextStyle`:  
- **color**: Text color (String, default `'#999'`).  
- **fontSize**: Text size (Number, default `22`).  
- **fontWeight**: Text weight (String, default `'normal'`).  
- **fontFamily**: Font family (String, default `'sans-serif'`).  

```typescript
xAxis: {
  nameTextStyle: {
    color: '#333',
    fontSize: 24,
    fontWeight: 'bold',
    fontFamily: 'Microsoft YaHei'
  }
}
```  


## Data Range Properties  

### `min`  
**Function**: Sets the minimum value of the axis.  
**Type**: String|Number  
**Default**: `null`  
**Scenario**: Force-set the minimum value, overriding automatic calculation.  
```typescript
xAxis: {
  min: 0 // Force start at 0
}
```  

### `max`  
**Function**: Sets the maximum value of the axis.  
**Type**: String|Number  
**Default**: `null`  
**Scenario**: Force-set the maximum value, overriding automatic calculation.  
```typescript
xAxis: {
  max: 100 // Force end at 100
}
```  

### `interval`  
**Function**: Sets the interval between axis ticks.  
**Type**: Number  
**Default**: `null`  
**Scenario**: Force-set the tick interval, overriding automatic calculation.  
```typescript
xAxis: {
  interval: 10 // Show a tick every 10 units
}
```  

### `minInterval`  
**Function**: Sets the minimum interval between axis ticks.  
**Type**: Number  
**Default**: `null`  
**Scenario**: Prevent ticks from being too dense.  
```typescript
xAxis: {
  minInterval: 1 // Minimum interval of 1
}
```  

### `maxInterval`  
**Function**: Sets the maximum interval between axis ticks.  
**Type**: Number  
**Default**: `null`  
**Scenario**: Prevent ticks from being too sparse.  
```typescript
xAxis: {
  maxInterval: 100 // Maximum interval of 100
}
```  

### `boundaryGap`  
**Function**: Sets whether to leave space at both ends of the axis.  
**Type**: Boolean  
**Default**: `null`  
**Scenario**: Control whether data is flush with both ends of the axis.  
```typescript
xAxis: {
  boundaryGap: false // No space, data flush with both ends
}
```  

### `splitNumber`  
**Function**: Sets the number of axis segments.  
**Type**: Number  
**Default**: `5`  
**Scenario**: Control the number of axis ticks.  
```typescript
xAxis: {
  splitNumber: 10 // Divide axis into 10 segments
}
```  


## Axis Line Style Properties  

### `axisLine`  
**Function**: Sets the style of the axis line.  
**Type**: Object  
**Default**: See sub-properties.  
**Scenario**: Customize the display and style of the axis line.  

#### Sub-properties of `axisLine`:  
- **show**: Whether to display the axis line (Boolean, default `true`).  
- **lineStyle**: Axis line style (Object, default see sub-properties).  

##### Sub-properties of `lineStyle`:  
- **color**: Axis line color (String, default `'#DDE2EB'`).  
- **width**: Axis line width (Number, default `1`).  
- **lineDash**: Sets dashed line style (Array, default `null`; e.g., `[5, 5]` for 5px solid + 5px gap).  

```typescript
xAxis: {
  axisLine: {
    show: true,
    lineStyle: {
      color: '#666',
      width: 2,
      lineDash: [5, 3] // Dashed line style
    }
  }
}
```  


## Tick Style Properties  

### `axisTick`  
**Function**: Sets the style of axis ticks.  
**Type**: Object  
**Default**: See sub-properties.  
**Scenario**: Customize the display and style of ticks.  

#### Sub-properties of `axisTick`:  
- **show**: Whether to display ticks (Boolean, default `true`).  
- **lineStyle**: Tick line style (Object, default see sub-properties).  

##### Sub-properties of `lineStyle`:  
- **color**: Tick line color (String, default `'#DDE2EB'`).  
- **width**: Tick line width (Number, default `1`).  
- **lineDash**: Sets dashed line style (Array, default `null`).  
- **interval**: Interval between ticks and labels (Number, default `4`).  
- **length**: Tick line length (Number, default `5`).  

```typescript
xAxis: {
  axisTick: {
    show: true,
    lineStyle: {
      color: '#999',
      width: 1.5
    },
    interval: 8,
    length: 10
  }
}
```  


## Label Style Properties  

### `axisLabel`  
**Function**: Sets the style of axis labels.  
**Type**: Object  
**Default**: See sub-properties.  
**Scenario**: Customize the display and style of labels.  

#### Sub-properties of `axisLabel`:  
- **show**: Whether to display labels (Boolean, default `true`).  
- **formatter**: Label formatting function or string (String|Function, default `null`).  
- **color**: Label text color (String, default `'#999999'`).  
- **fontSize**: Label text size (Number, default `22`).  
- **fontWeight**: Label text weight (Number, default `400`).  
- **fontFamily**: Label text font (String, default `'sans-serif'`).  
- **rotate**: Label rotation angle (Number, default `0`).  
- **interval**: Label display interval (String|Number, default `null`).  
- **width**: Label text width (Number|null, default `null`).  
- **overflow**: Text overflow handling (String, default `'none'`; options: `'none'` | `'truncate'` | `'breakAll'`).  
- **margin**: Distance between label and tick (Number, default `5`).  
- **shadowColor**: Text shadow color (String, default `'rgba(0, 0, 0, 0)'`).  
- **shadowBlur**: Text shadow blur radius (Number, default `0`).  
- **shadowOffsetX**: Text shadow X offset (Number, default `0`).  
- **shadowOffsetY**: Text shadow Y offset (Number, default `0`).  

```typescript
xAxis: {
  axisLabel: {
    show: true,
    formatter: '{value}月', // Add "月" suffix
    color: '#333',
    fontSize: 18,
    fontWeight: 600,
    rotate: 45, // Rotate 45 degrees
    overflow: 'truncate', // Truncate overflow
    margin: 10
  }
}
```  


## Grid Line Properties  

### `splitLine`  
**Function**: Sets the style of axis grid lines.  
**Type**: Object  
**Default**: See sub-properties.  
**Scenario**: Customize the display and style of grid lines.  

#### Sub-properties of `splitLine`:  
- **show**: Whether to display grid lines (Boolean, default `false`).  
- **lineStyle**: Grid line style (Object, default see sub-properties).  

##### Sub-properties of `lineStyle`:  
- **color**: Grid line color (String, default `'#DDE2EB'`).  
- **width**: Grid line width (Number, default `1`).  
- **lineDash**: Sets dashed line style (Array, default `null`).  

```typescript
xAxis: {
  splitLine: {
    show: true,
    lineStyle: {
      color: '#eee',
      width: 1,
      lineDash: [3, 3]
    }
  }
}
```  


## Other Properties  

### `data`  
**Function**: Sets the data for the X-axis.  
**Type**: Array  
**Default**: `[]`  
**Scenario**: Customize data items displayed on the X-axis.  
```typescript
xAxis: {
  data: ['January', 'February', 'March', 'April', 'May']
}
```  

### `rLevel`  
**Function**: Sets the rendering level of the X-axis.  
**Type**: Number  
**Default**: `-20`  
**Scenario**: Control the layer relationship between the X-axis and other elements.  
```typescript
xAxis: {
  rLevel: -10 // Increase rendering level
}
```  

### `animationCurve`  
**Function**: Sets the animation curve for the X-axis.  
**Type**: String  
**Default**: `'easeOutCubic'`  
**Scenario**: Customize the animation effect of the X-axis.  
```typescript
xAxis: {
  animationCurve: 'linear' // Linear animation
}
```  

### `animationFrame`  
**Function**: Sets the animation frame count for the X-axis.  
**Type**: Number  
**Default**: `30`  
**Scenario**: Control animation smoothness.  
```typescript
xAxis: {
  animationFrame: 60 // Smoother animation
}
```  


## Practical Application Case  
The following is a complete X-axis configuration example for a sales data chart:  

```typescript
import { McLineChart, Options } from '@mcui/mccharts'

@Entry
@Component
struct Index {
  @State maxData: number[] = [11, 11, 15, 13, 12, 130, 10]
  
  @State seriesOption: Options = new Options({
    xAxis: {
      type: 'category',
      name: 'Quarterly Sales Data',
      nameGap: 20,
      nameLocation: 'center',
      nameTextStyle: {
        color: '#333',
        fontSize: 24,
        fontWeight: 'bold'
      },
      axisLine: {
        show: true,
        lineStyle: {
          color: '#666',
          width: 2
        }
      },
      axisTick: {
        show: true,
        length: 8,
        lineStyle: {
          color: '#999',
          width: 1.5
        }
      },
      axisLabel: {
        show: true,
        color: '#666',
        fontSize: 18,
        rotate: 0,
        formatter: '{value} Quarter',
        margin: 12
      },
      splitLine: {
        show: false
      },
      data: ['Q1', 'Q2', 'Q3', 'Q4'],
      animationCurve: 'easeOutBack',
      animationFrame: 40
    },
    series: [
      {
        name: 'Quarterly Sales',
        data: this.maxData
      }
    ]
  })
  
  build() {
    Row() {
      McLineChart({
        options: this.seriesOption
      })
    }
    .height('50%')
  }
}
```  

This configuration displays an X-axis with the title "Quarterly Sales Data". Each tick label shows as "Q1 Quarter", "Q2 Quarter", etc. The axis line and ticks have custom styles, and there's a smooth animation effect.  


That's all for this episode. We hope this article helps you fully master the various usages of the `xAxis` property in Meichuang Charts' line chart component. Apply these properties flexibly in your development to create charts that meet your requirements. If you have any questions, feel free to leave a comment!
