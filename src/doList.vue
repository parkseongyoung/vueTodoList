<template>
  <div class="listCard">
    <li v-for="(list, index) in memoList" :key="index">
      <label
        ><span>{{ list.memo }}</span> <span>{{ list.status }}</span></label
      >
      <span
        class="taskcompl"
        @click="$emit('taskcompl', index, 'done')"
        v-if="list.status === 'created'"
        >....완료</span
      >
      <span
        class="taskrecheck"
        @click="$emit('taskcompl', index, 'created')"
        v-if="list.status === 'done'"
        >....완료아님</span
      >
      <span class="taskDel" @click="$emit('taskDel', index)">....삭제</span
      ><!-- 삭제하기 -->
    </li>
  </div>
</template>

<script>
export default {
  props: ["memoList"],
};
</script>

<style scoped></style>
