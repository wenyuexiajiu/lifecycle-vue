<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener"
          >babel</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-router"
          target="_blank"
          rel="noopener"
          >router</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-vuex"
          target="_blank"
          rel="noopener"
          >vuex</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
          target="_blank"
          rel="noopener"
          >eslint</a
        >
      </li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li>
        <a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a>
      </li>
      <li>
        <a href="https://forum.vuejs.org" target="_blank" rel="noopener"
          >Forum</a
        >
      </li>
      <li>
        <a href="https://chat.vuejs.org" target="_blank" rel="noopener"
          >Community Chat</a
        >
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank" rel="noopener"
          >Twitter</a
        >
      </li>
      <li>
        <a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a>
      </li>
    </ul>
    <h3>Ecosystem</h3>
    <div @click="updatedTest">{{ message }}</div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      message: "Welcome",
    };
  },
  methods: {
    updatedTest() {
      if (this.message === "Welcome") {
        this.message = "Hello World";
      } else if (this.message === "Hello World") {
        this.message = "Welcome";
      }
    },
  },
  // 在实例生成之前自动执行的函数
  beforeCreate() {
    console.log("HelloWorld--> beforeCreate");
  },
  // 在实例生成之后自动执行的函数
  created() {
    console.log("HelloWorld--> created");
  },
  //  在组件内容被渲染到页面之前自动执行的函数(实例挂载到页面之前)
  beforeMount() {
    console.log("HelloWorld--> beforeMount");
  },
  // 在组件内容被渲染到页面之后自动执行的函数(实例挂载到页面之后)
  mounted() {
    console.log("HelloWorld--> mounted");
  },
  // 当data中的数据发生变化时会立即自动执行的函数
  beforeUpdate() {
    console.log("HelloWorld--> beforeUpdate");
  },
  // 当data中的数据发生变化，同时页面完成更新并重新渲染后，会自动执行的函数
  updated() {
    console.log("HelloWorld--> updated");
  },
  // 当vue实例销毁时自动执行的函数
  beforeUnmount() {
    console.log("HelloWorld--> beforeUnmount");
  },
  // 当vue实例销毁时，且DOM完全销毁之后，自动执行的函数
  unmounted() {
    console.log("HelloWorld--> unmounted");
  },
  // Vue实例销毁之前被调用
  beforeDestroy() {
    console.log("HelloWorld--> beforeDestroy");
  },
  destroyed() {
    console.log("HelloWorld--> destroyed");
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
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
  color: #42b983;
}
</style>
