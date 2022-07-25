<script>
import 'bulma/css/bulma.css';

let inputCounts=1;
let quantity=[],price=[],cost=[],tquantity=0,tprice=0
let average=0;

function incinputCount(){
  inputCounts++;
}
function totalquantity(){
    for (let i = 0; i < quantity.length; i++) {
      tquantity += parseFloat(quantity[i]);
    } 
}
function totalamount(){
  for (let i = 0; i < price.length; i++) {
    tprice += parseFloat(price[i]) * parseFloat(quantity[i]);
    }
}
function avgprice(){
  average=0;
  tquantity=0;
  tprice=0;
  totalamount()
  totalquantity()
  average = tprice / tquantity;
}
</script>
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
