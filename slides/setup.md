## Setup

***

Fetch the CSV with ```d3.csv()``` and the TopoJson with ```d3.json()```

Loop over the data and turn strings into numbers:

```javascript
    var fields, svg = d3.select("#container").append("svg");
    fields = [ "Code", "1990-advanced", "1990-bachelors", "1990-hs", "1990-not-hs", "2000-advanced",
    "2000-bachelors", "2000-hs", "2006-advanced", "2006-bachelors", "2006-hs", "2007-advanced",
    "2007-bachelors", "2007-hs", "2008-advanced", "2008-bachelors", "2008-hs", "2009-advanced",
    "2009-bachelors", "2009-hs"];

    d3.json("data/us.json", function(us) {
      d3.csv("data/education.csv", function(edu) {
        edu.forEach(function(d) { 
          fields.forEach(function(field) {
            d[field] = parseFloat(d[field]);
          });
        }) // Append some text to prove we got what we want.
        svg.append("text").attr("transform", "translate(0,20)")
          .text("We have " + edu.length + " edu entries.");
      });
    });
```
[Step 1](step1.html)
