Chart
=====

HTML canvas-based pie and ring charts with tooltips and update animations.

![Canvas Pie and Ring Charts][chartImage]

Demos
-----

[Pie Chart Demo](http://www.matts411.com/static/demos/chart/pie_chart.html)
[Ring Chart Demo](http://www.matts411.com/static/demos/chart/ring_chart.html)

Features
--------

* Cross browser compatible (Chrome, Firefox, Safari, Opera, Internet Explorer 7+)
* Framework independent - Works with jQuery, Mootools, etc.
* Pie charts with animations and tooltips
* 2-level Ring charts with animations and tooltips

Installation
------------

Minify and add `src/Chart.js` and `src/Chart.css` to your website's resources 
directory. You can change some of the styling in Chart.css to suit your needs.

If you plan on supporting Internet Explorer 8 or older, you'll need to also 
minify and add `src/excanvas.js` as well as the image file `src\clear.gif`.

Usage
-----

Create a `DIV` element with an `ID`, relative positioning and a fixed width and
height:

    <div id="myChart" style="position:relative;width:250px;height:250px;"></div>

Initialize the chart using Javascript:

    new Chart.Pie("myChart", {
      showTooltips : true, 
      chartMinSize : [250, 250], 
      chartMaxSize : [250, 250], 
      chartData : [["Firefox", 39.20, "00:01:33", "#759ddf"], 
                   ["Internet Explorer", 30.58, "00:03:04", "#76df72"], 
                   ["Chrome", 22.91, "00:02:01", "#f1d94b"], 
                   ["Safari", 3.63, "00:01:03", "#f1994a"], 
                   ["Opera", 2.28, "00:00:48", "#f15f5f"], 
                   ["Other", 1.40, "00:00:14", "#aa7be5"]]
    });

A ring chart is initialized similarly:

    new Chart.Ring("myChart", {
      showTooltips : true, 
      chartMinSize : [250, 250], 
      chartMaxSize : [250, 250], 
      chartData : [["Fixed Income", [
                       ["Taxable Bonds", 10.00, ""], 
                       ["High Yield Bonds", 10.00, ""], 
                       ["Int'l Debt", 10.00, ""]], "", "#76df72"], 
                   ["Equity", [
                       ["Large Cap Equity", 15.00, ""], 
                       ["Mid Cap Equity", 10.00, ""], 
                       ["Small Cap Equity", 5.00, ""], 
                       ["Int'l Equity", 10.00, ""]], "", "#759ddf"], 
                   ["Real Estate", [
                       ["Global Public REITs", 5.00, ""], 
                       ["Private Real Estate", 10.00, ""]], "", "#f1d94b"], 
                   ["Alternatives", [
                       ["Diversified Hedge", 5.00, ""], 
                       ["Private Equity", 5.00, ""]], "", "#f1994a"], 
                   ["Cash", [
                       ["Cash", 5.00, ""]], "", "#f15f5f"]]
    });

See the demo source code for an animation example.

Options
-------

**showTooltips**
Boolean. Show tooltips when a mouse hovers over a slice. Disabled automatically in touch devices.
Default is `false`.

**selectorPrefix**
String. Prefixed to every `id`, `name`, `class` attribute for DOM element reference.
Default is `"chart"`.

**selectorSuffix**
String. Suffixed to every `id` and `name` attribute for DOM element reference (note NOT `class`.)
Default is `""`.

**chartData**
Array. An array of arrays. Inner array format depends on the chart type. See usage section for examples.
Default is `[]`.

**chartMinSize**
Array. Format is `[width, height]` in pixels (`-Infinity` for no minimum.)
Default is `[-Infinity, -Infinity]`.

**chartMaxSize**
Array. Format is `[width, height]` in pixels (`Infinity` for no maximum.)
Default is `[Infinity, Infinity]`.

**clearImgPath**
String. Path location of a 1x1 pixel transparent image for use by Internet Explorer 7 and older.
Default is `"src/clear.gif"`.

**onRegionEnter**
Function. If `showTooltips` is `true`, this function will be called whenever a mouse enters into a tooltip
region, such as a pie chart slice. Returned in `arguments` are one or more string labels passed in from the 
`chartData` option. The number of `arguments` differs by chart type.
Default is a function that does nothing.

**onRegionExit**
Function. Same as `onRegionEnter` but in reverse.
Default is a function that does nothing.

Future Features
---------------

* Bar charts
* Line charts

License
-------

MIT-style license.
Copyright 2012 Matt V. Murphy | bW11cnBoMjExQGdtYWlsLmNvbQ==


[chartImage]: data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYkAAAC6CAMAAABsmkE4AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyBpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuMC1jMDYwIDYxLjEzNDc3NywgMjAxMC8wMi8xMi0xNzozMjowMCAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENTNSBXaW5kb3dzIiB4bXBNTTpJbnN0YW5jZUlEPSJ4bXAuaWlkOjMyNTg3MjZDMzAzRDExRTI5RDdFQUJEMjRBOTFGMDlFIiB4bXBNTTpEb2N1bWVudElEPSJ4bXAuZGlkOjMyNTg3MjZEMzAzRDExRTI5RDdFQUJEMjRBOTFGMDlFIj4gPHhtcE1NOkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6MzI1ODcyNkEzMDNEMTFFMjlEN0VBQkQyNEE5MUYwOUUiIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6MzI1ODcyNkIzMDNEMTFFMjlEN0VBQkQyNEE5MUYwOUUiLz4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94OnhtcG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz6h2sMpAAADAFBMVEXhyk70aGjd3d2M7In266512XFlvGLYiUWP0Y2B5n6Vtuvn9ueG6YKkxfty1m6J6oXy8vLyy52avPX03VXa4/KNsu1YdqeJrut4ntr34Fz30a/w45L79uR43XRxl9b1qqpylc7k6/b13lim8KNtkctkgrT75WqEquiV8pHx2lFty2ptwmra89l0mdXv107sYmL1j4984nnhkk386+X3cnL65tel5aPqlUv2pFp6oOHnXV3H1et+pOSl+6Lq2XLm1/p11nLH5ca2yedzz3BqjMPSu0G4jO2657j38tj44mCBqOb5qmSApuX76H2WufKStvDp0kpihbuFptvu7u75w8PznVHyv5Li4uLH2vj36Mx6oN1ymdjr1FLaw0Z2nNrHpPKc9ph3nt2s26qY9JXm5uZ0mtjrmFCGrOnq8Pf1oFXp6en4+Pj619V+5Husw+hwzG2pu9jp0k343cSY4JV7ouJ52Xb48cV54HXxm07w2E7umEzY79iju+RqjcjH9MZce65pwWbR2ujdxkiP7oziy0j65GZhtl+ofOFesVuYs96D54CS8I5823lmicLB8b+287SRrNfm0Enqpmr2tnvp5Ni1xN7v++zbym6ewPdnv2Szy/LfyEvdyvX542OGzYO+0/f8/Pz05fZvlNB733fg5vBgf7Gv563srXSKo8vk6O9oir+UqszS3vHWw13fWFiAncvz21Hu5rrv9frs1Evr1Ev89PLyfX3v7OLs1U1wjLpqx2fWv0TS8dHizl5lh752ksDi08V41HXg99+f153fkErAzuXejUf24GV6nNTh29WK3Yf38f7anWjh8eHcllnjxcVfgLb8r2r4+v3////gZWV80XmDmr98w3repnW+0Ozmkkj3p17z4Xb3/ffz+PzfyEaOrN6u76z23+f//fHn7+jO9s7o6u/N7czroF1vh7H/+ffShUG+yt7r7OyLsOz03FODqed4nt+g+Jx9o+OA5XyPtO/+/v796G/jnWBmhbZpg66J5obi1IXSjU/qs4L2rm7eGwmbAAAzvUlEQVR42u2dfUBUVdrAxxE/corGGlsFFMfM3MJyG0CLNEU2xrVal0FG0axstHGgCTHJEjWyekON/N7WSqmIRNlKSiyXtMVsi3fZLekLtTLXoLamtDbcdn3tPZ/3nnPuuXfuDIP1h89QbcDuOvc3v+fj3HPvtbSciZ9HWM4cAv34aIOtubG5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 "Demo links below"
