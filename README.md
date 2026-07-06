<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fake Chatbot</title>
<style>
body{
    margin:0;
    background:#0d1117;
    color:white;
    font-family:Arial,sans-serif;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}
.chat{
    width:350px;
    background:#161b22;
    border-radius:10px;
    overflow:hidden;
}
.header{
    background:#238636;
    padding:15px;
    text-align:center;
    font-weight:bold;
}
.messages{
    height:400px;
    overflow-y:auto;
    padding:10px;
}
.bot,.user{
    margin:8px 0;
    padding:10px;
    border-radius:8px;
    max-width:80%;
}
.bot{
    background:#30363d;
}
.user{
    background:#238636;
    margin-left:auto;
}
.input-area{
    display:flex;
}
input{
    flex:1;
    padding:10px;
    border:none;
    outline:none;
}
button{
    background:#238636;
    color:white;
    border:none;
    padding:10px 15px;
    cursor:pointer;
}
</style>
</head>
<body>

<div class="chat">
    <div class="header">Fake AI Chatbot</div>

    <div class="messages" id="messages">
        <div class="bot">Hello! I'm a fake AI chatbot.</div>
    </div>

    <div class="input-area">
        <input id="input" placeholder="Type a message...">
        <button onclick="send()">Send</button>
    </div>
</div>

<script>
const replies = [
    "Interesting!",
    "I'm just a demo chatbot.",
    "That sounds great!",
    "Can you tell me more?",
    "I'm not connected to any AI.",
    "Thanks for your message!"
];

function send(){
    const input = document.getElementById("input");
    const text = input.value.trim();
    if(!text) return;

    const messages = document.getElementById("messages");

    messages.innerHTML += `<div class="user">${text}</div>`;
    input.value="";

    setTimeout(()=>{
        const reply = replies[Math.floor(Math.random()*replies.length)];
        messages.innerHTML += `<div class="bot">${reply}</div>`;
        messages.scrollTop = messages.scrollHeight;
    },700);
}
</script>

</body>
</html>
