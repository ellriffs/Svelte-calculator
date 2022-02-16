<script>
  import FaUndo from 'svelte-icons/fa/FaUndo.svelte';
  import FaEquals from 'svelte-icons/fa/FaEquals.svelte';

  let input = Number;
  let input2 = Number;
  let result;

  const inputNum = (event) => {
    event.preventDefault();
    input === event.target.value;
    input2 === event.target.value;
    result = input + input2;
    console.log(input + input2);
  };

  const reset = () => {
    input = null;
    input2 = null;
    result = null;
  };
</script>

<h1>Svelte Test App</h1>
<form>
  <input bind:value={input} type="number" />
</form>

<form>
  <input bind:value={input2} type="number" />
</form>
<div>
  <button on:click={inputNum}><FaEquals /></button>
  <button on:click={reset}> <FaUndo /> </button>
</div>
{#if result}
  <h3>{result}</h3>
{:else}
  <div />
{/if}

<style>
  :global(body) {
    background: linear-gradient(45deg, blue, cyan);
  }
  h1 {
    color: white;
    text-align: center;
    font-weight: lighter;
    font-size: 4rem;
    text-shadow: 2px 8px 7px black;
    text-decoration: underline 3px red;
  }
  h3 {
    color: white;
    font-size: 3rem;
    text-align: center;
  }
  form {
    width: 100%;
    height: 5vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  input {
    text-align: center;
    border-radius: 23px;
    width: 80vw;
  }

  button {
    border: 2px solid white;
    color: white;

    padding: 20px;
    width: fit-content;
    height: 100%;
    border-radius: 50px;
    background: linear-gradient(45deg, blue, cyan);
    margin: 10px;
  }

  div {
    height: 100px;
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
</style>
