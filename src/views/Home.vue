<template>
  <div class="container">
    <Header />
    <div>
        <form>
            <input v-model.trim="name1" type="text" name="title" placeholder="Enter Seed ID" required>
            <input v-on:click="hello" type="submit" value="Search" class="btn">
        </form>
    </div>
    <h3>information: </h3>
    <div v-if="isTrue">
      {{name2}}
    </div>
  </div>
  <div class="container1">
    <p>
      <b>How to use</b><br>
      <br>
      You will need to enter the seed ID from the Coffeeshop.
      (You can ask staffs from the coffeeshop to obtain ID)
      Enter the seed ID and click search.
      In the information, the origins of the coffee seed will display.
    </p>
  </div>
  <div>

    copyright©
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
export default {
  name: 'Home',
  components: {
    Header
  },
  data: function () {
    return {
      name1: '',
      name2: '',
      isTrue: false
    }
  },
  methods: {
    hello () {
      this.isTrue = !this.isTrue
      this.name2 = this.name1
      console.log(this.isTrue)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
p{
  text-align: left;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid #42b983;
  padding: 30px;
  border-radius: 5px;
}
.container1 {
  max-width: 200px;
  margin: 10px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid #42b983;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #42b983;
  color: black;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}

h3 {
  margin-top: 10px;
}
#preview {
    box-sizing:border-box;
    padding: 10px 20px;
    border: 1px dotted black;
    margin: 30px 0;
}

form {
    display: flex;
}

input[type="text"] {
    flex: 10;
    padding: 5px;
}

input[type="submit"] {
    flex:2
}
</style>
