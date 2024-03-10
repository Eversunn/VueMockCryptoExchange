
<template>
        <ul>
            <li @click="selectItem('BTC')" :className="current =='BTC' ? 'active' : ''">BTC</li>
            <li @click="selectItem('ETH')" :className="current =='ETH' ? 'active' : ''">ETH</li>
            <li @click="selectItem('USDT')" :className="current =='USDT' ? 'active' : ''">USDT</li>
        </ul>
</template>

<script>
export default {
    props:{
        setCrypto:{
            type:Function,
            required:true
        }

    },
    data(){
        return{
            current:''
        }
    },
    methods:{
        selectItem(val){
            this.setCrypto(val)
            this.current = val
        }
    }
}

</script>

<style scoped>
ul{
    list-style: none;
    width: 200px;
    padding: 0;
    border-radius: 3px;
    border: 3px solid black;
}
li{
    display: block;
    background: rgb(34, 34, 34);
    color: white;
    padding: 20px 0;
}
li:hover, li:active{
    background: rgb(228, 121, 121);
    cursor: pointer;

}
</style>
