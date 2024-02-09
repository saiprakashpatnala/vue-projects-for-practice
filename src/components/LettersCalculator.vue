<script setup>
import {ref} from "vue"
let word=ref("")

const wordHandler=(e)=>{
    word.value=e.target.value
}

</script>

<template>
    <div>
        <h1>Letters Calculator</h1>
        <input type="text" v-model="word" v-keypress="wordHandler"/>
        <p>Word Length :<span>{{ word.length }}</span></p>
    </div>
</template>