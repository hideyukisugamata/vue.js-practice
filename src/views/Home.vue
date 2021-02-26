<template>
<div id="home">
  <input type="text" maxlength="7" v-model="inputZipcode"/>
  <button @click="GO">住所自動入力</button>
  <p>Address：{{name}}</p>
</div>
</template>

<script>
import axios from "axios";
export default{
  data(){
    return{
      inputZipcode:"",
      name:""
    }
  },
  methods:{
  async GO(){
    const item = await axios.get(
      `https://apis.postcode-jp.com/api/v4/postcodes/${this.inputZipcode}/?apikey=z9UKvOjwgzkU24DOKSj5YMxpvjNKnPYfyIfxtFB`
    );
    const codeData= item.data[0]

    console.log(item)

    this.name= codeData.allAddress

    console.log(name);
  
  }
  }
};

  
  




</script>

