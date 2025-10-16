---
layout: default
title: Ice Cream Prices
---

**[🍦 Cinema Ticket Puzzle](./index.html)** 
**[🍦 Ice Cream Puzzle](./icecream.html)**  
**[🔐 Password Puzzle](./password)**  
**[🐞 Debugging Puzzle](./debug)**  

---

# Ice Cream Shop

The code blocks below represent a program that calculates the price of an ice cream order.

**Rules:**
- Vanilla = \$2, Chocolate = \$3, Strawberry = \$2.5  
- If the customer wants toppings, add \$1.  
- If they buy more than 3 scoops, give a 10% discount.

<div id="IceCream-sortableTrash" class="sortable-code"></div> 
<div id="IceCream-sortable" class="sortable-code"></div> 
<p>
  <input id="IceCream-feedbackLink" value="Get Feedback" type="button" />
  <input id="IceCream-newInstanceLink" value="Reset Problem" type="button" />
</p>

<script type="text/javascript">
(function(){
  var initial = "flavour = input(&quot;Choose flavour: Vanilla, Chocolate, or Strawberry: &quot;)\n" +
    "scoops = int(input(&quot;How many scoops? &quot;))\n" +
    "toppings = input(&quot;Add toppings (yes/no)? &quot;)\n" +
    "if flavour == &quot;Chocolate&quot;:\n" +
    "    price = 3\n" +
    "elif flavour == &quot;Strawberry&quot;:\n" +
    "    price = 2.5\n" +
    "else:\n" +
    "    price = 2\n" +
    "if toppings == &quot;yes&quot;:\n" +
    "    price = price + 1\n" +
    "total = price * scoops\n" +
    "if scoops &gt; 3:\n" +
    "    total = total * 0.9\n" +
    "print(f&quot;Your total is ${total:.2f}&quot;)";
  var puzzle = new ParsonsWidget({
    sortableId: "IceCream-sortable",
    grader: ParsonsWidget._graders.LineBasedGrader,
    can_indent: true,
    show_feedback: true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#IceCream-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  $("#IceCream-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 

})();
</script>

