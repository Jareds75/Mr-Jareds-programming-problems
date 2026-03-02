layout: default
title: Array Search Parsons Problem
---

# Finding Values in an Array

This puzzle focuses on **iterating** through a 1D array and using **selection** to output specific items that meet a criteria.

**Rules:**
- Define a 1D array (list) of fruits.
- Use a `for` loop to look at every item in the list.
- Use an `if` statement to check if the character "c" is in the string.
- **Output** the fruit name only if the condition is met.

<style>
  .sortable-code {
    width: 95%;
    min-height: 200px;
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

## Sort the code below

<div id="FruitSearch-sortableTrash" class="sortable-code"></div> 
<div id="FruitSearch-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="FruitSearch-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="FruitSearch-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 



<script type="text/javascript"> 
(function(){
  var initial =
    "fruits = ['apple', 'cherry', 'banana', 'coconut', 'peach']\n" +
    "for i in range(len(fruits)):\n" +
    "    if 'c' in fruits[i]:\n" +
    "        print(fruits[i])";

  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "FruitSearch-sortable",
    "max_wrong_lines": 1,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "can_indent": true,
    "x_indent": 50,
    "show_feedback": true
  });

  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();

  $("#FruitSearch-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 

  $("#FruitSearch-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
