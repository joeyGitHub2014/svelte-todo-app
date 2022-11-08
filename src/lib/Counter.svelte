<script>

  import {onMount} from "svelte"

  const  todos= [
      {
        id: 1,
        name:"JOE ORLANDO",
        city:"LA",
        task: "FInish portfolio"
      }


    ]


  let count = 0
  const increment = () => {
    count += 1
  }

  /* $: declares a reactive property or statement*/
$: doubled = count * 2;

$: obj = {
   
      name:"joe",
      num :1
  
}

onMount( function(){
  console.log("component is  mounted")
 setTimeout(()=> console.log("run animation"), 5000)
})

</script>
<div>

</div>
<button on:click={increment}>
  count is {count}
  doubled is {doubled}
  obj name : <h1>{obj.name}  </h1> <p>and is number {obj.num} </p>
</button>

<button on:click={() =>{count--}}> Decrement {count} </button>
{#if count > 8 }
   <!-- content here -->
   <p class="greater"> Count is <b>GREATER</b> than 8</p>
   {:else}
   <p > Count is lower than 8</p>

{/if}
{#each todos as todo}
   <!-- content here -->
   <ul>
    <li>NAME: {todo.name} CITY: {todo.city}</li>
   </ul>
{/each}
<style>
  h1 {
    color:orange;
    font-size: 2rem;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }
  p {
    color:red;
    font-size: 1rem;
    font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif
  }
  .greater{
    color: aquamarine;
  }
</style>
