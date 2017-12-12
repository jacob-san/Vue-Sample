<template>
  <div id="hello" class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <div class="secret-msg-container">
          <span v-if="seenMsg" v-bind:title="hoverMessage" class="secret-msg">Hover over to see the secret code</span>
    </div>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
    <ol>
      <li v-bind:key="todo.text" v-for="todo in todos">
        {{ todo.text }}
      </li>
    </ol>
    <button v-on:click="addItem">Add New Item</button>
    <button v-on:click="reverseMsg">Reverse Greeting message</button>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Build your Overwatch profile',
      hoverMessage: 'You logged in 3min ago',
      seenMsg: true,
      todos: [
        { text: 'Make a Toast' },
        { text: 'Roll over me' },
        { text: 'Hit me on the face' }
      ]
    }
  },
  methods: {
    addItem () {
      if (this.todos.length > 4) {
        return
      }
      this.todos.length < 4 ? this.todos.push({ text: 'Did you just add me?' }) : this.todos.push({ text: 'Ahw! getting bigger' })
    },
    reverseMsg () {
      this.msg = this.msg.split('').reverse().join('')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
      color: #fa9c1f;
}
.secret-msg-container {
      margin: 50px;
}
.secret-msg {
    background-color: #fa9c1f;
    color: #ffffff;
    cursor: pointer;
    font-size: 20px;
    padding: 10px;
    border: 5px solid #000;
}
</style>
