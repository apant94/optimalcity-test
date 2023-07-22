<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div class="app">
    <ul class="app__data">
      <li v-for="item in data" :key="item.name" class="app__data-item">
        {{ item.name }}: {{ item.value }}
      </li>
    </ul>
    <EditForm :data="data" />
  </div>
</template>

<script>
import EditForm from './components/EditForm.vue';

export default {
  name: 'App',
  components: {
    EditForm,
  },
  data() {
    return {
      data: [
        {
          name: 'foo1',
          value: 'bar1',
        },
        {
          name: 'foo2',
          value: 'bar2',
        },
        {
          name: 'foo3',
          value: 'bar3',
        },
        {
          name: 'foo4',
          value: 'bar4',
        },
        {
          name: 'foo5',
          value: 'bar5',
        },
        {
          name: 'foo6',
          value: 'bar6',
        },
        {
          name: 'foo7',
          value: 'bar7',
        },
        {
          name: 'foo8',
          value: 'bar8',
        },
        {
          name: 'foo9',
          value: 'bar9',
        },
        {
          name: 'foo10',
          value: 'bar10',
        },
        {
          name: 'foo11',
          value: 'bar11',
        },
        {
          name: 'foo12',
          value: 'bar12',
        },
        {
          name: 'foo13',
          value: 'bar13',
        },
        {
          name: 'foo14',
          value: 'bar14',
        },
        {
          name: 'foo15',
          value: 'bar15',
        },
        {
          name: 'foo16',
          value: 'bar16',
        },
        {
          name: 'foo17',
          value: 'bar17',
        },
        {
          name: 'foo18',
          value: 'bar18',
        },
        {
          name: 'foo19',
          value: 'bar19',
        },
        {
          name: 'foo20',
          value: 'bar20',
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.app {
  display: flex;
  width: 80%;
  flex-direction: column;
  gap: 30px;
  margin: 20px auto;
  align-items: center;

  &__data {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    gap: 10px;
  }

  &__data-item {
    list-style: none;
  }
}
</style>
