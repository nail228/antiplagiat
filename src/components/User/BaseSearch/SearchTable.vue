<template>

  <table class="base">
    <thead>
    <th v-for="(dat) of Object.keys(documents[0])" :key="dat.id" >
      <tr>{{dat}}</tr>
    </th>
    </thead>
    <tbody>
    <tr v-for="(data) of documents" :key="data.id">
      <td v-for="(i) of Object.values(data)" :key="i.id">{{i}}</td>
    </tr>
    </tbody>
  </table>
</template>
/* eslint-disable */
<script>
import store from '@/store';
/* eslint-disable */

export default {

  name:"SearchTable",
  props:{
    documents:{
      type:Array
    }
  },
  setup(props){


    async function dataAction(id){
      const action=await store.dispatch('downloadDoc',{id})
      return action
    }
  return{}
  }
}
</script>

<style scoped>
.base{
  position: relative;
  display: table;
  tab-size: 800px;
}
.btn-table{
  height: 25px;
  width:100px;
  background: #2615E4;
  color:#FFFFFF;
  border-radius: 5px;
}

</style>