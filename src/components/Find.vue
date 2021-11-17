<template>
  <div >
    <p>キーワード検索:</p><input class="form-control" v-model="find_word">
    <button class="btn btn-info mt-2 text-white" v-on:click="find">検索する</button>
  </div>
</template>

<script>
export default {
  name: "Find",
  data(){
      return{
          find_word:"",
      }
  },
  methods: {
      find(){
          const word = this.find_word;
          this.$emit("find-event",word);
      }
  },

}
</script>