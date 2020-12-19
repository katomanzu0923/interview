<template>
	<div class="contentsBody" v-if="!off">
		<div v-if="part =='new'">
			<div class="contents" v-if="select=== 1">
				<div class="NewTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたの自己prを教えてください</p>
				<p v-else-if="number === 3">その中で我が社に行かせそうなところを教えてください</p>
				<p v-else-if="number === 4">弱みを教えてください</p>
				<p v-else-if="number === 5">ありがとうございました。それでは何か質問はありませんか？</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="NewText">memo</textarea>
				<img src="@/assets/face01.png" alt="">
				</div>
				<button @click="next()" class="NewButton">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select===  2">
				<div class="NewTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたが頑張ったことを教えてください</p>
				<p v-else-if="number === 3">その中であなたが工夫したことを教えてください</p>
				<p v-else-if="number === 4">今回のあなたの就活軸を教えてください</p>
				<p v-else-if="number === 5">それを踏まえて弊社を志望する理由を教えてください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="NewText">memo</textarea>
				<img src="@/assets/face02.png" alt="">
				</div>
				<button @click="next()" class="NewButton">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 3">
				<div class="NewTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたの自己PRを教えてください</p>
				<p v-else-if="number === 3">なぜこの職種を希望されたのですか</p>
				<p v-else-if="number === 4">それはなぜですか</p>
				<p v-else-if="number === 5">あなたの失敗談を教えてください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="NewText">memo</textarea>
				<img src="@/assets/face03.png" alt="">
				</div>
				<button class="NewButton" @click="next()" >{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 4">
				<div class="NewTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">学生時代に力を入れてきたこと</p>
				<p v-else-if="number === 3">なぜそのことに取り組もうと考えたのですか</p>
				<p v-else-if="number === 4">現在、プログラミング学習 ではどのようなことを学習しているのですか</p>
				<p v-else-if="number === 5">プログラミングを学んでみた感想</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="NewText">memo</textarea>
				<img src="@/assets/face04.png" alt="">
				</div>
				<button class="NewButton" @click="next()" >{{down}}</button>
			</div>
			
			<div>{{finish}}</div>
		</div>
		<div v-else-if="part =='old'">
			<div class="contents" v-if="select=== 1">
				<div class="OldTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">前社で工夫した業務を教えてください</p>
				<p v-else-if="number === 3">その中で我が社に行かせそうなところを教えてください</p>
				<p v-else-if="number === 4">弱みを教えてください</p>
				<p v-else-if="number === 5">ありがとうございました。それでは何か質問はありませんか？</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="OldText">memo</textarea>
				<img src="@/assets/face01.png" alt="">
				</div>
				<button class="OldButton" @click="next()" >{{down}}</button>
			</div>
			<div class="contents" v-else-if="select===  2">
				<div class="OldTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてne</p>
				<p v-else-if="number === 2">あなたが頑張ったことを教えてください</p>
				<p v-else-if="number === 3">その中であなたが工夫したことを教えてください</p>
				<p v-else-if="number === 4">今回のあなたの就活軸を教えてください</p>
				<p v-else-if="number === 5">それを踏まえて弊社を志望する理由を教えてください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="OldText">memo</textarea>
				<img src="@/assets/face03.png" alt="">
				</div>
				<button class="OldButton" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 3">
				<div class="OldTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">あなたの自己PRを教えてください</p>
				<p v-else-if="number === 3">なぜこの職種を希望されたのですか</p>
				<p v-else-if="number === 4">それはなぜですか</p>
				<p v-else-if="number === 5">あなたの失敗談を教えてください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="OldText">memo</textarea>
				<img src="@/assets/face04.png" alt="">
				</div>
				<button class="OldButton" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 4">
				<div class="OldTitle">
					<p v-if="number=== 1">あなたの自己紹介を教えてください</p>
				<p v-else-if="number === 2">前社で力を入れてきたこと</p>
				<p v-else-if="number === 3">なぜそのことに取り組もうと考えたのですか</p>
				<p v-else-if="number === 4">現在、プログラミング学習ではどのようなことを学習しているのですか</p>
				<p v-else-if="number === 5">プログラミングを学んでみた感想</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="OldText">memo</textarea>
				<img src="@/assets/face02.png" alt="">
				</div>
				<button class="OldButton" @click="next()">{{down}}</button>
			</div>
			
			<div>{{finish}}</div>
		</div>
		<div v-else>
			<div class="contents" v-if="select=== 1">
				<div class="TechTitle">
					<p v-if="number=== 1">MVCの仕組みについて説明してください</p>
				<p v-else-if="number === 2">AWSとは何ですか？また、AWSの裏側ではどのような技術が動いていますか？</p>
				<p v-else-if="number === 3">Ruby の「include」とは何ですか？</p>
				<p v-else-if="number === 4">エラー解決はどのように行いますか？</p>
				<p v-else-if="number === 5">ログイン、ログアウトの仕組みを説明してください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="TechText">memo</textarea>
				<img src="@/assets/face01.png" alt="">
				</div>
				<button class="TechButton" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select===  2">
				<div class="TechTitle">
					<p v-if="number=== 1">オブジェクト指向とは何ですか？</p>
				<p v-else-if="number === 2">SQLとは何か説明してください</p>
				<p v-else-if="number === 3">SQLで具体的にどのようなことができますか？</p>
				<p v-else-if="number === 4">SQLの基本構文を教えてください</p>
				<p v-else-if="number === 5">クッキーとセッションの違いを説明してください</p>
				<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="TechText">memo</textarea>
				<img src="@/assets/face02.png" alt="">
				</div>
				<button class="TechButton" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 3">
				<div class="TechTitle">
					<p v-if="number=== 1">ブラウザにURLを打ち込んでサイトが表示されるまでの仕組みを教えてください</p>
					<p v-else-if="number === 2">好きなHTTPステータスコードを教えてください</p>
					<p v-else-if="number === 3">HTTPリクエストヘッダーはどのような役割を果たしていますか？</p>
					<p v-else-if="number === 4">エラー解決はどのように行いますか？</p>
					<p v-else-if="number === 5">アジャイル開発の利点を挙げてください</p>
					<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="TechText">memo</textarea>
				<img src="@/assets/face04.png" alt="">
				</div>
				<button class="TechButton" @click="next()">{{down}}</button>
			</div>
			<div class="contents" v-else-if="select=== 4">
				<div>
				<div class="TechTitle">
					<p v-if="number=== 1" >デスクトップPCとスマートフォンでは画面のサイズが異なりますが、どのように対応しますか？</p>
					<p v-else-if="number === 2">viewを作成するときにエンジニア目線で気をつけていることはありますか？</p>
					<p v-else-if="number === 3">データベースのトランザクションについて説明してください</p>
					<p v-else-if="number === 4">データベースのトランザクションについて説明してください</p>
					<p v-else-if="number === 5">Rubyの長所、短所について教えてください</p>
					<p v-else-if="number === 6">ありがとうございました。それでは何か質問はありませんか？</p>
				</div>
				<div class="flex">
					<textarea name="" id="" cols="30" rows="10" v-model="memo" placeholder="気になったことをメモ" class="TechText">memo</textarea>
				<img src="@/assets/face03.png" alt="">
				</div>
				<button class="TechButton" @click="next()">{{down}}</button>
			</div>
			</div>
			
			<div>{{finish}}</div>
		</div>
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
		},
		part: {
			type: String,
			default: "new"
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
	height: 600px;
}
textarea {
	width: 20%;
	outline: none;
}
p {
	font-size: 2rem;
	text-align: center;
	margin-bottom: 5%;
	width: 100%;
	}
button {
	outline: none;
}
button:active {
  /*ボタンを押したとき*/
  -webkit-transform: translateY(4px);
  transform: translateY(4px);/*下に動く*/
  border-bottom: none;/*線を消す*/
}
.NewTitle p{
  width: 100%;
  text-align: center;
  color:rgba(247, 205, 90, 0.548);
  margin: 50px auto;
  -webkit-text-stroke: 1px red;
  text-stroke: 1px red;
}
.OldTitle p{
  width: 100%;
  text-align: center;
  color:rgba(90, 247, 247, 0.548);
  margin: 50px auto;
  -webkit-text-stroke: 1px blue;
  text-stroke: 1px blue;
}
.TechTitle p{
  width: 100%;
  text-align: center;
  color:rgba(148, 247, 90, 0.548);
  margin: 50px auto;
  -webkit-text-stroke: 1px green;
  text-stroke: 1px green;
}
.NewButton  {
  color: red;
  background:rgba(247, 205, 90, 0.548);
  border:1px solid rgb(255, 0, 0);
  border-radius: 20px;
  border-bottom: solid 4px rgba(255, 0, 0, 0.822);
	width: 10%;
	font-size: 1.5rem;
	padding: 5px;
	margin: 10px auto;
}
.OldButton {
  color: blue;
  background:rgba(90, 247, 247, 0.548);
  border:1px solid blue;
  border-radius: 20px;
  border-bottom: solid 4px rgba(25, 0, 255, 0.822);
	width: 10%;
	font-size: 1.5rem;
	padding: 5px;
	margin: 10px auto;
}
.TechButton {
  color: rgb(0, 128, 0);
  background:rgba(148, 247, 90, 0.548);
  border:1px solid green;
  border-radius: 20px;
  border-bottom: solid 4px rgba(0, 128, 0, 0.822);
	width: 10%;
	font-size: 1.5rem;
	padding: 5px;
	margin: 10px auto;
}
.NewText {
  color: red;
  background:rgba(247, 205, 90, 0.548);
  border:1px solid rgb(255, 0, 0);
  border-radius: 20px;
	width: 30%;
	font-size: 1rem;
	padding: 5px;
	margin: 0 5px;
}
.OldText {
  color: blue;
  background:rgba(90, 247, 247, 0.548);
  border:1px solid blue;
  border-radius: 20px;
	width: 30%;
	font-size: 1rem;
	padding: 5px;
	margin: 0 5px;
}
.TechText {
  color: rgb(0, 128, 0);
  background:rgba(148, 247, 90, 0.548);
  border:1px solid green;
  border-radius: 20px;
	width: 30%;
	font-size: 1rem;
	padding: 5px;
	margin: 0 5px;
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