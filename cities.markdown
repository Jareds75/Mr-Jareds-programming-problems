layout: default
title: Filter Cities by Length
---

# 1D Array: City Length Filter

This puzzle uses a **for loop** to check the length of each string stored in a 1D array.

**Rules:**
- Define the array `mylist` with the names of the cities.
- Use `range(len(mylist))` to iterate through every index position.
- Inside the loop, check if the length of the current city `len(mylist[i])` is **greater than 5**.
- If it is, **output** that city.

<style>
  .sortable-code {
    width: 95%;
    min-height: 220px;
    margin-top: 0.4em;
    margin-bottom: 10px;
  }
  input[type="button"] {
    min-width: 140px;
    padding: 8px 12px;
    font-size: 1rem;
    margin-right: 10px;
    border-radius: 6px;
    cursor: pointer;
  }
</style>

## Sort the code to find cities with more than 5 characters

<div id="City-sortableTrash" class="sortable-code"></div> 
<div id="City-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="City-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="City-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 



<script type="text/javascript"> 
(function(){
  var initial =
    "mylist = ['New York', 'Paris', 'London', 'Tokyo', 'Singapore', 'Moscow']\n" +
    "for i in range(len(mylist)):\n" +
    "    if len(mylist[i]) > 5:\n" +
    "        print(mylist[i])";

  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "City-sortable",
    "max_wrong_lines": 1,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "can_indent": true,
    "x_indent": 50,
    "show_feedback": true
  });

  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();

  $("#City-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 

  $("#City-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
