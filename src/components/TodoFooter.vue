<template>
  <div class="removeWrap">
    <button class="btnTodoAll" @click="clearTodo">모두삭제</button>
  </div>
</template>
<script>
export default {
  methods:{
    clearTodo() {
      this.$emit('removeAll');
      // localStorage.clear();
      // this.todoItems = [];
    }
  }
}
</script>
