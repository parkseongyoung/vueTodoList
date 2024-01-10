<template>
  <div>
    <!-- 텍스트 필드  
    v-model을 통해서 뷰인스턴스와 연결-->
    <textarea
      id="addtext"
      class="writeList"
      v-model="memo"
      placeholder="투두리스트를 입력해주세요."
    ></textarea>
    <!-- 추가버튼 -->
    <button class="addlist" @click="listadd">추가하기</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      memo: null,
    };
  },
  methods: {
    listadd() {
      console.log("리스트 추가하기");
      if (this.memo === null) {
        alert("할일을 입력해주세요.");
      } else {
        this.$emit("memoListAdd", this.memo);
        this.memo = "";
      }
    },
  },
};
</script>
