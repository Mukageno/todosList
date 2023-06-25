<template>
  <section class="notes container">
    <div class="notes__top">
      <h3>Все заметки</h3>
      <button @click="grid = !grid" class="notes__btn" type="button">
        <img src="../assets/img/grid.svg" alt="" v-show="grid === true">
        <img src="../assets/img/list.svg" alt="" v-show="grid === false">
        <span>{{ grid == true ? 'Сетка' : 'Список' }}</span>
      </button>
    </div>
    <div class="notes__card">
      <NotesItem />
    </div>
  </section>
</template>
<script>
import NotesItem from './NotesItem.vue';

export default {
  data() {
    return {
      grid: true
    };
  },
  components: { NotesItem }
}
</script>
<style lang="scss">
.notes {
  padding: 30px 0;
  &__item{
    
  }
  &__top {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__btn {
    display: flex;
    align-items: center;
    padding: 16px 20px 16px 16px;
    border-radius: 16px;
    box-shadow: 0px 1px 3px 0px rgba(0, 0, 0, 0.30), 0px 4px 8px 3px rgba(0, 0, 0, 0.15);
    border: none;
    outline: none;
    gap: 12px;
    color: #6750A4;
    font-size: 14px;
    font-weight: 500;
    line-height: 20px;
    letter-spacing: 0.1px;
    cursor: pointer;
  }
}
</style>