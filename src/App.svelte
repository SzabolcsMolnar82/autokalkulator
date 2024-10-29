
<div class="body">
  <h1>Autó Hatótáv Kalkulátor</h1>
  <img src="./src/assets/car-icon.png" alt="car">
  
  <div class="beviteli-mezok">
    <label for="tankoltUzemanyag">Tankolt üzemanyag mennyisége (liter):</label>
    <input type="number" bind:value={tankoltUzemanyag} id="tankoltUzemanyag" min="0" />
  </div>

  <div class="beviteli-mezok">
    <label for="megtettUt">Megtett út (km):</label>
    <input type="number" bind:value={megtettUt} id="megtettUt" min="0" />
  </div>

  <div class="beviteli-mezok">
    <label for="atlagFogyasztas">Átlag fogyasztás (liter/100 km):</label>
    <input type="number" bind:value={atlagFogyasztas} id="atlagFogyasztas" min="0" />
  </div>
  
  <button on:click={szamolas}>Számolás</button>

  {#if atlagFogyasztas > 0 && tankoltUzemanyag > 0}
    <div class="eredmeny">
      <p>Megtehető távolság: {megtehetoTav.toFixed(2)} km</p>
    </div>
  {/if}
</div>
<div>
  
</div>

<script>
  let tankoltUzemanyag = 0;
  let megtettUt = 0;
  let atlagFogyasztas = 0;
  let megtehetoTav = 0;

  function szamolas() {
    if (atlagFogyasztas > 0) {
      megtehetoTav = (tankoltUzemanyag / atlagFogyasztas) * 100;
    }
  }
</script>


<style>
  .body {
    background-color: #2A3439;
    color: #AAA9AD;
    padding: 20px;
    border-radius: 8px;
    max-width: 400px;
    margin: auto;
    text-align: center;
  }
  img {
    border-radius: 25px;
      
  }
  .beviteli-mezok {
    margin-bottom: 15px;
  }
  label {
    color: #848689;
    display: block;
    margin-bottom: 5px;
  }
  input {
    width: 100%;
    border: 3px solid #5B676D;
    border-radius: 4px;
    background-color: #848689;
    color: #2A3439;
    text-align: center;
  }
  .eredmeny {
    margin-top: 20px;
    background-color: #5B676D;
    padding: 10px;
    border-radius: 4px;
  }
</style>

