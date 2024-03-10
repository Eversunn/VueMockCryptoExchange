<script>
import  numberInput  from "./components/input.vue";
import  Selector  from "./components/selector.vue";
import CryptoConvert from "crypto-convert"
const convert = new CryptoConvert();

export default {
  components: {numberInput,Selector,},
  data(){
    return{
      amount:0,
      cryptoFirst:'',
      cryptoSecond:'',
      error:'',
      result:''
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
    },
    async convert(){
      if(this.amount <= 0){
        this.error = 'Input Number above 0'
        return
      }else if(this.cryptoFirst == ''||this.cryptoSecond == ''){
        this.error = 'Please Select Coins'
        return
      }else if(this.cryptoFirst == this.cryptoSecond){
        this.error = 'Please Select Different Coins'
        return
      }
      this.error=''
      await convert.ready()
      if(this.cryptoFirst =='BTC' && this.cryptoSecond == 'ETH'){
        this.result = convert.BTC.ETH(this.amount)
      }else if(this.cryptoFirst =='BTC' && this.cryptoSecond == 'USDT'){
        this.result = convert.BTC.USDT(this.amount)
      }else if(this.cryptoFirst =='ETH' && this.cryptoSecond == 'BTC'){
        this.result = convert.ETH.BTC(this.amount)
      }else if(this.cryptoFirst =='ETH' && this.cryptoSecond == 'USDT'){
        this.result = convert.ETH.USDT(this.amount)
      }else if(this.cryptoFirst =='USDT' && this.cryptoSecond == 'BTC'){
        this.result = convert.USDT.BTC(this.amount)
      }else if(this.cryptoFirst =='USDT' && this.cryptoSecond == 'ETH'){
        this.result = convert.USDT.ETH(this.amount)
      }
      }
    }
  }

</script>

<template>
  <h1>Crypto Exchange</h1>
  <numberInput :changeAmount="changeAmount" :convert="convert" />
  <p className="result">{{ result }}</p>
  <p v-if="error !=''" >{{ error }}</p>
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
p{
  color: red;
}
.result{
  font-size: 32px;
  color: white;
  -webkit-text-stroke: 0.8px;
  -webkit-text-stroke-color: black;
}
</style>
