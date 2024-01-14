<template>
  <div class="home">
    <ol>
      <li v-for="x in data">{{ x.title }}
        <button v-on:click="seeDetail(x.id)"> See More</button>
      </li>
    </ol>
    <div v-if="dataDetail">
      {{ dataDetail }}
      <h1>{{ dataDetail.title }}</h1>
      <p>Job Description: </p>
      <!-- <div v-bind="dataDetail.description.txt"></div> -->
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import json from '../../data/no-auth.json'

export default{
  data(){
    return{
      data: null,
      dataDetail: null,
    }
  },
  methods:{
    seeDetail(id){
      this.dataDetail = this.data.find((detail) => detail.id == id)
    }
  },
  mounted(){
    this.data = json
    console.log(json)
    
  }
}
</script>
