<template>
  <div class="appBody">
    <div>
      <h2 :class="[ButtonSelect === 'new' ? 'NewTitle' : 'defaultTitle', ButtonSelect === 'old' ? 'OldTitle' : 'defaultTitle', ButtonSelect === 'tech'? 'TechTitle' : 'defaultTitle']">面接練習へようこそ</h2>
    </div>
    <div class="PartButton">
      <div v-if="NewNone" class="NewButton">
        <button @click="PositionNew()">新卒として練習する</button>
      </div>
      <div v-if="OldNone" class="OldButton">
        <button @click="PositionOld()">中途として練習する</button>
      </div>
      <div v-if="OldNone" class="TechButton">
        <button @click="PositionTech()">技術質問として練習する</button>
      </div>
    </div>
    <div class="PartButton">
      <div :class="[ButtonSelect === 'new' ? 'NewButton' : 'classB', ButtonSelect === 'old' ? 'OldButton' : 'classD', ButtonSelect === 'tech'? 'TechButton' : 'class']">
        <button @click="start()" v-if="none">開始</button>
      </div>
      <div :class="[ButtonSelect === 'new' ? 'NewButton' : 'classB', ButtonSelect === 'old' ? 'OldButton' : 'classD', ButtonSelect === 'tech'? 'TechButton' : 'class']">
        <button @click="back()" v-if="none">選択へ戻る</button>
      </div>
    </div>
    <div :class="[ButtonSelect === 'new' ? 'NewNotification' : 'classB', ButtonSelect === 'old' ? 'OldNotification' : 'classD', ButtonSelect === 'tech'? 'TechNotification' : 'class']" v-if="none">今回の気づき</div>
    <div class="memo" v-if="none">{{memo}}</div>
    <transition name="fade">
      <div v-if="isOpen == 'up'">
        <NewContents :select="select" :part="part" @isOff="off" @protect="memo= $event">メモらん</NewContents>
      </div>
    </transition>
  </div>
</template>

<script>
import NewContents from "./components/NewContents.vue";
export default {
  components: {
    NewContents
  },
  data() {
    return {
      foot: "0",
      isOpen:'down',
      select: 0,
      part:"new",
      memo:"特になし",
      none: false,
      NewNone:true,
      OldNone:true,
      ButtonSelect: ''
    }
  },
  methods: {
    start() {
      this.isOpen = 'up'
      let number = 1 + Math.floor( Math.random() * 4 )
      this.select = number
      this.memo = "特になし"
    },
    back() {
      this.NewNone = true
      this.OldNone = true
      this.none = false
      this.ButtonSelect = ''
      this.memo = "特になし"
    },
    off() {
      this.isOpen = 'down'
    },
    PositionNew() {
      this.none = true
      this.NewNone = false
      this.OldNone = false
      this.ButtonSelect = 'new'
      this.part = 'new'
    },
    PositionOld() {
      this.none = true
      this.NewNone = false
      this.OldNone = false
      this.ButtonSelect = 'old'
      this.part = 'old'
    },
    PositionTech() {
      this.none = true
      this.NewNone = false
      this.OldNone = false
      this.ButtonSelect = 'tech'
      this.part = 'tech'
    }
  }
};
</script>

<style lang="scss" scoped>
h2 {
  width: 100%;
  text-align: center;
  color:white;
  border-bottom: 1px solid black;
  width: 15%;
  margin: 50px auto;
  -webkit-text-stroke: 1px black;
  text-stroke: 1px black;
}
button {
  padding: 20px;
  text-decoration: none;
  outline: none;
}
.NewButton button:active {
  /*ボタンを押したとき*/
  -webkit-transform: translateY(4px);
  transform: translateY(4px);/*下に動く*/
  border-bottom: none;/*線を消す*/
}
.OldButton button:active {
  /*ボタンを押したとき*/
  -webkit-transform: translateY(4px);
  transform: translateY(4px);/*下に動く*/
  border-bottom: none;/*線を消す*/
}
.TechButton button:active {
  /*ボタンを押したとき*/
  -webkit-transform: translateY(4px);
  transform: translateY(4px);/*下に動く*/
  border-bottom: none;/*線を消す*/
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
.defaultTitle {
  width: 100%;
  text-align: center;
  color:white;
  border-bottom: 1px solid black;
  width: 15%;
  margin: 50px auto;
  -webkit-text-stroke: 1px black;
  text-stroke: 1px black;
}
.NewTitle {
  width: 100%;
  text-align: center;
  color:rgba(247, 205, 90, 0.548);
  border-bottom: 1px solid red;
  width: 15%;
  margin: 50px auto;
  -webkit-text-stroke: 1px red;
  text-stroke: 1px red;
}
.OldTitle {
  width: 100%;
  text-align: center;
  color:rgba(90, 247, 247, 0.548);
  border-bottom: 1px solid blue;
  width: 15%;
  margin: 50px auto;
  -webkit-text-stroke: 1px blue;
  text-stroke: 1px blue;
}
.TechTitle {
  width: 100%;
  text-align: center;
  color:white;
  border-bottom: 1px solid green;
  width: 15%;
  margin: 50px auto;
  -webkit-text-stroke: 1px green;
  text-stroke: 1px green;
}
.PartButton {
  display: flex;
  justify-content: center;
}
.NewButton {
  display: inline;
  margin: 20px;
  font-size: 1rem;
}
.NewButton button {
  color: red;
  background:rgba(247, 205, 90, 0.548);
  border:1px solid rgb(255, 0, 0);
  border-radius: 20px;
  border-bottom: solid 4px rgba(255, 0, 0, 0.822);
}

.OldButton {
  display: inline;
  margin: 20px;
}
.OldButton button {
  color: blue;
  background:rgba(90, 247, 247, 0.548);
  border:1px solid blue;
  border-radius: 20px;
  border-bottom: solid 4px rgba(25, 0, 255, 0.822);
}
.TechButton {
  display: inline;
  margin: 20px;
}
.TechButton button {
  color: rgb(0, 128, 0);
  background:rgba(148, 247, 90, 0.548);
  border:1px solid green;
  border-radius: 20px;
  border-bottom: solid 4px rgba(0, 128, 0, 0.822);
}
.NewNotification{
  text-align: center;
  color: red;
  background:rgba(247, 205, 90, 0.548);
  border:1px solid rgb(255, 0, 0);
  border-radius: 20px;
  width: 10%;
  margin: 0 auto;
}
.OldNotification{
  text-align: center;
  color: blue;
  background:rgba(90, 247, 247, 0.548);
  border:1px solid blue;
  border-radius: 20px;
  width: 10%;
  margin: 0 auto;
}
.TechNotification{
  text-align: center;
  color: green;
  background:rgba(148, 247, 90, 0.548);
  border:1px solid green;
  border-radius: 20px;
  width: 10%;
  margin: 0 auto;
}
.memo {
  text-align: center;
}

.OldMemo {
  text-align: center;
  background: rgb(0, 60, 255);
  margin: 0 auto;
  border: 1px solid red;
  border-radius: 20px;
  width: 10%;
  margin: 10px;
  text-align: center;
}

</style>