<template>
  <main>
    <img src="../images/logo.svg" alt="Website logo" />
    <div class="tip-calculator">
      <div class="tip-calculator__functional">
        <h1 class="tip-calculator__tittle">Bill</h1>
        <input class="tip-calculator__input" />
        <h2 class="tip-calculator__tittle">Select Tip %</h2>
        <div class="tip-calculator__tip-selector">
          <div class="tip-calculator__tip-percent">
            5%
          </div>
          <div class="tip-calculator__tip-percent">
            10%
          </div>
          <div class="tip-calculator__tip-percent">
            15%
          </div>
          <div class="tip-calculator__tip-percent">
            25%
          </div>
          <div class="tip-calculator__tip-percent">
            50%
          </div>
          <div class="tip-calculator__tip-percent">
            <input class="tip-calculator__tip-value" />
          </div>
        </div>
        <h3 class="tip-calculator__tittle">Number of People</h3>
        <input class="tip-calculator__input" />
      </div>
      <div class="tip-calculator__visual">
        <div class="tip-calculator__display">
          <div class="tip-calculator__display-text">
            <div class="tip-calculator__text-title">
              Tip Amount
            </div>
            <div class="tip-calculator__text-sub-title">
              / person
            </div>
          </div>
          <div class="tip-calculator__total">
            $4.27
          </div>
        </div>
        <div class="tip-calculator__display">
          <div class="tip-calculator__display-text">
            <div class="tip-calculator__text-title">
              Total
            </div>
            <div class="tip-calculator__text-sub-title">
              / person
            </div>
          </div>
          <div class="tip-calculator__total">
            $32.79
          </div>
        </div>
        <button>
          Reset
        </button>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<style>

body{
  background-color: hsl(185, 41%, 84%);
}

main{
 text-align: center;
}

.tip-calculator{
  display: flex;
  padding: 2rem;
  border-radius: 1rem;
  max-width: 30rem;
  background-color: white;
  margin: 0 auto;
}

.tip-calculator__functional{
  width: 50%;
}

.tip-calculator__visual{
  background-color: hsl(183, 100%, 15%);
  width: 50%;
  padding: 2rem;
  border-radius: 1rem;
}

</style>
