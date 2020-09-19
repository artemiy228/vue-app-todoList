<template>
  <div class="auth">
    <div class="title">Authorization</div>

    <form>
      <input type="text" placeholder="Enter your name:" />
      <input type="password" placeholder="Enter your password:" />
    </form>
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
  input {
    width: 300px;
    margin: 0 auto;
    margin-bottom: 10px;
    padding: 10px;
    border: none;
  }
}
</style>