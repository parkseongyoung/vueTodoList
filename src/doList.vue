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
      <!-- <span
        class="changetext"
        @click="memoEdit(list.memo, index)"
        v-if="list.status === 'created'"
        >....변경</span
      > -->
      <!-- 이벤트버스를 활용하여 메모변경하기 -->
    </li>
  </div>
</template>

<script>
// import { eventBus } from "./main";

export default {
  props: ["memoList"],
  // methods: {
  //   memoEdit(memo, index) {
  //     eventBus.memoEdit(memo, index);
  //   },
  // },
};
</script>

<style scoped></style>
