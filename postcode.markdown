---
layout: default
title: Postcode Validation Loop
---

<h1>Postcode Validation</h1>

This puzzle uses a **WHILE** loop to force the user to enter a non-empty postcode. The loop should only exit once a valid, non-blank input is received.

**Rules:**
- The program asks for input once before the loop to get the **initial attempt**.
- The loop repeats **only** if the input is blank, first displaying an **error message**.
- The loop exits when a non-blank postcode is entered.

<style>
  /* Make code blocks wider and easier to read and ensure they are LEFT-aligned */
  .sortable-code {
    /* Increased width for wider display */
    width: 98%; 
    min-height: 240px;
    font-family: monospace;
    font-size: 0.95rem;
    line-height: 1.3;
    white-space: pre-wrap;
    overflow-x: auto;
    /* Set left/right margins to 0 to remove centering and push content left */
    margin: 0.4em 0 1em 0; 
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

<!-- Removed inline text-align: center to default to left alignment -->
<p>
    <input id="feedbackLink" value="Get Feedback" type="button" />
    <input id="newInstanceLink" value="Reset Problem" type="button" />
</p>

<script type="text/javascript">
(function(){
  // The CORRECT and CLEANER pseudocode for validation:
  var initial = "postcode ← \"\"\n" +
    "OUTPUT \"Please enter your postcode: \"\n" +
    "postcode ← INPUT\n" +
    "// Loop continues WHILE the postcode is blank\n" +
    "WHILE postcode = \"\" DO\n" +
    "    OUTPUT \"Error: Postcode is required.\"\n" +
    "    OUTPUT \"Please enter your postcode again: \"\n" +
    "    postcode ← INPUT\n" +
    "ENDWHILE\n" +
    "OUTPUT \"Postcode accepted: \", postcode";

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
