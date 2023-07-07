<template>
  <div class="keep">
    <div @click="updatedTest">{{ message }}</div>
  </div>
</template>

<script>
export default {
  name: "KeepAliveTest",
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
    console.log("KeepAliveTest--> beforeCreate");
  },
  // 在实例生成之后自动执行的函数
  created() {
    console.log("KeepAliveTest--> created");
  },
  //  在组件内容被渲染到页面之前自动执行的函数(实例挂载到页面之前)
  beforeMount() {
    console.log("KeepAliveTest--> beforeMount");
  },
  // 在组件内容被渲染到页面之后自动执行的函数(实例挂载到页面之后)
  mounted() {
    console.log("KeepAliveTest--> mounted");
  },
  // 当data中的数据发生变化时会立即自动执行的函数
  beforeUpdate() {
    console.log("KeepAliveTest--> beforeUpdate");
  },
  // 当data中的数据发生变化，同时页面完成更新并重新渲染后，会自动执行的函数
  updated() {
    console.log("KeepAliveTest--> updated");
  },
  // 当vue实例销毁时自动执行的函数
  beforeUnmount() {
    console.log("KeepAliveTest--> beforeUnmount");
  },
  // 当vue实例销毁时，且DOM完全销毁之后，自动执行的函数
  unmounted() {
    console.log("KeepAliveTest--> unmounted");
  },

  // keep-alive组件提供的钩子函数activated、deactivated
  activated() {
    // 组件激活时调用,进入home组件的那一刻就会打印
    console.log("KeepAliveTest--> activated");
  },
  deactivated() {
    // 组件停用时调用,离开home组件的那一刻就会打印
    console.log("KeepAliveTest--> deactivated");
  },

  // Vue实例销毁之前被调用
  beforeDestroy() {
    console.log("KeepAliveTest--> beforeDestroy");
  },
  destroyed() {
    console.log("KeepAliveTest--> destroyed");
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
