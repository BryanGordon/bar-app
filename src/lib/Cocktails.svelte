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

  article {
    margin: 25px;
    justify-items: center;
    width: 50%;
  }
  
  .card-container {
    width: 60%;
    background-color: rgb(55, 55, 55);
    padding: 15px;
    border-radius: 20px;
  }

  img {
    width: 350px;
    height: 400px;
    border-radius: 5px;
  }

</style>