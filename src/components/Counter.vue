<template>
  <v-card>
    <v-text-field v-model="count" type="number" label="Current Number"/>
    <v-btn @click="add(input)">+</v-btn>
    <v-btn @click="subtract(input)">-</v-btn>
    <v-btn @click="multiply(input)">*</v-btn>
    <v-btn @click="divide(input)">/</v-btn>
    <v-text-field v-model="input" type="number" label="input"/>
    <v-slider
    v-model="input"
    :max="10000"
    :min="-10000"
    :step="0.01"
    label="input"
    thumb-label        
    ></v-slider>
  </v-card>
</template>

<script>
export default {
  name: 'Counter',
  data(){
      return{
          count: 0,
          input: 0,
          text: ''
      }
  },
  methods:{
      add(input){
          this.count += input;
      },
      subtract(input){
          this.count -= input;
      },
      multiply(input){
          this.count *= input;
      },
      divide(input){
          this.count /= input;
      }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
</style>
