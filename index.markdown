---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Pseudocode problems
---
# Parsons Practice

## Parsons 1 (Line Based Grader)
<div id="Cinema-sortableTrash" class="sortable-code"></div> 
<div id="Cinema-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="Cinema-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="Cinema-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "age = int(input(&quot;Please enter your age: &quot;))\n" +
    "day = input(&quot;What day is it? &quot;)\n" +
    "if age &gt;= 18 and day == &quot;Wednesday&quot;:\n" +
    "    price = 10\n" +
    "elif age &lt; 18 and day == &quot;Wednesday&quot;:\n" +
    "    price = 6\n" +
    "elif age &gt;= 18:\n" +
    "    price = 12\n" +
    "else:\n" +
    "    price = 8\n" +
    "print(f&quot;Your ticket price is ${price}&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "Cinema-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#Cinema-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#Cinema-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>


