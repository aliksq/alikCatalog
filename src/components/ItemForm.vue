<template>
  <div class="item__form">
    <form action="" class="item__info" @submit.prevent>
      <h3 class="item_h">
        Наименование товара
      </h3>
      <input
          v-model = "card.title"
          type="text"
          placeholder="Введите наименование товара"
          class="inp__name"
      >

      <h3 class="item_h">
        Описание товара
      </h3>
      <input
          v-model = "card.desc"
          type="text"
          placeholder="Введите описание товара"
          class="inp__desc"
      >

      <h3 class="item_h">
        Ссылка на изображение товара
      </h3>
      <input
          v-model = "card.image"
          type="text"
          placeholder="Введите ссылку"
          class="inp__link"
      >

      <h3 class="item_h">
        Цена товара
      </h3>
      <input
          v-model = "card.price"
          type="text"
          placeholder="Введите цену"
          class="inp__price"
      >
    </form>

    <add-button
        class="add__btn"

        @click = "validateCard"
    >
      Добавить товар
    </add-button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      card: {
        image: '',
        title: '',
        desc: '',
        price: '',
      }
    }
  },
  methods: {
    createCard() {
      this.card.id = Date.now()
      this.$emit('create', this.card)
      this.card = {
        image: '',
        title: '',
        desc: '',
        price: '',
      }
    },
  }
}
</script>

<style scoped>
.item__form {
  padding: 24px;
  box-shadow: 0 6px 30px rgba(0, 0, 0, 0.04);
  width: 332px;
  max-height: 440px;
}
@media(max-width: 1040px){
  .item__form {
    width: 80%;
  }
}
@media(max-width: 478px){
  .item__form {
    width: 100%;
  }
}
.item__info {
  display: flex;
  flex-direction: column;
}
.item_h {
  margin-bottom: 4px;
  font-weight: 400;
  font-size: 10px;
  line-height: 130%;
  color: #49485E;
}
.item__info input{
  margin-bottom: 16px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  transition: 0.3s;
  color: #727070;
}
.item__info input{
  outline: none;
}
input:focus{
  box-shadow: 0 0 10px #B4B4B4;

}

input::-webkit-input-placeholder { color: #B4B4B4; font-size: 12px;}
input::-moz-placeholder { color: #B4B4B4; font-size: 12px;}

input::-webkit-input-placeholder       {text-indent: 0;   transition: text-indent 0.3s ease;}
input::-moz-placeholder                {text-indent: 0;   transition: text-indent 0.3s ease;}
input:-moz-placeholder                 {text-indent: 0;   transition: text-indent 0.3s ease;}
input:-ms-input-placeholder            {text-indent: 0;   transition: text-indent 0.3s ease;}
input:focus::-webkit-input-placeholder {text-indent: 500px; transition: text-indent 0.3s ease;}
input:focus::-moz-placeholder          {text-indent: 500px; transition: text-indent 0.3s ease;}
input:focus:-moz-placeholder           {text-indent: 500px; transition: text-indent 0.3s ease;}
input:focus:-ms-input-placeholder      {text-indent: 500px; transition: text-indent 0.3s ease;}


.inp__name {
  height: 36px;
  padding-top: 10px;
  padding-left: 16px;
  padding-bottom: 11px;
}
.inp__desc {
  height: 108px;
  padding-top: 10px;
  padding-left: 16px;
  padding-bottom: 83px;
}
.inp__link {
  height: 36px;
  padding-top: 10px;
  padding-left: 16px;
  padding-bottom: 11px;
}
.inp__price {
  height: 36px;
  border-radius: 4px;
  padding-top: 10px;
  padding-left: 16px;
  padding-bottom: 11px;
}

</style>