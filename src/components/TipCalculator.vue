<template>
  <img src="../images/logo.svg" alt="Website logo" class="logo" />
  <div class="tip-calculator">
    <div class="tip-calculator__functional">
      <div>
        <div class="tip-calculator__header-input">
          <h1 class="tip-calculator__tittle">Bill</h1>
          <div class="tip-calculator__error-message" v-if="bill === 0">Can't be zero</div>
        </div>
        <input class="tip-calculator__input tip-calculator__input--dollar"
          :class="bill === 0 ? 'tip-calculator__input--error' : ''" placeholder="0" v-model="bill" type="number" />
      </div>
      <div>
        <div class="tip-calculator__header-input">
          <h2 class="tip-calculator__tittle">Select Tip %</h2>
          <div class="tip-calculator__error-message" v-if="tipSelected === 0">Can't be zero</div>
        </div>
        <div class="tip-calculator__tip-selector">
          <div class="tip-calculator__tip-percent" @click="tipSelected = 5" :class="selectTipPercent(5)">
            5%
          </div>
          <div class="tip-calculator__tip-percent" @click="tipSelected = 10" :class="selectTipPercent(10)">
            10%
          </div>
          <div class="tip-calculator__tip-percent" @click="tipSelected = 15" :class="selectTipPercent(15)">
            15%
          </div>
          <div class="tip-calculator__tip-percent" @click="tipSelected = 25" :class="selectTipPercent(25)">
            25%
          </div>
          <div class="tip-calculator__tip-percent" @click="tipSelected = 50" :class="selectTipPercent(50)">
            50%
          </div>
          <!-- <div class="tip-calculator__tip-percent"> -->
          <input class="tip-calculator__input" placeholder="Custom"
            :class="tipSelected === 0 ? 'tip-calculator__input--error' : ''" v-model="tipSelected" type="number">
          <!-- </div> -->
        </div>
      </div>
      <div>
        <div class="tip-calculator__header-input">
          <h3 class="tip-calculator__tittle">Number of People</h3>
          <div class="tip-calculator__error-message" v-if="numberPeople === 0">Can't be zero</div>
        </div>
        <input class="tip-calculator__input tip-calculator__input--person"
          :class="numberPeople === 0 ? 'tip-calculator__input--error' : ''" placeholder="0" v-model="numberPeople"  type="number"/>
      </div>
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
          ${{ tip }}
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
          ${{ total }}
        </div>
      </div>
      <button class="tip-calculator__button" @click="reset()" :disabled="total == 0"
        :class="total == 0 ? 'tip-calculator__button--disable' : ''">
        Reset
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    msg: String
  },
  data() {
    return {
      bill: '',
      tipSelected: '',
      numberPeople: ''
    }
  },
  computed: {
    tip() {
      if (this.bill > 0 && this.numberPeople > 0 && this.tipSelected)
        return ((this.bill * (this.tipSelected / 100)) / this.numberPeople).toFixed(2)
      else
        return '0.00'

    },
    total() {
      if (this.bill > 0 && this.numberPeople > 0 && this.tipSelected)
        return ((this.bill / this.numberPeople) + ((this.bill * (this.tipSelected / 100)) / this.numberPeople)).toFixed(2)
      else
        return '0.00'
    }
  },
  methods: {
    selectTipPercent(percent) {
      if (percent == this.tipSelected) return "tip-calculator__tip-percent--selected"
    },
    reset() {
      this.bill = ''
      this.tipSelected = ''
      this.numberPeople = ''
    }
  }
}
</script>

<style>
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type=number] {
  -moz-appearance: textfield;
}

main {
  text-align: center;
}

.logo {
  margin-bottom: 2rem;
}

input,
button {
  font-family: "Space Mono";
}

.tip-calculator {
  text-align: start;
  display: flex;
  padding: 1.5rem;
  border-radius: 1rem;
  max-width: 45rem;
  background-color: white;
  margin: 0 auto;
  box-sizing: border-box;
  gap: 1rem;
}

.tip-calculator__functional {
  width: 50%;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.tip-calculator__visual {
  background-color: hsl(183, 100%, 15%);
  box-sizing: border-box;
  width: 50%;
  padding: 2rem;
  border-radius: 1rem;
}

.tip-calculator__tittle {
  font-size: 16px;
  margin: 0 0 0.5rem 0;
  color: hsl(186, 14%, 43%);
}

.tip-calculator__header-input {
  display: flex;
  justify-content: space-between;
}

.tip-calculator__error-message {
  color: hsl(0, 80%, 70%);
  font-weight: bold;
}


.tip-calculator__input {
  border: none;
  outline: none;
  font-size: 20px;
  font-weight: bold;
  padding: 0.5rem;
  text-align: end;
  color: hsl(183, 100%, 15%);
  background-color: hsl(189, 41%, 97%);
  border-radius: 0.5rem;
  width: 100%;
  box-sizing: border-box;
}

.tip-calculator__input:focus:not(.tip-calculator__input--error) {
  outline: 2px solid hsl(172, 67%, 45%);
}

.tip-calculator__input--error {
  outline: 2px solid hsl(0, 80%, 70%);

}

.tip-calculator__input--dollar {
  background-image: url(../images/icon-dollar.svg);
  background-repeat: no-repeat;
  background-position: 15px 15px;
}

.tip-calculator__input--person {
  background-image: url(../images/icon-person.svg);
  background-repeat: no-repeat;
  background-position: 15px 15px;
}

.tip-calculator__tip-selector {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
}

.tip-calculator__tip-percent {
  text-align: center;
  width: 100%;
  color: white;
  background-color: hsl(183, 100%, 15%);
  border-radius: 0.5rem;
  padding: 0.5rem;
  box-sizing: border-box;
  font-weight: bold;
}

.tip-calculator__tip-percent--selected {
  color: hsl(183, 100%, 15%);
  background-color: hsl(172, 67%, 45%);
}

.tip-calculator__tip-value {
  text-align: center;
  width: 100%;
  font-weight: bold;
  color: hsl(186, 14%, 43%);
  background-color: hsl(189, 41%, 97%);
  box-sizing: border-box;
  border: 0;
  outline: none;
  border-radius: 0.5rem;
}

.tip-calculator__tip-value {
  font-weight: 700;
  outline: 2px solid hsl(172, 67%, 45%);
}


.tip-calculator__visual {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.tip-calculator__display {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.tip-calculator__text-title {
  color: white;
  font-weight: bold;
}

.tip-calculator__text-sub-title {
  color: hsl(186, 14%, 43%);
  font-size: 12px;
  font-weight: bold;
}

.tip-calculator__total {
  font-size: 32px;
  font-weight: bold;
  color: hsl(172, 67%, 45%)
}

.tip-calculator__button {
  width: 100%;
  border: 0;
  background-color: hsl(172, 67%, 45%);
  border-radius: 0.5rem;
  padding: 0.5rem;
  color: hsl(183, 100%, 15%);
  font-weight: 900;
  font-size: 16px;
  text-transform: uppercase;
}

.tip-calculator__button:hover:not(.tip-calculator__button--disable) {
  background-color: hsl(172, 67%, 80%);
}


.tip-calculator__button--disable {
  background-color: hsla(172, 67%, 45%, 0.397);
}

@media (max-width: 600px){
  .logo{
    margin-top: 2rem;
  }
  .tip-calculator{
    flex-direction: column;
  }
  .tip-calculator__functional{
    width: 100%;
  }

  .tip-calculator__tip-selector{
    grid-template-columns: repeat(2, 1fr);
  }

  .tip-calculator__visual{
    width: 100%;
    margin-top: 1rem;
  }

  .tip-calculator__visual{
    gap: 2rem;
  }

  input,button,.tip-calculator__tip-percent{
    height: 3rem;
  }

  .tip-calculator__tip-percent{
    display: flex;
    align-items: center;
    justify-content: center;
  }

}


</style>
