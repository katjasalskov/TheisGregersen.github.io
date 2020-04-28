# COVID-19 Germany

This page will investigate the spread of COVID-19 in Germany.
The first case of the coronavirus in Germany were registered on Januray 28, 2020 in the state of Bavaria. 

etc.
etc.
etc.


Flot plot
![image](https://user-images.githubusercontent.com/60900143/80474990-7e6dd800-8948-11ea-8ea9-9ee43e9ab953.png) PAS PÅ!!


Flottere plot

Uhh,-nu-bliver-det-lækkert-plot


## "WOW!! HOLD NU OP" siger Sune om dette plot


![MEGA FEED](https://github.com/fertin/Random/blob/master/Assignment2P3.gif?fbclid=IwAR1XvovCVwFiMBrr2b-X-YPQyQpec-bzlBPhB8W44WzQpMigvvyP-9Nlkqo)Welcome to the TheisGregersen.github.io wiki!

https://raw.githubusercontent.com/fertin/Random/master/Assignment2P3.gif

<div id="byte_freq"></div>
<script>
  var language_bytes = <%= language_byte_count %>
  var childrenFunction = function(d){return d.elements};
  var sizeFunction = function(d){return d.count;};
  var colorFunction = function(d){return Math.floor(Math.random()*20)};
  var nameFunction = function(d){return d.name;};

  var color = d3.scale.linear()
              .domain([0,10,15,20])
              .range(["grey","green","yellow","red"]);

  drawTreemap(5000, 2000, '#byte_freq', language_bytes, childrenFunction, nameFunction, sizeFunction, colorFunction, color);

  function drawTreemap(height,width,elementSelector,language_bytes,childrenFunction,nameFunction,sizeFunction,colorFunction,colorScale){

      var treemap = d3.layout.treemap()
          .children(childrenFunction)
          .size([width,height])
          .value(sizeFunction);

      var div = d3.select(elementSelector)
          .append("div")
          .style("position","relative")
          .style("width",width + "px")
          .style("height",height + "px");

      div.data(language_bytes).selectAll("div")
          .data(function(d){return treemap.nodes(d);})
          .enter()
          .append("div")
          .attr("class","cell")
          .style("background",function(d){ return colorScale(colorFunction(d));})
          .call(cell)
          .text(nameFunction);
  }

  function cell(){
      this
          .style("left",function(d){return d.x + "px";})
          .style("top",function(d){return d.y + "px";})
          .style("width",function(d){return d.dx - 1 + "px";})
          .style("height",function(d){return d.dy - 1 + "px";});
  }
</script>
