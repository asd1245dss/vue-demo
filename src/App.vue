<template xmlns:v-bind="http://www.w3.org/1999/xhtml">
  <div id="app">
    <img src="./assets/logo.png" v-bind:class="{'img-circle': imgCircle}">
    <hello></hello>
    <label>
      <select v-model="see">
        <optgroup label="label">
          <option value="true">true</option>
          <option value="false">false</option>
        </optgroup>
      </select>
    </label>
    <p v-if="see">Can you see</p>
    <template v-if="see">
      <h1>菜鸟教程</h1>
      <p>学的不仅是技术！更是梦想！</p>
      <p>打字辛苦！</p>
    </template>
  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  components: {
    Hello
  },
  data () {
    return {
      imgCircle: true,
      see: false
    }
  },
  methods: {
    toggleVisible: function (value) {
      console.info(value)
      this.see = value
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .img-circle {
    border-radius: 50%;
  }
</style>
