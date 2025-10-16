---
layout: default
title: Pseudocode Problems
---

# Parsons Practice

**[🍦 Ice Cream Puzzle](./icecream.html)**  
**[🔐 Password Puzzle](./password)**  
**[🐞 Debugging Puzzle](./debug)**  

---
# Cinema Tickets

The code blocks below are for a program that calculates the price of a cinema ticket.  
The program should ask for an age and the day of the week.

**Drag, drop, and indent** the blocks to create a working program that follows these rules:

- The base price is **$12** for adults (18+) and **$8** for children.  
- On **Wednesdays**, everyone gets a **$2 discount**.

<style>
  /* Reduce extra space after paragraphs and lists */
  p, ul {
    margin-bottom: 0.5em;
  }

  /* Make code boxes wider and reduce top gap */
  .sortable-code {
    width: 95%;
    min-height: 220px;
    margin-top: 0.4em;
    margin-bottom: 10px;
  }

  /* Make buttons larger and neater */
  input[type="button"] {
    min-width: 140px;
    padding: 8px 12px;
    font-size: 1rem;
    margin-right: 10px;
    border-radius: 6px;
    cursor: pointer;
  }
</style>

## Sort the code below so that it is in the correct order
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



