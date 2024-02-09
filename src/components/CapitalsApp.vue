<script setup>
import { ref } from 'vue';

const countryAndCapitalsList = [
  {
    id: 'NEW_DELHI',
    capitalDisplayText: 'New Delhi',
    country: 'India',
  },
  {
    id: 'LONDON',
    capitalDisplayText: 'London',
    country: 'United Kingdom',
  },
  {
    id: 'PARIS',
    capitalDisplayText: 'Paris',
    country: 'France',
  },
  {
    id: 'KATHMANDU',
    capitalDisplayText: 'Kathmandu',
    country: 'Nepal',
  },
  {
    id: 'HELSINKI',
    capitalDisplayText: 'Helsinki',
    country: 'Finland',
  },
];

const selectedCapital = ref(countryAndCapitalsList[0].id);

const capital = ref(countryAndCapitalsList[0].capitalDisplayText);

const selectCapital = (event) => {
  const selectedId = event.target.value;
  selectedCapital.value = selectedId;
  const selectedCapitalObj = countryAndCapitalsList.find(item => item.id === selectedId);
  capital.value = selectedCapitalObj.capitalDisplayText;
};

console.log(selectedCapital.value)
</script>

<template>
  <div>
    <select @change="selectCapital" v-model="selectedCapital">
      <option v-for="item in countryAndCapitalsList" :key="item.id" :value="item.id">
        {{ item.country }}
      </option>
    </select>
    <span>is Capital Of?</span>
    <p>{{ capital }}</p>
  </div>
</template>


