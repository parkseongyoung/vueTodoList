<template>
  <div class="listCard">
    <li v-for="(list, index) in memoList" :key="index">
      <label
        ><span>{{ list.memo }}</span> <span>{{ list.status }}</span></label
      >
      <span class="taskcompl" @click="$emit('taskcompl', index, 'done')"
        >완료</span
      >
      <span class="taskrecheck" @click="$emit('taskcompl', index, 'created')"
        >완료아님</span
      >
      <span class="taskDel" @click="$emit('taskDel', index)">삭제</span>
    </li>
  </div>
</template>

<script>
export default {
  props: ["memoList"],
};
</script>

<style scoped></style>
