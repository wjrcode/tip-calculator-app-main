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
          <!-- <div class="tip-calculator__tip-percent"> -->
            <input class="tip-calculator__tip-value" placeholder="Custom" />
          <!-- </div> -->
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
        <button class="tip-calculator__button">
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
@import url('https://fonts.googleapis.com/css2?family=Space+Mono&display=swap');

body{
  background-color: hsl(185, 41%, 84%);
  font-family: "Space Mono";
}

main{
 text-align: center;
 
}

input{
  font-family: "Space Mono";
}

.tip-calculator{
  text-align: start;
  display: flex;
  padding: 1.5rem;
  border-radius: 1rem;
  max-width: 40rem;
  background-color: white;
  margin: 0 auto;
  box-sizing: border-box;
}

.tip-calculator__functional{
  width: 50%;
  padding-right: 1.5rem;
  box-sizing: border-box;
}

.tip-calculator__visual{
  background-color: hsl(183, 100%, 15%);
  box-sizing: border-box;
  width: 50%;
  padding: 2rem;
  border-radius: 1rem;
}

.tip-calculator__tittle{
  font-size: 16px;
  margin: 0;
  color: hsl(186, 14%, 43%);
}

.tip-calculator__input{
  width: 100%;
  border: none;
  background-color: hsl(189, 41%, 97%);
  outline: none;
  font-weight: 700;
  padding: 0.5rem;
  text-align: end;
}

.tip-calculator__tip-selector{
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.tip-calculator__tip-percent{
  text-align: center;
  width: 5rem;
  color: white;
  background-color: hsl(183, 100%, 15%);
  border-radius: 0.5rem;
  padding: 0.5rem;
  box-sizing: border-box;
  font-weight: bold;
}

.tip-calculator__tip-value{
  text-align: center;
  width: 5rem;
  font-weight: bold;
  color: hsl(186, 14%, 43%);
  background-color: hsl(189, 41%, 97%);
  box-sizing: border-box;
  border: 0;
  outline: none;
  border-radius: 0.5rem;
}

.tip-calculator__visual{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.tip-calculator__display{
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.tip-calculator__text-title{
  color: white;
  font-weight: bold;
}

.tip-calculator__text-sub-title{
  color: hsl(186, 14%, 43%);
  font-size: 12px;
  font-weight: bold;
}

.tip-calculator__total{
  font-size: 24px;
  font-weight: bold;
  color:hsl(172, 67%, 45%)
}

.tip-calculator__button{
  width: 100%;
  border: 0;
  background-color:hsl(172, 67%, 45%);
  border-radius: 0.5rem;
  padding: 0.5rem;
  color: hsl(183, 100%, 15%);
  font-weight: bold;
}

</style>
