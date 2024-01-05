<template>
  <div>
    <h1 class="IntroAnti">Аналитическая система выбора материалов</h1>
    <div class="Request-container">
      <p> Выберите устройство для которого вам нужно собрать печатную плату</p>
      <p>Данная система сделает вам подборку материалов для данного устройства</p>
      <button  @click="submitMobile"  class="action-btn" type="submit">Мобильный телефон</button>
      <button  @click="submitTv"  class="action-btn" type="submit">Телевизор</button>
    </div>
    <LoaderPage v-if="loading==true"/>

    <p class="center" v-else-if="!records.length">No records</p>

    <section v-else>
      <table class="base">
        <thead>
        <th v-for="(dat) of Object.keys(records[0])" :key="dat.id" >
          <tr>{{dat}}</tr>
        </th>
        </thead>
        <tbody>
        <tr v-for="(data) of records" :key="data.id">
          <td v-for="(i) of Object.values(data)" :key="i.id">{{i}}</td>
        </tr>
        </tbody>
      </table>
    </section>


  </div>


</template>

<script>
import store from "@/store";

export default {
  components:{},
  name: "EvadeLayout",
    data(){
      return{
        loading:true,
        records:[],
      }
    },
   /* async mounted(){
      try{
        const records=await store.dispatch('docsGet')
        this.records=records['data'].map(record=>{
          return{
            ...record
          }
        })

      }catch (e) {
        store.commit('setError')
      }

      this.loading=false
      return this.records
    }, */
    methods: {
      setup(){

      },
      async submitTv(){
        try{
          const records=await store.dispatch('docsGet')
          this.records=records['data'].map(record=>{
            return{
              ...record
            }
          })

        }catch (e) {
          store.commit('setError')
        }

        this.loading=false
        return this.records
      },
      async submitMobile(){
        try{
          const records=await store.dispatch('recDocsGet')
          this.records=records['data'].map(record=>{
            return{
              ...record
            }
          })

        }catch (e) {
          store.commit('setError')
        }

        this.loading=false
        return this.records
      }

    }

  }

</script>

<style scoped>
.IntroAnti{
  align-self: center;
  text-align: center;
}
.Request-container{
  display: flex;
  align-items: center;
  flex-direction: column;
}
.action-btn{

  display:inline;
  background: #00f638;
  border-radius: 20px;
  padding: 10px 10px;
  margin-bottom: 30px;
  margin-top:10px;


}


</style>