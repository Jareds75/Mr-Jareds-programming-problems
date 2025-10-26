---
layout: default
title: Days chooser
---

**[🍿 Cinema Ticket Puzzle](./index.html)**  
**[📅 Days chooser](./CASEdays.html)**  
**[🍦 Ice Cream Puzzle](./icecream.html)**  
**[🔐 Password Puzzle](./password.html)**  
**[🐞 Debugging Puzzle](./debug.html)**  

---

# Days chooser

The code blocks below represent a program that lets users choose the day of the week.

**Rules:**
- Users choose a day number  
- The program outputs the day of the week  
- If the number is not a day of the week, it outputs “Error”

<style>
  /* Make code blocks wider and easier to read */
  .sortable-code {
    width: 95%;            /* Use nearly the full page width */
    min-height: 240px;     /* Slightly taller area */
    font-family: monospace;
    font-size: 0.95rem;    /* Slightly larger text */
    line-height: 1.3;
    white-space: pre-wrap; /* Allow long lines to wrap if needed */
    overflow-x: auto;      /* Add horizontal scroll if still too wide */
    margin: 0.4em auto 1em auto; /* Center and reduce top/bottom gaps */
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

<div id="CASEdays-sortableTrash" class="sortable-code"></div> 
<div id="CASEdays-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="CASEdays-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="CASEdays-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 

<script type="text/javascript"> 
(function(){
  var initial = "OUTPUT &quot;Please enter a day number (1-7): &quot;\n" +
    "INPUT DayNumber\n" +
    "// Start the CASE statement, which evaluates the variable DayNumber\n" +
    "CASE OF DayNumber\n" +
    "    1: OUTPUT &quot;Monday&quot;\n" +
    "    2: OUTPUT &quot;Tuesday&quot;\n" +
    "    3: OUTPUT &quot;Wednesday&quot;\n" +
    "    4: OUTPUT &quot;Thursday&quot;\n" +
    "    5: OUTPUT &quot;Friday&quot;\n" +
    "    6: OUTPUT &quot;Saturday&quot;\n" +
    "    7: OUTPUT &quot;Sunday&quot;\n" +
    "    // The OTHERWISE clause catches any value not listed above\n" +
    "    OTHERWISE OUTPUT &quot;Error: Invalid day number entered.&quot;\n" +
    "ENDCASE";

  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "CASEdays-sortable",
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

  $("#CASEdays-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#CASEdays-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
