<template>
  <div class="catalog" v-show="cards.length > 0">
      <ItemCard
          v-for ="card in cards"
          :card="card"
          :key ="card.id"
          @remove = "$emit('remove', card)"
      />
  </div>
  <div class="ask__card" v-show="cards.length === 0">
    <h2>Добавьте карточку, заполнив форму</h2>
  </div>
</template>

<script>
import ItemCard from "@/components/ItemCard";
export default {
  components: {ItemCard},
  props: {
    cards: {
      type: Array,
      required: true

    }
  },
}
</script>

<style scoped>
.catalog {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  align-items: center;
}
@media(max-width: 768px) {
  .catalog {
    flex-wrap: nowrap;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}
.ask__card{
  font-size: 2rem;
  color: #B4B4B4;
}
</style>