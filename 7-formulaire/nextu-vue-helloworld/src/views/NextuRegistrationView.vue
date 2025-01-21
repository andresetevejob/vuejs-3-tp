<script lang="ts" setup>
import {reactive} from "vue"
import type {Student} from "@/models/student"

const student:Student = reactive({
  name:'',
  lastName:'',
  theme:''
});
const themes = reactive([
  "Machine Learning",
  "LLM",
  "NoSql"
])
const onSubmit = ()=>{
  console.log(student.name)
  console.log(student.lastName);
  console.log(student.theme)
}
</script>
<template>
  <form @submit.prevent="onSubmit">
    <label for="fname">First Name</label>
    <input type="text" id="fname" name="firstname" placeholder="Your name.." v-model="student.name"/>
    <label for="lname">Last Name</label>
    <input type="text" id="lname" name="lastname" placeholder="Your last name.." v-model="student.lastName"/>
    <label for="theme">Filière</label>
    <select id="theme" name="theme" v-model="student.theme">
      <option v-for="(item,i) in themes" :key="i" :value="item">{{item}}</option>
    </select>
    <button type="submit">Enregistrer</button>
  </form>
</template>
<style scoped>
input[type='text'],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type='submit'] {
  width: 100%;
  background-color: #4caf50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type='submit']:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>
