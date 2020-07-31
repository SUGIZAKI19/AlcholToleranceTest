<template>
  <div id="app">
    <div class="container">
    <img src="@/assets/scouter_logo.png">

    <div style="text-align:left; max-width:720px; margin:auto;">
      <h3 class="border-bottom py-2">
        <v-fa icon="info-circle"/>
        このアプリについて
      </h3>
      <p>このアプリでは, 13項目の質問に答えるだけで，自分が体質的にお酒に強いかどうかを判定することができます。</p>

      <p><span style="font-weight:bold;">-45</span>点から<span style="font-weight:bold;">25.62</span>点の間で得点化されます。0点以上だとお酒に強く，そうでなければお酒に弱いと判定が下されます。</p>

      <h3 class="border-bottom py-2">
        <v-fa icon="info-circle"/>
        注意事項
      </h3>
      <p>本アプリは、体質を測るためのものであり決して人の優劣をつけるものではございません。</p>
      <p>このテストの結果が誰かの生活の指針になれば幸いです。</p>
    </div>

      <div class="inputGroup p-2">
        <div class="questionHeader p-3" style="text-align: left">
          1. 顔が赤くなる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="1_a">
            <input class="answer-option" type="radio" name="q1" value=-10 v-model="score[0]" id="1_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="1_b">
            <input class="answer-option" type="radio" name="q1" value=5.22 v-model="score[0]" id="1_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="1_c">
            <input class="answer-option" type="radio" name="q1" value=8.95 v-model="score[0]" id="1_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          2. 顔意外の部分が赤くなる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="2_a">
            <input class="answer-option" type="radio" name="q2" value=-0.43 v-model="score[1]" id="2_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="2_b">
            <input class="answer-option" type="radio" name="q2" value=-2.98 v-model="score[1]" id="2_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="2_c">
            <input class="answer-option" type="radio" name="q2" value=1.2 v-model="score[1]" id="2_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          3. かゆくなる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="3_a">
            <input class="answer-option" type="radio" name="q3" value=3.37 v-model="score[2]" id="3_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="3_b">
            <input class="answer-option" type="radio" name="q3" value=-3.89 v-model="score[2]" id="3_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="3_c">
            <input class="answer-option" type="radio" name="q3" value=0.38 v-model="score[2]" id="3_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          4. めまいがする
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="4_a">
            <input class="answer-option" type="radio" name="q4" value=-0.58 v-model="score[3]" id="4_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="4_b">
            <input class="answer-option" type="radio" name="q4" value=-1.27 v-model="score[3]" id="4_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="4_c">
            <input class="answer-option" type="radio" name="q4" value=0.25 v-model="score[3]" id="4_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          5. 眠くなる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="5_a">
            <input class="answer-option" type="radio" name="q5" value=0.31 v-model="score[4]" id="5_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="5_b">
            <input class="answer-option" type="radio" name="q5" value=0.36 v-model="score[4]" id="5_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="5_c">
            <input class="answer-option" type="radio" name="q5" value=-1.03 v-model="score[4]" id="5_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          6. 不安になる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="6_a">
            <input class="answer-option" type="radio" name="q6" value=0 v-model="score[5]" id="6_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="6_b">
            <input class="answer-option" type="radio" name="q6" value=-4.11 v-model="score[5]" id="6_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="6_c">
            <input class="answer-option" type="radio" name="q6" value=-0.1 v-model="score[5]" id="6_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          7. 頭が痛くなる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="7_a">
            <input class="answer-option" type="radio" name="q7" value=-0.79 v-model="score[6]" id="7_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="7_b">
            <input class="answer-option" type="radio" name="q7" value=0.07 v-model="score[6]" id="7_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="7_c">
            <input class="answer-option" type="radio" name="q7" value=0.01 v-model="score[6]" id="7_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          8. 頭の中が打つように感じる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="8_a">
            <input class="answer-option" type="radio" name="q8" value=0.83 v-model="score[7]" id="8_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="8_b">
            <input class="answer-option" type="radio" name="q8" value=0.62 v-model="score[7]" id="8_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="8_c">
            <input class="answer-option" type="radio" name="q8" value=-0.24 v-model="score[7]" id="8_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          9. 汗をかく
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="9_a">
            <input class="answer-option" type="radio" name="q9" value=-3.25 v-model="score[8]" id="9_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="9_b">
            <input class="answer-option" type="radio" name="q9" value=1.43 v-model="score[8]" id="9_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="9_c">
            <input class="answer-option" type="radio" name="q9" value=-0.44 v-model="score[8]" id="9_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          10. 心臓がドキドキする
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="10_a">
            <input class="answer-option" type="radio" name="q10" value=-1.88 v-model="score[9]" id="10_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="10_b">
            <input class="answer-option" type="radio" name="q10" value=0.04 v-model="score[9]" id="10_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="10_c">
            <input class="answer-option" type="radio" name="q10" value=0.26 v-model="score[9]" id="10_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          11. 吐き気がする
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="11_a">
            <input class="answer-option" type="radio" name="q11" value=-10.1 v-model="score[10]" id="11_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="11_b">
            <input class="answer-option" type="radio" name="q11" value=0.19 v-model="score[10]" id="11_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="11_c">
            <input class="answer-option" type="radio" name="q11" value=0.03 v-model="score[10]" id="11_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          12. 寒気がする
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="12_a">
            <input class="answer-option" type="radio" name="q12" value=8.15 v-model="score[11]" id="12_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="12_b">
            <input class="answer-option" type="radio" name="q12" value=-2.42 v-model="score[11]" id="12_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="12_c">
            <input class="answer-option" type="radio" name="q12" value=0.14 v-model="score[11]" id="12_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>

      <div class="inputGroup p-2 mt-2">
        <div class="questionHeader p-3" style="text-align: left">
          13. 息苦しくなる
        </div>
        <div class="inputAnswer row p-3 mt-2">
          <label class="answer col-4 px-2" for="13_a">
            <input class="answer-option" type="radio" name="q13" value=-4.34 v-model="score[12]" id="13_a">
            <span class="answer-text">いつも出る</span>
          </label>

          <label class="answer col-4 px-2" for="13_b">
            <input class="answer-option" type="radio" name="q13" value=2.69 v-model="score[12]" id="13_b">
            <span class="answer-text">時々出る</span>
          </label>

          <label class="answer col-4 px-2" for="13_c">
            <input class="answer-option" type="radio" name="q13" value=-0.19 v-model="score[12]" id="13_c">
            <span class="answer-text">出ない</span>
          </label>
        </div>
      </div>
    </div>

    <div class ="container">
      <template v-if ="!validation">
        <b-button
          v-on:click ="display_alert();"
          class="btn btn-lg col-6 mb-5"
          variant="outline-success"
          >Calculate!</b-button>
      </template>
      <template v-else>
        <b-button
          v-on:click ="sum();display();"
          class="btn btn-lg col-6 mb-5"
          variant="outline-success">Calculate!</b-button>
      </template>
    </div>


    <!--https://qiita.com/ykhirao/items/1ff89bd157bc9480d899
      イベントを二つ持たせるとき
    -->

    <div class ="container result" v-show="show">
      <template class="heavy" v-if="totalScore > 0">
        <div class="card mb-3 border-success">
          <div class="card-header bg-success text-white ">{{name}}さんの診断結果</div>
          <div class="card-body" style="text-align:left;">
            <h4 class="card-title text-success">アルコール感受性スコア: {{totalScore}}点</h4>
            <p class="card-text">お酒に強い体質をお持ちのようです！<br>お酒は快適に飲めますが，くれぐれも飲み過ぎないように！</p>
          </div>

          <b-button type="reset"
            value ="リセット"
            v-on:click="pop"
            class="btn btn-lg m-4 col-10"
            variant="outline-success">もういちど挑戦する</b-button>
        </div>
      </template>

      <template v-else-if ="totalScore <=0">
        <div class="card mb-3 border-danger">
          <div class="card-header bg-danger text-white">{{name}}さんの診断結果</div>
          <div class="card-body" style="text-align:left;">
            <h4 class="card-title text-danger">アルコール感受性スコア: {{totalScore}}点</h4>
            <p class="card-text">どうやらお酒に弱いみたいです…(´・ω・｀)</p>
            <p class="card-text">でも気を落とさないで！<br>飲めないのは生まれつきの体質で，引け目を感じることはありません！</p>
            <p class="card-text">堂々と飲めないことを宣言して，すすめられてもキッパリ断ってください．</p>
          </div>

          <b-button type="reset"
            value ="リセット"
            v-on:click="pop"
            class="btn btn-lg m-4 col-10"
            variant="outline-danger">もういちど挑戦する</b-button>
        </div>
      </template>
    </div>

  </div>
</template>

<script>
export default{
  data(){
    return {
      name: "",
      comment: 0,
      score: [ ],
      totalScore: null,
      show: false, //診断結果出現
      alert: false, //未回答バルーン出現
      calledComponent: null
    }
  },
  methods:{
    sum:function(){
      let sum =0;
      for (const item of this.score){
        sum +=Number(item);
      }
      this.totalScore = sum.toFixed(2);
    },
    display:function(){
      this.show = true;
    },
    display_alert: function(){ //アラートバルーンの出現
      this.alert= true;
    },
    pop: function(){ //リアクティブに配列の初期化
      this.show = false;
      this.totalScore = null;
      this.score.splice(-this.score.length);
      this.alert=false;
    }
  },
  computed:{
    validation: function(){ //リアルタイムでバリデーション
      if(this.score==0){
        return false;
      }
      else{
        for(const item of this.score){
          if(item == null || this.score.length <13){
            return false;
          }
        }
        return true;
      }
    }
  }
}

</script>


<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container{

}

.inputGroup{
  max-width:720px;
  min-width:380px;
  margin:auto;
}

.questionHeader{
  background-color: rgb(250,189,132);
  border-radius:10px;
}

* {
  box-sizing: border-box;
}

*::before {
  box-sizing: border-box;
}

*::after {
  box-sizing: border-box;
}

.answer-option {
  opacity: 0;
  appearance: none;
  position: absolute;
}

.answer-text {
  position: relative;
  display: flex;
  align-items: center;
  font-size: 1.125rem;
}

.answer-text::before {
  content: '';
  display: block;
  border-radius: 50%;
  border: 1px solid rgb(250,189,132);
  width: 24px;
  height: 24px;
}

.answer-option:checked+.answer-text::after {
  content: '';
  position: absolute;
  left: calc(12px - 7.5px);
  display: block;
  border-radius: 50%;
  width: 15px;
  height: 15px;
  background-color: rgb(250,189,132);
}



</style>
