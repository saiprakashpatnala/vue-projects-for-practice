<script setup>

import {ref} from "vue"


const HEADS_IMG_URL = 'https://assets.ccbp.in/frontend/react-js/heads-img.png'

const TAILS_IMG_URL = 'https://assets.ccbp.in/frontend/react-js/tails-img.png'

let imgUrl=ref(HEADS_IMG_URL)
let toss=ref(0)
let heads=ref(0)
let tails=ref(0)

const tossStart=()=>{
    toss.value=toss.value+1
    let random=Math.ceil(Math.random()*100)
    if(random%2===0){
        heads.value=heads.value+1
        imgUrl.value=HEADS_IMG_URL
    }
    else{
        tails.value=tails.value+1
        imgUrl.value=TAILS_IMG_URL
    }
}
</script>

<template>
    <div>
        <img class="picture" :src=imgUrl alt="toss"/>
        <p>Tosses:{{ toss }}</p>
        <p>Heads:{{ heads }}</p>
        <p>Tails:{{ tails }}</p>
    </div>

    <button @click="tossStart">Toss</button>
</template>

<style scoped>
.picture{
    height: 120px;
    width: 200px;
}
</style>