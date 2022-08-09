# UFOs

### Overview of the analysis: 

Use JavaScript, HTML and CSS to create filter to sort through the UFO sighting data

Resources: JavaScript, HTML, Bootstrap, Data-Driven Documents (D3), bootstrap, CSS

Files: data.js, app.js, index.html, style.css

## Results:

Fully functional webpage was created and filters as the user adds the required parameters.

Figure 1 -  UFO Webpage

![This is an image](https://github.com/IIrazoque/UFOs/blob/977a201a8ed292a7c821f8c1a589727a44554b5e/static/images/figure1.PNG)

Figure 2 – Filtering through data.js UFO sighting data

![This is an image](https://github.com/IIrazoque/UFOs/blob/977a201a8ed292a7c821f8c1a589727a44554b5e/static/images/figure2.PNG)

## Summary:
# Deliverable 1

To create a Filter on multiple criteria we added a new javaScript function called “updateFilters”. Inside this function we created the 3 additional variables followed by an “if statement”. 

**Peusdo code:**

-	An empty variable for the new keys & values called “all filters”
-	Create new function “update filters” and within this function 
-	get the “element AKA: field” that changed (the key and value) 
-	and pass it through the if statement 
-	if the “element” property changes populate the “all filter” variable

**JavaScript code:**
```ruby
  // 1. Create a variable to keep track of all the filters as an object.
  var allfilters = [];
  
  // 3. Use this function to update the filters. 
  function updateFilters() {
  
    // 4a. Save the element that was changed as a variable.
  let elementchange = d3.select(this)
  
    // 4b. Save the value that was changed as a variable.
  let elementvalue = elementchange.property("value");
  
    // 4c. Save the id of the filter that was changed as a variable.
  let filterID = elementchange.attr("id");
  
    // 5. If a filter value was entered then add that filterId and value
    // to the filters list. Otherwise, clear that filter from the filters object.
  if (elementvalue) {
    allfilters[filterID]=elementvalue
  }
  else {
    delete allfilters[filterID];
  }
``` 
The last part of the code re-populated the table with the new details requested.

Figure 3 -  

![This is an image](https://github.com/IIrazoque/UFOs/blob/977a201a8ed292a7c821f8c1a589727a44554b5e/static/images/figure3.PNG)

# Drawback of this webpage -

One drawback of this webpage is that it generates data specific to the filtered criteria. One city at a specific day of the year. For that reason, the user can’t compare dates, cities and states. JavaScript is case sensitive! Having a coding block where the user input is case insensitive (code example, see below). 

# Additional recommendations for further development -

We could fix these drawbacks by adding ranges on the “Enter dates” field and add a second filtering option if the user wishes to us. 
Case insensitive:

//convert to lowercase for case insensitive comparison
if(name1.toLowerCase() === name2.toLowerCase()){

