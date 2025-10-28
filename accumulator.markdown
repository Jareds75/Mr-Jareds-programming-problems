
---
layout: default
title: Days chooser
---

**[🍿 Cinema Ticket Puzzle](./index.html)**  
**[📅 Days chooser](./CASEdays.html)**
**[📲 Accumulator](./accumulator.html)** 
**[🍦 Ice Cream Puzzle](./icecream.html)**  
**[🔐 Password Puzzle](./password.html)**  
**[🐞 Debugging Puzzle](./debug.html)**  

---

# Accumulator

The code blocks below represent a program that totals numbers until a user decides to stop

**Rules:**
- The program asks the user to enter numbers repeatedly.
- Each number entered is added to a running Total.
- When the user enters -1, the loop stops and the final Total is displayed.

<style>
  /* Make code blocks full-width */
  .sortable-code {
    display: block !important;     /* Force block layout */
    width: 95% !important;         /* Nearly full page width */
    max-width: none !important;    /* Remove any internal max-width */
    min-height: 240px;
    font-family: monospace;
    font-size: 0.95rem;
    line-height: 1.3;
    white-space: pre-wrap;
    overflow-x: auto;
    margin: 0.6em auto 1em auto;
    text-align: left;
  }

  /* Fix the internal parsons container */
  .sortable {
    display: block !important;
    width: 100% !important;
    max-width: none !important;
    text-align: left !important;
  }

  /* Make buttons look consistent */
  input[type="button"] {
    min-width: 140px;
    padding: 8px 12px;
    font-size: 1rem;
    margin-right: 10px;
    border-radius: 6px;
    cursor: pointer;
  }
</style>

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "Total ← 0\n" +
    "Number ← 0\n" +
    "OUTPUT &quot;This program totals the numbers you enter.&quot;\n" +
    "OUTPUT &quot;"Enter first number (-1 to stop): " &quot;\n" +
    "Number ← INPUT\n" +
    "// loops until a user enters -1\n" +
    "WHILE Number != -1 DO\n" +
    "    // This line accumulates a total\n" +
    "    Total ← Total + Number\n" +
    "    \n" +
    "    OUTPUT &quot;Enter another number (or -1 to stop): &quot;\n" +
    "    Number ← INPUT\n" +
    "ENDWHILE\n" +
    "OUTPUT &quot;The final total is: &quot;, Total";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
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
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
