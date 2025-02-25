<script lang="ts">
  export let cocktailData
</script>

<article>
  <div class="card-container">

    <div class="img-container">
      <img src={cocktailData.strDrinkThumb} alt={cocktailData.strDrink}/>
    </div>

    <div>
      <h4>{cocktailData.strDrink}</h4>
      <p>{cocktailData.strInstructions}</p>
    </div>

  </div>
</article>

<style>
  
</style>