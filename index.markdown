# Directions
Re-arrange the blocks so that the program asks the user to continuously enter numbers, add them all up, and then stop asking when the total exceeds 20.

# Code
<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p>

<style>
   #feedbackLink {
        background: green;
        color: white;
        padding: 16px;
        border: 2px solid transparent;
        border-radius: 12px;
    }
    #feedbackLink:hover {
        cursor: pointer;
        background: white;
        color: green;
        border: 2px solid green;
    }

    #feedbackLink:active {
        outline: 2px solid green;
    }
</style>

<script type="text/javascript"> 
(function(){
  var initial = "total = 0\n" +
    "while True:\n" +
    "	number = input(&quot;Enter a number&quot;)\n" +
    "	number = int(number)\n" +
    "	total = total + number\n" +
    "	if number &gt;= 20:\n" +
    "		break";
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
