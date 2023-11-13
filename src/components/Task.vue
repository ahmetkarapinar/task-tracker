<template>
  <div
    @dblclick="$emit('toggle-reminder')"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="onDelete()" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "task-comp",
  props: {
    task: Object,
  },
  methods: {
    onDelete() {
      this.$emit("delete-task");
      console.log("Clicked from deepest comp");
    },
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
<style scope>
.fas {
  color: red;
}

.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  border-left: 5px solid rgb(128, 51, 0);
  cursor: pointer;
}

.task.reminder {
  border-left: 5px solid green;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
