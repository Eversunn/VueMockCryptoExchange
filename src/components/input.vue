

<template>
    <input min="0" type="number" @input="changeAmount($event.target.value)" placeholder="Input Number">
    <br>
    <button @click="convert()">Convert</button>
</template>
<script>
export default {
    props:{
        changeAmount:{
            type:Function,
            required:true
        },
        convert:{
            type:Function,
            required:true
        }
    }
}
</script>


<style scoped>
input{
    outline: none;
    border-radius: 3px;
    border: 0;
    padding: 10px 15px;
    background: white;
    color: rgb(87, 87, 87);
}

button {
    margin-top: 40px;
    position: relative;
    padding: 15px 20px;
    color: white;
    text-transform: uppercase;
    cursor: pointer;
    background: blueviolet;
    border: 0;
    border-radius: 15px;
}
button:active {
    background: rgb(153, 93, 209);

}
</style>
