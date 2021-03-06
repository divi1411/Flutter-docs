---
layout: post
title: Syncfusion Flutter Chart legend
description: Learn how to configure the legend and customize the appearance of its element in SfCartesian charts.
platform: flutter
control: Chart
documentation: ug
---

# Legend in Cartesian charts

The [`legend`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/SfCartesianChart/legend.html) contains list of chart series/data points in chart. The information provided in each legend item helps to identify the corresponding data series in chart.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
              child:SfCartesianChart(
                // Enables the legend
                legend: Legend(isVisible: true),
                series: <LineSeries>[
                  LineSeries<ChartData, String>(
                    dataSource: chartData,
                    xValueMapper: (ChartData data, _) => data.x,
                    yValueMapper: (ChartData data, _) => data.y
                  )
                ]
              )
            )
          )
        );
      }

{% endhighlight %}

![Legend](images/legend/legend.png)

## Customizing legend 

The [`name`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/CartesianSeries/name.html) property of [`CartesianSeries`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/CartesianSeries-class.html) is used to define the label for the corresponding series legend item .The appearance of the label can be customized using the below properties.
* [`borderWidth`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/borderWidth.html) - used to change the stroke width of the legend shape.
* [`borderColor`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/borderColor.html) - used to change the stroke color of the legend shape.
* [`backgroundColor`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/backgroundColor.html) - used to change the background color of legend shape.
* [`opacity`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/opacity.html) - used to control the transparency of the legend icon shape.
* [`padding`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/padding.html) - used to add padding between the icon shape and the text.
* [`iconHeight`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/iconHeight.html) - used to change the height of the icon shape.
* [`iconWidth`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/iconWidth.html) - used to change the width of the icon shape.
* [`borderWidth`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/borderWidth.html) - used to change the stroke width of the legend icon shape.
* [`iconBorderColor`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/iconBorderColor.html) - used to change the stroke color of the legend icon shape.
* [`itemPadding`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/itemPadding.html) - used to add padding between the first legend text and the second legend icon shape.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child:SfCartesianChart(
              legend: Legend(
                isVisible: true,
                name:legend,
                // Border color and border width of legend
                borderColor: Colors.black,
                borderWidth: 2
              ),
              series: <CartesianSeries>[
                LineSeries<ChartData, String>(
                  name:'line-series',
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

![Customized Legend](images/legend/customized_legend.png)

## Legend title

The following properties are used to define and customize the [`title`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/title.html) of [`legend`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/SfCartesianChart/legend.html).

* [`text`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/LegendTitle/text.html) - used to change the text of the title.
* [`textStyle`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/textStyle.html) - used to change the text color, size, font family, fontStyle, and font weight.
* [`textStyle.color`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/ChartTextStyle/color.html) - used to change the color of the text.
* [`textStyle.fontFamily`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/ChartTextStyle/fontFamily.html) - used to change the font family for legend text. 
* [`textStyle.fontStyle`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/ChartTextStyle/fontStyle.html) - used to change the font style for the legend text.
* [`textStyle.fontSize`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/ChartTextStyle/fontSize.html) - used to change the font size for the legend text.
* [`alignment`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/alignment.html) - used to change the alignment of the title text; it can be near, center, or far.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
            child: Container(
                child:SfCartesianChart(
                legend: Legend(
                    isVisible: true,
                    // Legend title
                    title: LegendTitle(
                      text:'Country',
                      textStyle: ChartTextStyle(
                      color: Colors.red,
                      fontSize: 15,
                      fontStyle: FontStyle.italic,
                      fontWeight: FontWeight.w900
                    )
                  ),
                series: <CartesianSeries>[
                  LineSeries<ChartData, String>(
                    dataSource: chartData,
                    xValueMapper: (ChartData data, _) => data.x,
                    yValueMapper: (ChartData data, _) => data.y
              ),
                series: <CartesianSeries>[
                  LineSeries<ChartData, String>(
                    dataSource: chartData,
                    xValueMapper: (ChartData data, _) => data.x,
                    yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

![Legend title](images/legend/legend_tittle.png)

## Toggles the series visibility

You can control the visibility of the series by tapping the legend item. You can enable this feature by enabling the [`toggleSeriesVisibility`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/toggleSeriesVisibility.html) property.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child:SfCartesianChart(
              legend: Legend(
                isVisible: true,
                // Toogles the series visibility on tapping the legend item
                toggleSeriesVisibility: true
              ),
              series: <CartesianSeries>[
                LineeSeries<ChartData, String>(
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

## Legend visibility

The [`isVisible`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/isVisible.html) property of [`legend`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/SfCartesianChart/legend.html) is used to toggle the visibility of legend.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child:SfCartesianChart(
              legend: Legend(
                // Visibility of legend
                isVisible: false
              ),
              series: <CartesianSeries>[
                LineSeries<ChartData, String>(
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

## Legend item visibility

You can control the visibility of a particular series legend item using the [`isVisibleInLegend`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/CartesianSeries/isVisibleInLegend.html) property of series. The default value of the [`isVisibleInLegend`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/CartesianSeries/isVisibleInLegend.html) property is *true*. If it is set to false, then the legend item for this specific series will not be displayed in the legend.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child: SfCartesianChart(
              legend: Legend(
                isVisible: true
              ),
              primaryXAxis: CategoryAxis(),
              series: <ColumnSeries>[
                ColumnSeries<ChartData, String>(                  
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                ),
                ColumnSeries<ChartData, String>(
                  // Hiding the legend item for this series
                  isVisibleInLegend: false,
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

![Legend isVisibleInLegend](images/legend/toggle_visibility.jpg)

## Legend overflow

The legend items can be placed in multiple rows or scroll can be enabled using the [`overflowMode`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/overflowMode.html) property if size of the total legend items exceeds the available size. The default value of the [`overflowMode`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/overflowMode.html) property is [`scroll`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/LegendItemOverflowMode-class.html).

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child: SfCartesianChart(
              legend: Legend(
                isVisible: true,
                // Overflowing legend content will be wraped
                overflowMode: LegendItemOverflowMode.wrap
              ),
              series: <CartesianSeries>[
                LineSeries<ChartData, String>(
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

![Legend](images/legend/overflow_wrap.png))


## Positioning the legend

You can change the position of the legend inside the chart. The following properties are used to customize the position of legend. **auto** position will place the legend at the right, if the chart's width is greater than the chart's height. Else the legend will be placed at the bottom position.

* [`position`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/LegendPosition-class.html) - used to position the legend relatively. The available options are auto, bottom, left, right, and top. Defaults to auto.
* [`orientation`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/orientation.html) - used to change the orientation of the legend, the default value is **auto**. Also you can set [`horizontal`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/LegendItemOrientation-class.html) or [`vertical`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/LegendItemOrientation-class.html).

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child: SfCartesianChart(
              legend: Legend(
                isVisible: true,
                // Legend will be placed at the left
                position: LegendPosition.left
              ),
              series: <CartesianSeries>[
                AreaSeries<ChartData, String>(
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                ),
              ]
            )
          )
        )
      );
    }

{% endhighlight %}

![Legend](images/legend/legend_position.png))

## Legend item template

You can customize the appearance of legend items with your template by using [`legendItemBuilder`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/Legend/legendItemBuilder.html) property of [`legend`](https://pub.dev/documentation/syncfusion_flutter_charts/latest/charts/SfCartesianChart/legend.html). Here you can specify the content that needs to be displayed in the legend text as widget.

{% highlight dart %} 

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        body: Center(
          child: Container(
            child: SfCartesianChart(
              legend: Legend(
                isVisible: true,
                // Templating the legend item
                legendItemBuilder: (String name, dynamic series, dynamic point, int index) {
                  return Container(
                    child: Container(
                      child: Text('template')
                  );
                }
              ),
              series: <CartesianSeries>[
                AreaSeries<ChartData, String>(
                  dataSource: chartData,
                  xValueMapper: (ChartData data, _) => data.x,
                  yValueMapper: (ChartData data, _) => data.y
                )
              ]
            )
          )
        )
      );
    }

{% endhighlight %}
