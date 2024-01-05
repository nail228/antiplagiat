<template>
  <div class="filter-container">
    <div class="filter">
      <div  v-for="(i) of Object.keys(docs[0])" :key="i.id">
        <div class="f-item">{{i}}
          <input placeholder="Введите количество" class="f-input"/>
          <button class="f-button"> Ввести</button>
        </div>

      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "SearchFilter",
  props:{
    docs:Array
  },
  data(){
    return{
      selected:''
    }
  },
  components:{}
}
</script>

<style scoped>
.filter-container{
  display: flex;
  flex-direction: column;
  margin: 50px;

}
.filter{
  display: flex;
  flex-direction: column;
  background: #61892f;
  border-radius: 25px;
  margin-right: 400px;

}
.f-item{
  padding:10px;
  display: flex;
  flex-direction: row;
  margin: 20px;
  align-items: center;
}
.f-item>button{
  padding:10px;
  background: #00f638;
  border-radius: 15px;
}
.f-input{
  margin: 10px 200px;
}

</style>