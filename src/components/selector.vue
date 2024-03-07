


<template>
    <div>
        <h2>selector</h2>
        <ul>
            <li>BTC</li>
            <li>ETH</li>
            <li>USDT</li>
        </ul>
    </div>
</template>

<script>
export default {}

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
