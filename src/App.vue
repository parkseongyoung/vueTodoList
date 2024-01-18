<template>
  <div>
    <div>
      <div>
        <doList
          :memoList="memoList"
          @taskcompl="taskcompl"
          @taskDel="taskDel"
        />
      </div>
      <div>
        <ListAdd @memoListAdd="memoListAdd" />
      </div>
    </div>
  </div>
</template>

<script>
import doList from "./doList";
import ListAdd from "./ListAdd";

export default {
  components: {
    doList,
    ListAdd,
  },
  data() {
    return {
      memoList: [],
    };
  },
  methods: {
    memoListAdd(memo) {
      console.log("받았음");
      this.memoList.push({ memo: memo, status: "created" });
      //memoList안에  memo에는 내가 적은 메모랑 status는 created를 넣기
    },
    taskcompl(index, status) {
      this.memoList[index].status = status;
      // index번째거 status변경
    },
    taskDel(index) {
      this.memoList.splice(index, 1);
      // index번째거 1개 지우기
    },
  },
};
</script>

<style></style>
