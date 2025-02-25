<script lang="ts">
  import axios from 'axios'
  import Cocktails from './Cocktails.svelte';

  let cocktails = []
  let cocktailName = ''

  const getDrinks = async (cocktailSearch: string = 'margarita') => {
    const { data } = await axios.get(`https://www.thecocktaildb.com/api/json/v1/1/search.php?s=${cocktailSearch}`)

    cocktails = data.drinks
  }

  let promise = getDrinks()

  const handleSubmit = () => {
    promise = getDrinks(cocktailName)
  }

</script>

<section>
  <header>
    <h1>Search cocktails</h1>
  </header>

  <div>
    <input type="text"
      placeholder="bloody mary"
      bind:value={cocktailName}
    >
    <button on:click={handleSubmit()} type="submit">Search by liquor</button>
  </div>

  <article>
    {#await promise}
      Loading...
    {:then}
      {#each cocktails as item}
        <Cocktails cocktailData={item}/>
      {/each}
      
    {/await}
  </article>

</section>

<style>

</style>