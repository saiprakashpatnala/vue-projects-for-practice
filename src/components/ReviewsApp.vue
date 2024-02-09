<script setup>

import {ref,computed} from "vue"
let index=ref(0)
const reviewsList = [
  {
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/wade-warren-img.png',
    username: 'Wade Warren',
    companyName: 'Rang',
    description:
      'The most important thing I learnt is that nothing is a failure, but what we learn from that is a rich and rewarding experience.',
  },
  {
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/adrian-williams-img.png',
    username: 'Adrian Williams',
    companyName: 'WheelO',
    description:
      'Coming to Startup School is the best thing that has happened to me. I wish every startup in the country should get this opportunity.',
  },
  {
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/sherry-jhonson-img.png',
    username: 'Sherry Johnson',
    companyName: 'MedX',
    description:
      'I am glad to have such experienced mentors guiding us in every step through out the 4 weeks. I have improved personally and developed many interpersonal skills.',
  },
  {
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/ronald-jones-img.png',
    username: 'Ronald Jones',
    companyName: 'Infinos Tech',
    description:
      'I am really loving the way how mentors are taking care of us, the way they are explaining big theories with lots of case studies and innovative methods.',
  },
]



const increment=()=>{
    if(index.value>=0 && index.value<reviewsList.length-1){
         index.value=index.value+1
    }
}

const decrement=()=>{
    if(index.value>0){
        index.value=index.value-1
    }
}

const kk=computed(()=>{
    return reviewsList[index.value]
})

</script>

<template>
    <h1>Users Reviews</h1>
    <button @click="increment">⏭️</button>
    <img :src=kk.imgUrl :alt=kk.username />
    <h1>{{ kk.username }}</h1>
    <span>{{ kk.companyName }}</span>
    <p>{{ kk.description }}</p>
    <button @click="decrement">⏮️</button>
</template>