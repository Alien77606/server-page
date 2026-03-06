<!DOCTYPE html>
<html>
<head>
<title>Secure Server Terminal</title>

<style>
body{
background:black;
color:#00ff00;
font-family:monospace;
text-align:center;
padding-top:80px;
}

input{
background:black;
border:1px solid #00ff00;
color:#00ff00;
padding:10px;
font-size:18px;
}

button{
background:#00ff00;
color:black;
border:none;
padding:10px 20px;
font-size:18px;
cursor:pointer;
}

#terminal{
margin-top:30px;
font-size:18px;
}

.progress{
width:60%;
height:20px;
border:1px solid #00ff00;
margin:20px auto;
}

.bar{
height:100%;
width:0%;
background:#00ff00;
}
</style>

</head>

<body>

<h2>SECURE SERVER ACCESS</h2>

<input type="text" id="device" placeholder="Enter Device Name">
<br><br>

<button onclick="start()">Connect</button>

<div id="terminal"></div>

<div class="progress">
<div class="bar" id="bar"></div>
</div>

<script>

function fakeIP(){
return Math.floor(Math.random()*255)+"."+
Math.floor(Math.random()*255)+"."+
Math.floor(Math.random()*255)+"."+
Math.floor(Math.random()*255);
}

function start(){

var device=document.getElementById("device").value;
var ip=fakeIP();

document.getElementById("terminal").innerHTML=
"Initializing connection...<br>"+
"Device: "+device+"<br>"+
"Generating IP... "+ip+"<br>"+
"Connecting to secure server...";

var bar=document.getElementById("bar");
var width=0;

var load=setInterval(function(){

if(width>=100){
clearInterval(load);

document.getElementById("terminal").innerHTML+=
"<br>Bypassing firewall..."+
"<br>Decrypting server key..."+
"<br><br>ACCESS GRANTED ✔";

}else{
width++;
bar.style.width=width+"%";
}

},40);

}

</script>

</body>
</html># server-page
