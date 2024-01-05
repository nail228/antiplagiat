<template>
  <div class="wrapper">
        <main class="main">
          <div class="main_container">
            <div class="Intro">
                Зачем нужна данная система?
            </div>
            <div class="description">
              Данная система нужна для того чтобы помочь пользователям с выбором правильных материалов для проектирования МПП
            </div>
            <div class="action">
              В нашей системе вы можете работать с аналитической системой выбора а также использовать базу данных для материалов МПП
            </div>
            <div class="action-container">
              <ActionMain/>
            </div>
            <div class="resorses-container">
              <h1>Какие ресурсы использует наша система ?</h1>
              <div>
                <img src="@/assets/book.png">
                <p> База данных с характеристиками материалов МПП (механические свойства, термическая стойкость, электропроводность и т.д.).</p>
              </div>
              <div>
                <img src="@/assets/files.png">
                <p> Аналитические инструменты для расчета оптимальных параметров материалов МПП (например, методы оптимизации или алгоритмы машинного обучения).</p>
              </div>
              <div>
                <img src="@/assets/book.png">
                <p> Коллекции   документов “Кольцо ВУЗов”</p>
              </div>
              <div>
                <img src="@/assets/translate.png">
                <p> Информационные ресурсы о производителях материалов МПП и их продукции.</p>
              </div>
              <div>
                <img src="@/assets/book.png">
                <p> Результаты предыдущих исследований и экспериментов по выбору материалов МПП</p>
              </div>
              <div>
                <img src="@/assets/book.png">
                <p> КСпециализированные журналы и научные публикации в области материалов МПП.</p>
              </div>

            </div>
          </div>
        </main>



  </div>


</template>

<script >
import ActionMain from "@/components/User/main/ActionMain.vue";



export default {
  components: {ActionMain},
  data(){
    return{


    }
  }
}
</script>

<style lang="scss" >
@import '../../node_modules/materialize-css/dist/css/materialize.min.css';

.wrapper{
  display: flex;
  flex-direction: column;
}

.main {
  position: relative;


}
.main_container{
  display: flex;
  flex-direction: column;
  flex: 0 0 100%;
  justify-content: space-between;

}
.Intro{

  font-family: Roboto Flex;
  font-style: normal;
  font-weight: 700;
  font-size: 64px;
  line-height: 63px;
  text-align:center;
  align-self: center;
  padding: 10px 10px ;
  margin: 40px 40px;

  color: #000000;
}
.description{
  font-family: Roboto Flex;
  position: relative;
  margin: 150px 0;
  text-align: center;
  align-self: center;
  padding: 10px 10px;


  color: #937C7C;
}
.description:nth-child(n){
  box-sizing: border-box;
  margin: 100px 150px;
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 23px;

}
.action{
  font-family: 'Roboto Flex';
  font-style: normal;
  font-weight: 400;
  font-size: 26px;
  line-height: 38px;
  margin-bottom: 40px;
  margin-left: 50px;
  align-self: flex-start;

  color: #666363;
}


.resorses-container{
  display: flex;
  flex-direction: column;
  padding-left: 50px;
  align-self: flex-start;

}
h1{
  font-family: Roboto Flex;
  font-style: normal;
  font-weight: 400;
  font-size: 30px;
  line-height: 47px;
  align-self: flex-start;

  color: #000000;
}
.resorses-container>div{
  display: flex;
}

div>img{
  display: inline-block;
  position: relative;
  height: 64px;
  width: 64px;
  padding: 15px 15px;

}
div>p{
  font-family: Roboto Flex;
  text-align: center;
  align-self: center;
}


</style>