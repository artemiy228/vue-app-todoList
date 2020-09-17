<template>
  <div class="todo">
    <div class="todo__inner">
      <div class="todo__header">
        <div class="todo__title">Список задач</div>
      </div>
      <div class="todo__wrapper">
        <div class="todo__task--add">
          <input
            type="text"
            placeholder="Введите текс задачи..."
            v-model="currentTask"
            @keyup.enter="addTask"
          />
          <button class="todo__btn" @click="addTask">
            <img src="../assets/plus.svg" alt />
          </button>
        </div>
        <div class="todo__task--new">
          <ul class="todo__list">
            <li v-for="task in tasks" :key="task" class="todo__task">
              <span class="todo__content">
                <input type="checkbox" name="check" @click="task.done = !task.done" />
                <p :class="{strike: task.done}">{{ task.text }}</p>
              </span>
              <img src="../assets/trash.svg" @click="deleteTask(task.id)" />
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentTask: "",
      tasks: [
        { text: "Todo 1", done: false, id: 1 },
        { text: "Todo 2", done: false, id: 2 },
      ],
    };
  },
  components: {},
  methods: {
    addTask() {
      if (this.currentTask) {
        this.tasks.push({
          text: this.currentTask,
          done: false,
          id: this.tasks.length + 1,
        });
        this.currentTask = "";
      }
    },
    deleteTask(taskId) {
      this.tasks = this.tasks.filter((task) => task.id !== taskId);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" >
.strike {
  text-decoration: line-through;
}
img {
  cursor: pointer;
}
.todo {
  display: flex;
  min-height: 330px;
  display: flex;
  justify-content: center;
  margin-top: 20px;
  &__header {
    height: 20px;
    background-color: #c792df;
    padding: 10px 15px;
    border-radius: 6px 6px 0 0;
    width: 300px;
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
    }
  }
  &__task {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 15px;
    padding-bottom: 0;
    border-bottom: 1px solid #efefef;

    img {
      width: 15px;
      height: 15px;
    }
  }
}
</style>
