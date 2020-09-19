<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="buttons">
      <button class="TODOLIST" @click="componentID = 'TodoList'">TODOLIST</button>
      <button class="Authorization" @click="componentID = 'FormAuth'">Authorization</button>
      <button class="Registration" @click="componentID = 'FormReg'">Registration</button>
    </div>

    <keep-alive>
      <component :is="componentID"></component>
    </keep-alive>
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import FormReg from "./components/FormReg";
import FormAuth from "./components/FormAuth";

export default {
  name: "App",
  data() {
    return {
      componentID: "TodoList",
    };
  },
  components: {
    TodoList,
    FormAuth,
    FormReg,
  },
};
</script>

<style lang="scss" >
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&display=swap");
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
body {
  background-color: #efefef;
}
.buttons {
  button {
    padding: 10px;
    margin-right: 10px;
    border: none;
    border-radius: 5px;
    color: #fff;
    cursor: pointer;
  }
  .TODOLIST {
    background: rgb(85, 85, 85);
  }
  .Authorization {
    background: rgb(233, 82, 82);
  }
  .Registration {
    background: rgb(53, 23, 23);
  }
}
</style>
