<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
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
