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
            <li
              is="todo-item"
              v-for="task in tasks"
              :key="task.id"
              :task="task"
              @delete-task="deleteTask($event)"
            />
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
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
  components: {
    TodoItem,
  },
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
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
