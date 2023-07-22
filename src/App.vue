<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <FormItem /> -->
  <div class="app">
    <ul class="app__data">
      <li v-for="item in data" :key="item.name" class="app__data-item">
          {{ item.name }}
          {{ item.value }}
          <!-- <input v-model="item.value"> -->
        <!-- <template>
          {{ item.name }}
          <input v-model="item.value">
          <button @click="save(item)">
            save
          </button>
        </template> -->
      </li>
    </ul>
    <form v-on:submit.prevent>
      <select v-model="selected" class="form__input">
        <option v-for="(item, i) in data" :value="i" :key="item.name">
          {{ item.name }}
          {{ item.value }}
        </option>
      </select>
      <input v-model="newValue" ref="input" placeholder="Введите новое значение">
      <!-- <button @click="edit(selected)" v-if="!isEditing">
        edit
      </button> -->
      <button @click="isEditing = !isEditing" v-if="!isEditing">
        Edit
      </button>
      <button @click="save" v-else-if="isEditing">
      Save
      </button>
    </form>
</div>
</template>

<script>
// import FormItem from './components/FormItem.vue';

export default {
  name: 'App',
  // components: {
  //   FormItem,
  // }
  data() {
    return {
      selected: '',
      newValue: '',
      isEditing: false,
      data: [
        {
          "name": "foo1",
          "value": "bar1",
        },
        {
          "name": "foo2",
          "value": "bar2",
        },
        {
          "name": "foo3",
          "value": "bar3",
        },
        {
          "name": "foo4",
          "value": "bar4",
        },
        {
          "name": "foo5",
          "value": "bar5",
        },
        {
          "name": "foo6",
          "value": "bar6",
        },
        {
          "name": "foo7",
          "value": "bar7",
        },
        {
          "name": "foo8",
          "value": "bar8",
        },
        {
          "name": "foo9",
          "value": "bar9",
        },
        {
          "name": "foo10",
          "value": "bar10",
        },
        {
          "name": "foo11",
          "value": "bar11",
        },
        {
          "name": "foo12",
          "value": "bar12",
        },
        {
          "name": "foo13",
          "value": "bar13",
        },
        {
          "name": "foo14",
          "value": "bar14",
        },
        {
          "name": "foo15",
          "value": "bar15",
        },
        {
          "name": "foo16",
          "value": "bar16",
        },
        {
          "name": "foo17",
          "value": "bar17",
        },
        {
          "name": "foo18",
          "value": "bar18",
        },
        {
          "name": "foo19",
          "value": "bar19",
        },
        {
          "name": "foo20",
          "value": "bar20",
        },
      ]
    }
  },
  methods: {
    save() {
      console.log(this.$refs.input.value);
      this.data[this.selected].value = this.$refs.input.value;
      this.isEditing = !this.isEditing;
    }
  },
}
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.app {
  display: flex;
  width: 80%;
  justify-content: space-between;
  border: 3px solid #2c3e50;
  margin: 20px auto;

  &__data-item {
    list-style: none;
  }
}

.form {
  &__input {
    min-width: 200px;
    height: 40px;
    border: 1px solid #454749;
    border-radius: 20px;
  }
}
</style>
