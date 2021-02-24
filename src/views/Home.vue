<template>
<div id="home">
  <input type="text" maxlength="7" v-model="inputZipcode"/>
  <button @click="GO">住所自動入力</button>
  <p>Address：{{this.name}}</p>
</div>
</template>

<script>
import axios from "axios";
export default{
  data(){
    return{
      inputZipcode:""
    }
  },
  methods:{
  async created(){
    const item = await axios.get(
      `https://apis.postcode-jp.com/api/v4/postcodes/?apikey=z9UKvOjwgzkU24DOKSj5YMxpvjNKnPYfyIfxtFB`
    );
    const codeData= item.data;
    this.zipcode = codeData.postcode;
    this.name= codeData.allAddress;
  },
  GO(){
    const input
    if((this.zipcode) == (inputcode)){

    }

  }
  }



}
</script>

