<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css"/>
<script>
$(document).ready(function(){
$("button").addClass("animated bounce")
});

function reSet() {
document.getElementById("demo").innerHTML="";
var table=document.getElementById("myTable");
var r=0;
while(row=table.rows[r++])
{
  var c=0;
  while(cell=row.cells[c++])
  {
    cell.innerHTML=''; // do sth with cell
  }
}
}


function start(){

document.getElementById('demo').innerHTML="Game Started";
    const set1 = new Set();
    
   
    var table = document.getElementById("myTable");
  
    var value,count=0;
    for ( var i = 0; i<table.rows.length; i++ ) { 
        document.getElementById('demo').innerHTML="Game Started"+i;
         var row = table.rows.item(i); 
         for ( var j = 0; j<row.cells.length; j++ ) { 
document.getElementById('demo').innerHTML="Game Started"+i+j;
             var col = row.cells.item(j);
              
             value=parseInt(table.rows[i].cells[j].innerHTML);
             //alert(value);
             if(Number.isNaN(value) && value!=0){
               alert("FILL THE BOX"+i+j);
               count++;
               continue;
               }
               else
                {
                 set1.add(value);
                }
         } 
      } 
if(set1.size===1 && count===0)
{
alert("YOU WIN");
//document.getElementById('demo').innerHTML="YOU WIN";
}
else
{
alert("YOU LOSE");
//document.getElementById('demo').innerHTML="YOU LOSE";
}
  reSet();
}
</script>
</head>
<body>
<div class="container-fluid">
<p id="demo" class="bounce"></p>
<script>

</script>
<center>
<h3>FILL ALL THE BOXES WITH EQUAL INTEGERS</h3>
<table border=60 cellpadding=50px  id="myTable">
<caption><center>Play Game</center></caption>
<tr >
<td contenteditable="true" ></td> 
<td contenteditable='true'></td>
<td contenteditable='true'></td>
</tr>

<tr >
<td contenteditable='true'></td>
<td contenteditable='true'></td>
<td contenteditable='true'></td>
</tr>

<tr >
<td contenteditable='true'></td>
<td contenteditable='true'>
</td>
<td contenteditable='true'>
</td>
</tr>
</table>
<button type="button" onclick="start()">START GAME</button>
<button type="button" onclick="reSet()">RESET</button>
</center>

<p align="right">Created By Prashant S.</p>
</div>
</body>
</html>
