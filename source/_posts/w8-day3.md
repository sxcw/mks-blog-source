---
title: Day 37 and Let's D3!
tags: 
- during-bootcamp
- d3
comments: true
date: 2016-07-20
---

Data visualization and d3 today! I started using react-d3-componenet module last night and managed to have something show up! So exciting. The next step is populate graphs with meaningful users statistics.  This will be fun.  


React D3: Intro
----------

The module I used is <a href="https://github.com/codesuki/react-d3-components" target="_blank"> React D3 Component</a>.  It is easy to use and you can quickly have your graphs up and running on page if you follow the readme. The downside I experienced is lack of customization (compared to native D3) and because this is a relatively new module, when I ran into problems, I didn't have a lot of resources/tutorials to refer to. Google and stackoverflow don't offer much help.  Using new module is the both thrilling and a little painful. 

React D3: Let's create a Simple Piechart (3-5 mins)
----------

**First Step: install module**

```
npm install --save react-d3-components
```

**Second Step: get data**

```
data = {
	label: 'Your Stats',
	values: this.state.pieChartValues
}
```
This is what I have in the constructor function:
```
constructor(props) {
	super(props);
	this.state = {
	  pieChartValues: [{x: 'wins', y: 0}, {x: 'losses', y: 0}] //initial value
	}
}

```
D3 is very particular about what data you feed in, pay attention to what data it is looking for, is it an object or array.  Refer to official documentation when in doubt (<a href="https://github.com/codesuki/react-d3-components" target="_blank"> React D3 Component</a>).

**Last Step: feed data to chart**

```
<PieChart
	data={data}
	width={600}
	height={400}
	margin={{top: 30, bottom: 10, left: 100, right: 100}} // for positioning            
	tooltipHtml={this.tooltipPieChart} //optional
	tooltipMode={'fixed'} // optional 
	tooltipOffset={{top: 135, left: 200}} // optional
/>
```

```
tooltipPieChart(x,y) {
	// helper function for tooltip
	// I only need to show y
  return y.toString();
}
```
That's it! 