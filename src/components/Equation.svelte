<script lang="ts">
  let {equation, response, winAnimating, wrongAnimating}: {equation:string, response:number, winAnimating:boolean, wrongAnimating:boolean} = $props();
</script>

<div class="container">
  <div class="borderAnimating  {winAnimating ? 'winAnimating' : ''} {wrongAnimating ? 'wrongAnimating' : ''}">
    {equation} = 
    {#if response != 0 }
    {response}
    {/if}
  </div>
</div>

<style>
  .container{
    width: 96%;
    text-align: center;
    padding: 2%;

    font-size: 40px;
    background-color: #D9DFC6;
  }
  .borderAnimating{
    border: 10px solid transparent;
  }


  .wrongAnimating{
    animation: blinkRed 0.2s infinite;
  }
  @keyframes blinkRed {
    0%, 100% {
      border: transparent 10px solid;
    }
    50% {
      border: red 10px solid;
    }
  }


  .winAnimating {
    animation: rotateBorder 3s linear;
  }
  @keyframes rotateBorder {
    0% {
      border: green 10px solid;
      border-top-color: transparent;
      border-left-color: transparent;
    }
    25% {
      border: green 10px solid;
      border-right-color: transparent;
      border-bottom-color: transparent;
    }
    50% {
      border: green 10px solid;
      border-left-color: transparent;
      border-top-color: transparent;
    }
    75% {
      border: green 10px solid;
      border-bottom-color: transparent;
      border-right-color: transparent;
    }
    100% {
      border: green 10px solid;
      border-top-color: transparent;
      border-left-color: transparent;
    }
  }
</style>