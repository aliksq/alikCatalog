<template>
  <div class="item__card"
    @click = "getRemove"
  >
    <a v-if="needRemove" id = "delete__card" class="delete__card"
        @click ="$emit('remove', card)"
    >
      <img src="../../public/assets/img/removeIcon.png" alt="icon">
    </a>
    <div class="card__img">
      <img :src = "card.image" alt="photo">
    </div>
    <div class="card__info">
      <h3 class="card__name">
        {{card.title}}
      </h3>
      <div class="card__desc">
        {{card.desc}}
      </div>
      <div class="card__footer">
        <img src="" alt="">
        <div class="card__price">{{card.price}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    card: {
      type: Object,
      required:true,
    }
  },
  data(){
    return{
      needRemove: false
    }
  },
  methods:{
    getRemove(){
      if(this.needRemove === true){
         return this.needRemove = false
      }else{
        return this.needRemove = true
      }
    },

  },
}
</script>

<style scoped>
.item__card {
  box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04);
  border-radius: 4px;
  width: 332px;
  height: 423px;
  position: relative;
}

@media(max-width: 768px){
  .item__card {
    box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04);
    border-radius: 4px;
    width: 300px;
    height: 423px;
  }
}
@media(max-width: 478px){
  .item__card {
    width: 100%;
  }
}
.card__img img{
  width: 100%;
  height: 200px;
}
@media(max-width: 768px){
  .card__img img{
    max-width: 100%;
    height: 200px;
  }
}
.card__info{
  padding: 16px 16px 24px 16px;
}
.card__name {
  font-weight: 600;
  font-size: 20px;
  margin-bottom: 16px;
}
.card__desc {
  font-weight: 400;
  font-size: 16px;
  margin-bottom: 32px;
  min-height: 80px;
}
.card__footer{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.card__price {
  font-size: 24px;
  font-weight: 600;
}
.delete__card{
  z-index: 1;
  position: absolute;
  bottom: 395px;
  right: -10px;
}
</style>