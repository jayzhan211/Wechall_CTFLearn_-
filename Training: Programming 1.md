# Problem
When you visit this link you receive a message.
Submit the same message back to http://www.wechall.net/challenge/training/programming1/index.php?answer=the_message
Your timelimit is 1.337 seconds
## Solution
Log in website first,it will check your cookie

1.Press F12

2.write the code below in the console

```jquery
$.ajax({
  url: 'http://www.wechall.net/challenge/training/programming1/index.php?action=request',
  type: 'get',
  dataType: 'text',
  success:function(data){
    var newUrl="index.php?answer="+data;
    window.location.href=newUrl;
  }
});
```
