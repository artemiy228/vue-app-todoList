<template>
  <div class="reg">
    <div class="title">Registration</div>
    <div class="wrapper">
      <form>
        <input type="text" placeholder="Enter your name:" />
        <input type="password" placeholder="Enter your password:" />
        <input type="email" placeholder="Enter your email:" />
        <button>Enter</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.title {
  font-size: 22px;
  margin: 10px 0;
}
.wrapper {
  margin: 0 auto;
  display: flex;
  justify-content: center;
}
form {
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin: 0 auto;
  button {
    padding: 10px;
    width: 100px;
  }
  input {
    width: 300px;
    margin-bottom: 10px;
    padding: 10px;
    border: none;
  }
}
</style>