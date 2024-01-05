<template>
    <div class="frame-container">

      <LoaderPage v-if="loading==true"/>

        <p class="center" v-else-if="!records.length">No records</p>

      <section v-else>
        <SearchFilter :docs="records"></SearchFilter>
        <SearchTable :documents="records"></SearchTable>
      </section>


    </div>
</template>

<script>
import SearchTable from "@/components/User/BaseSearch/SearchTable"
import store from '@/store'
import LoaderPage from "@/components/app/LoaderPage.vue";
import SearchFilter from "@/components/User/BaseSearch/SearchFilter.vue";
export default {
  name: "SearchFrame",
  data(){
    return{
      loading:true,
      records:[],
      searchTable:SearchTable,
    }
  },
  components:{SearchFilter, LoaderPage, SearchTable},
    async mounted(){
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
    methods: {
    setup(){

    }

      }

  }

</script>

<style scoped>

</style>