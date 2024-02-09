<script setup>
import {ref} from "vue"
let balance=ref(4200000)

const withdrwMoney=(val)=>{
    balance.value=balance.value-val
}
</script>

<template>
    <div>
        <h1>S</h1>
        <p>Sai Praksh</p>
        <p>You Balance</p>
    <h1>{{balance}}</h1>
    <span>In Rupees</span>
    <div>
        <p>Withdraw</p>
        <p>Choose sun in rupees</p>
        <button @click="withdrwMoney(50)">50</button>
        <button @click="withdrwMoney(100)">100</button>
        <button @click="withdrwMoney(200)">200</button>
        <button @click="withdrwMoney(500)">500</button>
        
    </div>
    </div>
</template>