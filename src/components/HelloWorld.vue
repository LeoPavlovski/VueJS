<template>
  <div id="app">
    <div>
      <label for="goal">Goal</label>
      <input type="text" id="goal" v-model="enteredValue"/>
      <button id="btn" v-on:click="addGoal">Add Goal</button>
    </div>
    <ul id="list">
      <li v-for="goal in goals" v-bind:key="goal">
        {{goal}}
      </li>
    </ul>
  </div>
</template>

<script>
export default{
  data(){
    return{
      goals:[],
      enteredValue:'',
    }
  },
  //holds the object, methods, function that are callable from the HTML code
  methods:{
    addGoal(){
      this.goals.push(this.enteredValue)
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

#app {
  margin: 3rem auto;
  max-width: 40rem;
  padding: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}

label, input {
  margin-bottom: 0.5rem;
  display: block;
  width: 100%;
}

label {
  font-weight: bold;
}

ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}

li {
  margin: 1rem 0;
  padding: 1rem;
  border: 1px solid #ccc;
}
</style>
