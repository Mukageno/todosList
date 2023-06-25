<template >
  <div class="modal">
    <div class="modal__block">
      <h3>Добавить заметку</h3>
      <label class="modal__inputs" for="title">
        <span>Title</span>
        <input id="title" type="text" v-model="note.title" placeholder="Title">
      </label>
      <label class="modal__inputs" for="text">
        <span>Content</span>
        <textarea id="text" rows="1" v-model="note.text" type="text" placeholder="Content"></textarea>
      </label>
      <div class="modal__btns">
        <button type="button" @click="$emit('active')">Отмена</button>
        <button type="button" @click="send">Добавить</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      note: {
        title: '',
        text: '',
        id: 1
      }
    }
  },
  props: {
    active: Boolean
  },
  methods: {
    send() {
      this.$emit('addNote', { ...this.note })
      this.note.title = ''
      this.note.text = ''
      this.id++
    }
  }
}
</script>
<style lang="scss">
.modal {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  background: rgba(0, 0, 0, 0.35);
  z-index: 99;
  display: flex;
  align-items: center;
  justify-content: center;

  &__block {
    border-radius: 28px;
    background: #FFFBFE;
    max-width: 312px;
    width: 100%;
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 16px;



    h3 {
      font-size: 24px;
      line-height: 32px;
      font-weight: 500;
    }
  }

  &__btns {
    display: flex;
    justify-content: flex-end;
    gap: 24px;

    button {

      text-align: center;
      font-size: 14px;
      font-family: Roboto;
      font-weight: 500;
      line-height: 20px;
      letter-spacing: 0.1px;
      background: transparent;
      text-transform: uppercase;

      &:first-of-type {
        color: #CF1B1B;
      }

      &:last-of-type {
        color: #6750A4;
      }
    }
  }

  &__inputs {
    border-radius: 4px 4px 0px 0px;
    background: #E7E0EC;
    display: flex;
    flex-direction: column;
    padding: 9px 16px;

    input,
    textarea {
      background: transparent;
      outline: none;
      border: none;
      font-size: 16px;
      line-height: 24px;
      letter-spacing: 0.5px;
      resize: none;
    }
  }
}
</style>