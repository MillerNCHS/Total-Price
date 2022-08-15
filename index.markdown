<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "def rate_score(score):\n" +
    "    &quot;&quot;&quot;Rate a score and return a string&quot;&quot;&quot;\n" +
    "    if score &lt; 1000:\n" +
    "        return &quot;Nothing to be proud of.&quot;\n" +
    "    elif score &lt; 10000:\n" +
    "        return &quot;Not bad.&quot;\n" +
    "    else:\n" +
    "        return &quot;Nice!&quot;\n" +
    "def main ():\n" +
    "    &quot;&quot;&quot; calls the function with user inputed scores&quot;&quot;&quot;\n" +
    "    print (&quot;Welcome to Chapter 6, Project 1!&quot;)\n" +
    "    yourscore = int(input(&quot;What was your score?&quot;))\n" +
    "    while yourscore != -1:\n" +
    "        print (rate_score(yourscore))\n" +
    "        yourscore = int(input(&quot;What was your score? (-1 to end) &quot;))\n" +
    "   \n" +
    "    input(&quot;Press the enter key to exit.&quot;)\n" +
    "main()";
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
