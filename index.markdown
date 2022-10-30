# Directions
Re-arrange the blocks so that the program asks the user to continuously enter numbers, adds them all up, and then stops asking when the total reaches or exceeds 20.

# Code
<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p id="buttons"> 
    <input id="feedbackLink" class="button" value="Check" type="button" /> 
    <input id="newInstanceLink" class="button" value="Reset Problem" type="button" /> 
</p>

<style>
    #buttons {
        padding-left: 32px;
    }
   .button {
        padding: 8px 16px;
        border: 2px solid transparent;
        border-radius: 12px;
        font-size: 18px;
    }
    .button:hover {
        cursor: pointer;
    }

    #feedbackLink {
        background: #C4B454;
        color: #222;
    }
    #feedbackLink:hover {
        color: #222;
        background: white;
        border: 2px solid #C4B454;
    }
    #feedbackLink:active {
        outline: 2px solid #C4B454;
    }

    #newInstanceLink {
        background: #222;
        color: white;
    }
    #newInstanceLink:hover {
        color: #222;
        background: white;
        border: 2px solid #222;
    }

    #newInstanceLink:active {
        outline: 2px solid #222;
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
