<template>
  <div class="block">
    <span class="demonstration">默认 Hover 指示器触发</span>
    <el-carousel height="150px">
      <el-carousel-item v-for="item in 4" :key="item">
        <h3 class="small">{{ item }}</h3>
      </el-carousel-item>
    </el-carousel>
  </div>
  <div class="mask" v-if="modalStatus">
    <div class="modal-popup">
      hello
      <div class="bottom-area">
        <button @click="handleConfirmClick" class="bottom-btn">确定</button>
        <button @click="handleCancelClick" class="bottom-btn">取消</button>
      </div>
    </div>
  </div>
  <el-row>
    <el-button size="mini" type="info" :round="true" :loading="true">默认按钮</el-button>
    <el-button type="primary">主要按钮</el-button>
    <el-button type="success">成功按钮</el-button>
    <el-button type="info">信息按钮</el-button>
    <el-button type="warning">警告按钮</el-button>
    <el-button type="danger">危险按钮</el-button>
  </el-row>

  <button @click="modalStatus = true">展示弹窗</button>
  <h1 class="hello-container">Hello Vue</h1>
  
  <img alt="Vue logo" src="./assets/logo.png">
  <p>
    我是父组件，下面是子组件helloword
  </p>
  <HelloWorld text-title="我是helloWorld子组件"/>
  <HelloWorld text-title="我不是helloWorld子组件"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data () {
    return {
      modalStatus: false
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    handleConfirmClick () {
      console.log('你点了确定')
    },
    handleCancelClick () {
      this.modalStatus = false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.hello-container {
  background-color: #999;
  color: bisque;
}
.mask {
  width: 100vw;
  height: 100vh;
  position: absolute;
  left: 0;
  top: 0;
  background-color: rgba(0, 0, 0, .4);
}
.modal-popup {
  width: 200px;
  height: 120px;
  background-color: #fff;
  left: 50%;
  top: 50%;
  position: absolute;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.bottom-area {
  display: flex;
  justify-content: space-between;
}
</style>
