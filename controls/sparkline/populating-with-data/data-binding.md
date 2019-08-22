---
title: Data-Binding
page_title: RadSparkline Data-Binding
description: The Sparkline control is an information graphic, which is characterized by small size, excellent performance
slug: radsparkline-data-binding
tags: sparkline, data, binding
published: True
position: 0
---

# Data Binding

You can directly bind your preferred series to your data, the currently supported data sources are:

* __IList__ interface for one-dimensional arrays.

* __IListSource__ interface (like DataTable and DataSet classes).

* __IBindingList__ interface. For example the generic BindingList class.

* __IBindingListView__ interface. For example BindingSource class.

To bind the series you need to set theValueMember property. The following example demonstrates this.

#### Bind Series to a DataTable

{{source=..\SamplesCS\Sparkline\SparklineCode.cs region=Bind}} 
{{source=..\SamplesVB\Sparkline\SparklineCode.vb region=Bind}}
````C#
oTable
        DataTable table;
        public void AddBoundSeries()
        {
            table = new DataTable();
            table.Columns.Add("Value", typeof(double));
            table.Rows.Add(1);
            table.Rows.Add(-3);
            table.Rows.Add(5);
            table.Rows.Add(1);
            table.Rows.Add(6);
            table.Rows.Add(-1);
            table.Rows.Add(3);
            table.Rows.Add(-5);
            table.Rows.Add(1);
            table.Rows.Add(6);
            SparkLineSeries lineSeries = new SparkLineSeries();
            lineSeries.ValueMember = "Value";
            lineSeries.DataSource = table;
            lineSeries.ShowMarkers = true;
            lineSeries.ShowHighPointIndicator = true;
            lineSeries.ShowLowPointIndicator = true;
            radSparkline1.Series = lineSeries;
        }

````
````VB.NET
````
 

{{endregion}} 

The bellow image show the result from the above code.

 ![](images/sparkline-data-binding001.png)

 