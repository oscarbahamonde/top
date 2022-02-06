// @ts-nocheck
<script>
// @ts-nocheck

  import io from 'socket.io-client'
  const socket = io("http://localhost:8000")
  let messages = []
  let message = ''
  let date = new Date().toLocaleDateString().slice(0, -5)
  let time = new Date().toLocaleTimeString().slice(0,-3)
  
 
  socket.on('chat message', (data) => {
  messages = [...messages, data]
})
function sendMessage() {
  socket.emit('chat message', message)
  message = ""
}
  let texto = ""  
  async function appendText(text) {
    try {const element = document.createElement("p")
    element.innerHTML = text
    document.getElementById("text").appendChild(element)
    messages.push(element.text);
    console.log(messages)
  } catch(e) {
    console.log(e)
  }
  }
</script>

<div class="fixed bottom-0-left-0 bg-gray-100 p-1 bottom-0 right-0 rounded-lg h-100 overscroll border-4 border-black" >
  <div class="bg-white border-black border-2 p-1 rounded-md mb-2 p-1 max-h-48 overflow-scroll " id="text" />
  <div>
    <input
      placeholder="write your message here..."
      class="bg-gray-50 border-4 border-black text-teal-500 rounded-lg p-2"
      on:change={appendText(`<div class="my-2"><small class="bg-teal-600 content-box rounded-lg text-lg text-white p-1"><strong>You:</strong> 
       ${texto} </small><sub class="text-xs text-teal-600 p-1">${date}@${time}</sub></div>`)
      .then((this.value = "")
      .then(messages.push(texto)))}
      bind:value={texto}
    /><i class="mdi mdi-send p-2 text-2xl cursor-pointer" style="color: #2C998C;" on:click={appendText}/>
  </div>
</div>