<template>
  <form v-on:submit.prevent class="form">
    <p class="form__text">Сначала выберите элемент для редактирования</p>
    <select v-model="selected" class="form__input">
      <option v-for="(item, i) in data" :value="i" :key="item.name">
        {{ item.name }}
        {{ item.value }}
      </option>
    </select>
    <button
      @click="isEditing = !isEditing"
      v-if="!isEditing"
      class="form__button"
    >
      Редактировать
    </button>
    <button @click="onSave" v-else-if="isEditing" class="form__button">
      Сохранить
    </button>
    <input
      v-if="isEditing"
      v-model="newValue"
      @click="onClickInput"
      ref="input"
      placeholder="Введите новое значение"
      class="form__input"
    />
  </form>
</template>

<script>
export default {
  name: 'EditForm',
  props: {
    data: {
      type: Object,
    },
  },
  data() {
    return {
      selected: '',
      newValue: '',
      isEditing: false,
    };
  },
  methods: {
    onClickInput() {
      if (!this.newValue) {
        this.$refs.input.value = this.data[this.selected].value;
      }
    },
    onSave() {
      // eslint-disable-next-line vue/no-mutating-props
      this.data[this.selected].value = this.$refs.input.value;
      this.isEditing = !this.isEditing;
      this.newValue = '';
    },
  },
};
</script>

<style lang="scss" scoped>
.form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  width: 100%;
  &__text {
    align-self: center;
    color: #4fbf71;
  }
  &__button {
    background-color: #98e0ae;
    width: 150px;
    height: 40px;
    border-radius: 20px;
    margin: 0 auto;
  }
  &__input {
    margin: 0 auto;
    width: 40%;
    min-width: 220px;
    height: 40px;
    border: 1px solid #4fbf71;
    border-radius: 20px;
    padding: 0 10px;
    text-align: center;
    cursor: pointer;
  }
}
</style>
