<script>
import  numberInput  from "./components/input.vue";
import  Selector  from "./components/selector.vue";

export default {
  components: {numberInput,Selector,},
  data(){
    return{
      amount:0,
      cryptoFirst:'',
      cryptoSecond:''
    }
  },
  methods:{
    changeAmount(val){
      this.amount = val
    },
    setFirstCrypto(val){
      this.cryptoFirst = val
    },
    setSecondCrypto(val){
      this.cryptoSecond = val
    }
  }
}
</script>

<template>
  <h1>Crypto Exchange</h1>
  <numberInput />
  <div className="selector-box">
    <Selector :setCrypto="setFirstCrypto"/>
    <Selector :setCrypto="setSecondCrypto"/>
  </div>
</template>

<style >
.selector-box{
  display: flex;
  justify-content: space-evenly ;
  margin: 0 auto;
}
</style>
