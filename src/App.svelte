
<main>
  <section class="hero is-link">
    <div class="hero-body">
      <p class="title">
        Average Price Calculator
      </p>
      
    </div>
  </section>
  <hr>
<div class="container">
  <div class="columns">
    <div class="column is-two-thirds">
      <table class="table is-hoverable is-fullwidth">
        <thead>
          <th>S.No</th>
          <th>Quantity</th>
          <th>Price</th>
        </thead>
        <tbody>
          {#each Array(inputCounts) as number,index}
          <tr>
            <td>{index}</td>
            <td><input  class="input is-rounded is-small" type="number" bind:value={quantity[index]}></td>
            <td><input  class="input is-rounded is-small" type="number" bind:value={price[index]}></td>
          </tr>
          
          {/each}
          <tr>
            <td><button class="button is-black" on:click={incinputCount} >Add Orders</button></td>
          </tr>

        </tbody>
      </table>
    </div>
    <div class="column center">
      <strong>Avg.Price:</strong><h1 class="is-size-1">{average.toFixed(2)}</h1>
      <button class="button is-black" on:click={avgprice} >Calculate Average price</button>
    </div>
    
  </div>
 
</div>
</main>

<style>
 .center{
  display: grid;
  place-items: center;
 }
</style>
