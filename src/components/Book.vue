<template>
  <div class="card">
    <h2>{{ result_word }}を検索しました</h2>
    <!--<img v-bind:src="image" alt="">
    <p>{{ itemPrice }}円</p>-->
  </div>
</template>

<script>
export default {
  name: 'Book',
  props:{
      result_word:String
  },
  data:()=>({
    title:"",
    image:"",
    itemPrice:""
  }),
  async mounted() {
    const url = 'https://app.rakuten.co.jp/services/api/BooksTotal/Search/20170404?format=json&keyword=WordPress&applicationId=1074634728112638150'
    const response = await fetch(url);
    const data = await response.json();
    
    console.log(data.Items[0])
    const first_item = data.Items[0].Item
    this.title = first_item.title
    this.image = first_item.smallImageUrl
    this.itemPrice = first_item.itemPrice
  },

}
</script>

