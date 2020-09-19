<template>
  <li class="task-me">
    <input type="checkbox" name="check" @click="task.done = !task.done" />
    <p :class="{strike: task.done}" class="task-me__text">{{ task.text }}</p>
    <button @click="$emit('delete-task', task.id)" class="task-me__button">
      <img src="../assets/trash.svg" />
    </button>
  </li>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
.task-me {
  display: flex;
  align-items: center;
  padding: 10px 40px 10px 20px;
  position: relative;
  overflow: hidden;

  &__text {
    color: #000;
    overflow: hidden;
    word-break: break-word;
    margin-left: 10px;
  }

  &__button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    right: 10px;
    border: none;
    background: none;
  }
}

//
.strike {
  text-decoration: line-through;
}
img {
  cursor: pointer;
}
.todo {
  display: flex;
  justify-content: center;
  margin-top: 20px;
  &__header {
    height: 45px;
    background-color: #c792df;
    padding: 10px 15px;
    border-radius: 6px 6px 0 0;
    width: 330px;
  }
  &__title {
    font-size: 16px;
    color: #fff;
    text-align: left;
  }
  &__wrapper {
    background-color: #fff;
    box-shadow: 12px 12px 20px 1px rgba(50, 50, 65, 0.2);
    max-width: 330px;
    min-height: 350px;
  }
  &__list {
    padding: 0;
    margin: 0;
    max-width: 330px;
  }
  &__task--add {
    display: flex;
    justify-content: space-between;
    padding: 15px;
    padding-bottom: 0;
    border-bottom: 1px solid #efefef;
    input {
      padding: 5px;
      border: none;
      margin-bottom: 10px;
    }
    button {
      border: none;
      background: none;
      padding: 0;
      img {
        width: 15px;
        height: 15px;
      }
    }
  }
  &__content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    p {
      margin-left: 10px;
      max-width: 100px;
    }
  }
  &__task {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 15px;
    padding-bottom: 0;
    border-bottom: 1px solid #efefef;
    max-width: 330px;
    button {
      border: none;
      background: none;
    }
    img {
      width: 15px;
      height: 15px;
      margin-left: 10px;
    }
  }
}
</style>