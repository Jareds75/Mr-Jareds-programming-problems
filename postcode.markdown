---
layout: default
title: Postcode Validation Loop
---

# Postcode Validation

This puzzle uses a **WHILE** loop to force the user to enter a non-empty postcode.  
The loop should only exit once a valid, non-blank input is received.

**Rules:**
- The program asks for input once before the loop to get the **initial attempt**.
- The loop repeats **only** if the input is blank, first displaying an **error message**.
- The loop exits when a non-blank postcode is entered.

<style>
  /* Reduce extra space after paragraphs and lists */
  p, ul {
    margin-bottom: 0.5em;
  }

  /* Make code boxes wider and reduce top gap — consistent with Cinema version */
  .sortable-code {
    width: 95%;
    min-height: 220px;
    margin-top: 0.4em;
    margin-bottom: 10px;
  }

  /* Make buttons larger and neater — matching Cinema version */
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
<div id="Postcode-sortableTrash" class="sortable-code"></div> 
<div id="Postcode-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="Postcode-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="Postcode-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 

<script type="text/javascript"> 
(function(){
  var initial = 
    "postcode ← \"\"\n" +
    "OUTPUT \"Please enter your postcode: \"\n" +
    "postcode ← INPUT\n" +
    "WHILE postcode = \"\" DO\n" +
    "    OUTPUT \"Error: Postcode is required.\"\n" +
    "    OUTPUT \"Please enter your postcode again: \"\n" +
    "    postcode ← INPUT\n" +
    "ENDWHILE\n" +
    "OUTPUT \"Postcode accepted: \", postcode";

  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "Postcode-sortable",
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

  $("#Postcode-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 

  $("#Postcode-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
