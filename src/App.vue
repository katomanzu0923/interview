<template>
  <div class="appBody">
    <div>
      <h2>面接練習へようこそ</h2>
    </div>
    <div class="button">
      <button @click="start1()">開始</button>
    </div>
    <div class="notification">今回の気づき<div>{{memo}}</div></div>
    <transition name="fade">
      <div v-if="isOpen == 'up'">
        <Contents :select="select" @isOff="off" @protect="memo= $event">メモらん</Contents>
      </div>
    </transition>
  </div>
</template>

<script>
import Contents from "./components/Contents.vue";
export default {
  components: {
    Contents
  },
  data() {
    return {
      foot: "0",
      isOpen:'down',
      select: 0,
      memo:"特になし"
    }
  },
  methods: {
    start1() {
      this.isOpen = 'up'
      let number = 1 + Math.floor( Math.random() * 4 )
      this.select = number
      this.memo = "特になし"
    },
    off() {
      this.isOpen = 'down'
    }
  }
};
</script>

<style lang="scss" scoped>
h2 {
  width: 100%;
  text-align: center;
  color: red;
}
button {
  text-align: center;
  margin: 0 auto;
}
.appBody {
  
}
.none {
  display: none;
}
.fade-enter-active {
  transition: all 0.5s ease;
}
.fade-enter{
  opacity: 0;
}
.fade-enter-to {
	opacity: 1;
}
.button {
  text-align: center;
}
.notification {
  text-align: center;
}
</style>