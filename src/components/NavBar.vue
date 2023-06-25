<template>
  <nav class="navbar">
    <Transition name="header-change" mode="out-in">
      <div class="navbar__block" v-if="isActive">
        <div></div>
        <h3>Заметки</h3>
        <button @click="isActive = false" type="button" class="navbar__btn"><img src="../assets/img/search.svg"
            alt=""></button>
      </div>
      <div class="navbar__block" v-else>
        <button @click="isActive = true" class="navbar__btn" type="button"><img src="../assets/img/back.svg"
            alt=""></button>
        <div class="navbar__search container">
          <input v-model="Search" type="text" placeholder="Поиск...">
        </div>
        <button @click="Search = ''" class="navbar__btn" type="button"><img src="../assets/img/close.svg" alt=""></button>
      </div>
    </Transition>

  </nav>
</template>
<script>
export default {
  data() {
    return {
      isActive: true,
      Search: ''
    }
  },
}
</script>
<style lang="scss">
.navbar {
  background: #F3EDF7;
  padding: 14px;
  box-shadow: 0px 1px 3px 0px rgba(0, 0, 0, 0.30), 0px 4px 4px 0px rgba(0, 0, 0, 0.25);

  &__block {
    display: flex;
    justify-content: space-between;
    align-items: center;

    h3 {
      font-weight: 400;
    }
  }

  &__btn {
    outline: none;
    border: none;
    background: transparent;
    width: 36px;
    height: 36px;
    cursor: pointer;
  }

  &__search {
    width: 100%;

    input {
      width: 100%;
      border: none;
      outline: none;
      background: transparent;
      color: #000;
      font-size: 16px;
      line-height: 20px;
    }
  }
}

.header-change-enter-active,
.header-change-leave-active {
  transition: 0.2s linear;
}

.header-change-enter-from,
.header-change-leave-to {
  opacity: 0;
  transform: translateY(-100%);
}
</style>