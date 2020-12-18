<template>
	<div class="contentsBody" v-if="!off">
		{{select}} {{number}}
			<div class="contents" v-if="select=== 1">
				<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたの自己prを教えてください</p>
				<p v-else-if="number === 3">その中で我が社に行かせそうなところを教えてください</p>
				<p v-else-if="number === 4">弱みを教えてください</p>
				<p v-else-if="number === 5">ありがとうございました。それでは何か質問はありませんか？</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo">memo</textarea>
				<img src="@/assets/face.png" alt="">
				</div>
				<button id="button" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select===  2">
				<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたが頑張ったことを教えてください</p>
				<p v-else-if="number === 3">その中であなたが工夫したことを教えてください</p>
				<p v-else-if="number === 4">今回のあなたの就活軸を教えてください</p>
				<p v-else-if="number === 5">それを踏まえて弊社を志望する理由を教えてください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo">memo</textarea>
				<img src="@/assets/face.png" alt="">
				</div>
				<button id="button" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 3">
				<div>
				<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたの自己PRを教えてください</p>
				<p v-else-if="number === 3">なぜこの職種を希望されたのですか</p>
				<p v-else-if="number === 4">それはなぜですか</p>
				<p v-else-if="number === 5">あなたの失敗談を教えてください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo">memo</textarea>
				<img src="@/assets/face.png" alt="">
				</div>
				<button id="button" @click="next()">{{down}}</button>
				</div>
			</div>
			<div class="contents" v-else-if="select=== 4">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">学生時代に力を入れてきたこと</p>
				<p v-else-if="number === 3">なぜそのことに取り組もうと考えたのですか</p>
				<p v-else-if="number === 4">現在、プログラミング学習 ではどのようなことを学習しているのですか</p>
				<p v-else-if="number === 5">プログラミングを学んでみた感想</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo">memo</textarea>
				<img src="@/assets/face.png" alt="">
				</div>
				<button id="button" @click="next()">{{down}}</button>
			</div>
			
			<div>{{finish}}</div>
	</div>
</template>

<script>
export default {
	data(){
		return {
			down: "次へ",
			number:1,
			memo:"",
		}
	},
	props: {
		select: {
			type: Number,
			default: 1
		}
	},
	methods: {
		next() {
			if (this.number >= 5) {
				if (this.number == 5) {
					this.down = "終了"
					this.number = this.number +1 
				}else if (this.number == 6) {
					this.number = 0
					this.$emit('isOff')
				}
			}else{
				this.$emit('protect', this.memo)
				this.number = this.number +1
				this.down = "次へ"
			}
		},
		
	}
}
</script>

<style lang="scss" scoped>
img {
	width: 60%;
	left: 25%;
	height: 500px;
}
textarea {
	width: 20%;
}
p {
	font-size: 2rem;
	margin-bottom: 10%;
	width: 80%;
	margin-left:10%;
	}

.contentsBody {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;

}
#button {
	display: block;
	text-align: center;
	width: 20%;
	margin-left: 40%;
	margin-top: 5%;
}
.contents {
	position: absolute;
	top: 0;
	width: 100%;
	height: 100%;
	bottom: 10%;
	text-align: center;
	background: white;
}
.flex {
	
	display: flex;
	justify-content: space-around;
}
.memo {
}
</style>