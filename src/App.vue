<template>
  <div class="wrapper">
    <div class="container">
      <div class="header">
        <div class="header__menu">
          <h3 class="add__item">
            Добавление товара
          </h3>
          <div class="select">
            <select>
              <option selected value="1">По умолчанию</option>
              <option value="2">По названию</option>
              <option value="3">По цене min</option>
              <option value="4">По цене max</option>
            </select>
          </div>
        </div>
      </div>
      <div class="main">
        <div class="main__block">
          <ItemForm
              @create = "createCard"
          />
          <Catalog
              :cards="cards"
              @remove = "removeCard"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Catalog from "@/components/Catalog";
import ItemForm from "@/components/ItemForm";
export default {
  components:{
    Catalog,
    ItemForm
  },
  data() {
    return {
      cards : [
        {
          id: 1,
          image: require('../public/assets/img/card__img.png'),
          title: 'Наименование товара',
          desc: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
          price: 10000,
        },
        {
          id: 2,
          image: require('../public/assets/img/card__img.png'),
          title: 'Наименование товара',
          desc: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
          price: 10000,
        },
        {
          id: 3,
          image: require('../public/assets/img/card__img.png'),
          title: 'Наименование товара',
          desc: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
          price: 10000,
        },
        {
          id: 4,
          image: require('../public/assets/img/card__img.png'),
          title: 'Наименование товара',
          desc: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
          price: 10000,
        },
        {
          id: 5,
          image: require('../public/assets/img/card__img.png'),
          title: 'Наименование товара',
          desc: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
          price: 10000,
        },
        {
          id: 6,
          image: require('../public/assets/img/card__img.png'),
          title: 'Наименование товара',
          desc: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
          price: 10000,
        },
      ],
    }
  },
  methods: {
    createCard (card) {
      this.cards.push(card)
    },
    removeCard (card){
      this.cards = this.cards.filter(c => c.id !== card.id)
    },
  }
}
</script>
<style>
*,
*::before,
*::after {
  padding: 0;
  margin: 0;
  border: 0;
  box-sizing: border-box;
}
a {
  text-decoration: none;
}
ul,
ol,
li {
  list-style: none;
}
img {
  vertical-align: top;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: inherit;
  font-size: inherit;
}
html,
body {
  height: 100%;
  line-height: 1;
}








*{
  line-height: 125%;
}
body {
  font-family: 'Source Sans Pro', sans-serif;
  font-size: 12px;
  color: #3F3F3F;
  background-color: rgba(255, 254, 251, 0.8);
}
.wrapper {
  overflow: hidden;
  display: flex;
  flex-direction: column;
  min-height: 100%;
}
/*------------------------*/
.main {
  flex: 1 1 auto;
}
.container{
  padding: 0 32px;
}
/*-----------------------------------------------------*/
.header{

}
.header__menu{
  padding-top: 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}
@media(max-width: 768px){
  .header__menu{
    flex-direction: column;
    align-items: flex-start;
    gap: 25px;
    margin-bottom: 40px;
  }
}
.add__item{
  font-size: 28px;
  font-weight: 600;
}
@media(max-width: 768px){
  .add__item{
    font-size: 22px;
    font-weight: 600;
  }
}
.select{
  position: relative;
}
.select select{
  border: 1px solid rgba(0, 0, 0, 0.1);
  font-size: 12px;
  padding: 10px 16px;
  color: #B4B4B4;
  border-radius: 4px;
  box-shadow: 2px 2px 3px rgba(0, 0, 0, 0.1);
  font-family: inherit;
}
.main__block{
  display: flex;
  gap:16px
}
@media (max-width: 1040px){
  .main__block{
    gap:96px
  }
}
@media (max-width: 1040px){
  .main__block{
    flex-direction: column;
    gap: 32px;
    align-items: flex-start;
  }
}
</style>