---
sidebar_position: 4
---

 # Charts

A chart defines how data from submitted forms will be displayed.

 ![Chart](img/chart-edit.png) 

**Chart Name** - The Chart Name is the identifier of the chart.  It should not contain spaces or special characters.

**Title** - The Title is displayed at the top of the chart

**View On** - You can select if the chart is displayed on mobile, desktop or both.  By default a chart is displayed on both.

**Units of Measure** - Select one or more units of measure to display in the chart.

 ![Chart Types](img/chart-types.png)

## Time Series

The Time Series options displays charts in a line chart with the date on the X axes.  You can select many units of measure or just one.  When defining a time series chart, select the date field (sort order), the smoothing algorithm applied and grid lines settings.

![Time Series Edit](img/time-series-edit.png)
![Time Series](img/line-chart-one.png)

## Bar Chart

When bar chart option is selected, *Grouped* and *Horizontal* may be specified.  The *Grouped* setting determines if the bars show up side by side (as shown below) are stacked.  Use stacked when the sum is interesting. 

![Bar Chart Edit](img/bar-chart-edit.png)

![Bar Chart](img/bar-chart-grouped.png)

## Submission Count

This simple chart simply displays the number of form submissions made in the selected period.  It is good for demonstrating engagement. Here it is shown with the *Two Charts 1 Big 1 Any* layout.

![Submission Count](img/submission-count.png)

## Photo Gallery

Displaying images uploaded by users can also be done with a chart.  When using a Photo Gallery chart type, also specify the form that contains the image upload feature and the upload field name.  A *Form View* selection allows you to specify text from the same form submission that will be overlaid on the image when the info (i) is clicked. Select a view defined in the [Views](./views) section.

![Edit Photo](img/image-edit.png)

![Gallery](img/gallery.png)
![Form View](img/image-form-view.png)

## Checkbox Grid

Configuring a Check Box grid requires that you define a form and field.  The field you select should be a multi select field such as a *Select Boxes* field type that allow a user to select one of many values.

![Check Box Grid Edit](img/check-box-grid-edit.png)

![Check Box Grid](img/check-box-grid.png)
![Check Box Grid](img/check-box-grid2.png) 

## Grid

A Grid chart type is a simple table of numbers.  Configuring simple requires selecting the fields to display.

![Grid Edit](img/grid-edit.png)

![Grid Edit](img/grid.png)

## View

A View allows you to specify a formatted text with data inserted by using [Healix Expression Grammar](/docs/dynamic-data-model/healix-calculation-grammar).  When defining a View chart type, just select the *View* defined in the [Views](./views) section.

![View Chart Edit](img/view-chart-edit.png)


