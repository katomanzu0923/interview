<template>
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
</template>