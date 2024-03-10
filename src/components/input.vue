

<template>
    <input min="0" type="number" @input="changeAmount($event.target.value)">
</template>
<script>
export default {
    props:{
        changeAmount:{
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
</style>
