<template>
  <div class="home">
    <div @click="updatedTest">{{ message }}</div>
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <!-- 被keep-alive包含的组件会被缓存 -->
    <keep-alive include ="HomeView">
      <KeepAliveTest msg="Welcome to Your Vue.js App" />
    </keep-alive>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import KeepAliveTest from "@/components/KeepAliveTest.vue";

export default {
  name: "HomeView",
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
  components: {
    HelloWorld,
    KeepAliveTest,
  },
  // 在实例生成之前自动执行的函数
  beforeCreate() {
    console.log("beforeCreate");
  },
  // 在实例生成之后自动执行的函数
  created() {
    console.log("created");
  },
  //  在组件内容被渲染到页面之前自动执行的函数(实例挂载到页面之前)
  beforeMount() {
    console.log("beforeMount");
  },
  // 在组件内容被渲染到页面之后自动执行的函数(实例挂载到页面之后)
  mounted() {
    console.log("mounted");
  },
  // 当data中的数据发生变化时会立即自动执行的函数
  beforeUpdate() {
    console.log("beforeUpdate");
  },
  // 当data中的数据发生变化，同时页面完成更新并重新渲染后，会自动执行的函数
  updated() {
    console.log("updated");
  },
  // 当vue实例销毁时自动执行的函数
  beforeUnmount() {
    console.log("beforeUnmount");
  },
  // 当vue实例销毁时，且DOM完全销毁之后，自动执行的函数
  unmounted() {
    console.log("unmounted");
  },
  // Vue实例销毁之前被调用
  beforeDestroy() {
    console.log("beforeDestroy");
  },
  destroyed() {
    console.log("destroyed");
  },
};
</script>
