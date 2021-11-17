<template>
  <div id="app" class="mx-auto mt-4" style="width: 400px">
    <h1>楽天APIで書籍を検索</h1>
    <Find v-on:find-event="find_event" />
    <div style="margin-top:20px">
      <Book v-bind:result_word="result" />
    </div>
  </div>
</template>

<script>
import Book from './components/Book.vue'
import Find from './components/Find.vue'

export default {
  name: 'App',
  components: {
    Book,
    Find
  },
  data(){
    return{
      result:""
    }
  },
  methods: {
    find_event(find_word){
      this.result = find_word;
    }
  },
}
</script>

