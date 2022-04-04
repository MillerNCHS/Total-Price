<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "import random\n" +
    "drivers = [&quot;Bowser&quot;, &quot;Luigi&quot;, &quot;Mario&quot;, &quot;Peach&quot;]\n" +
    "rndNum = random.randrange(0, 10)\n" +
    "if rndNum &lt; len(drivers):\n" +
    "	print(&quot;You&#039;ve lost &quot; + drivers[rndNum] + &quot; because they drove off the Rainbow Road.&quot;)\n" +
    "    del drivers[rndNum]\n" +
    "else:\n" +
    "	print(&quot;You&#039;ve unlocked Yoshi!&quot;)\n" +
    "    drivers.append(&quot;Yoshi&quot;)\n" +
    "   \n" +
    "print(&quot;You now have the following drivers:&quot;)\n" +
    "for driver in drivers:\n" +
    "	print(driver)";
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
