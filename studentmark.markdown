---
layout: default
title: Mark Validation Loop
---

# Mark Validation

This puzzle uses a **REPEAT…UNTIL** loop to force the user to enter a student mark in the valid range **0 to 100**.

**Rules:**
- The program asks once before the loop for the **initial attempt**.
- If the mark is outside 0–100, an error message is shown.
- The loop repeats until a valid mark is entered.

<style>
  /* Reduce spacing for consistency */
  p, ul {
    margin-bottom: 0.5em;
  }

  /* Match Cinema + Postcode styling */
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

## Sort the code below so that it is in the correct order
<div id="Mark-sortableTrash" class="sortable-code"></div> 
<div id="Mark-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="Mark-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="Mark-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 

<script type="text/javascript"> 
(function(){
  var initial =
    "OUTPUT \"Please enter the student's mark \"\n" +
    "StudentMark ← INPUT\n" +
    "REPEAT\n" +
    "IF StudentMark < 0 OR StudentMark > 100 THEN\n" +
    "    OUTPUT \"The student's mark should be in the range 0 to 100, please re-enter the mark \"\n" +
    "    StudentMark ← INPUT\n" +
    "ENDIF\n" +
    "UNTIL StudentMark >= 0 AND StudentMark <= 100\n" +
    "OUTPUT \"Mark accepted.\"";

  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "Mark-sortable",
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

  $("#Mark-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 

  $("#Mark-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
