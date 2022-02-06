<script>
// @ts-nocheck

  import Chat from "./components/Chat.svelte";
  import logo from './assets/logo.svg';
  import logo2 from './assets/logo.png'
</script>
<main>
<div class="grid-auto-columns grid-auto-rows">
<div id='#nav' class='sticky flex mdi-18pxw-100 bg-gray-900 shadow-2xl '>
<img src={logo} alt="logo" type="image/svg+xml" class="w-16 h-16 p-4 m-0 hover:animate-spin" />
<img src={logo2} alt="logo2" type="image/svg+xml" class="w-36 h-16 p-4 m-0 hover:animate-ping" />
  <Chat />

</div>
</div>
</main>