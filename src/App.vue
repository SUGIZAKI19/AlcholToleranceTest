<template>
  <div id="app">
    <div class="container">

      <!--アラートバルーン-->
      <template v-if="alert">
        <div class="alert alert-danger alert-dismissible fade show" role="alert">
          <strong><font-awesome-icon icon="coffee" /></strong>
          未回答の項目があります！
          <button
            type="button"
            class="close"
            data-dismiss="alert"
            aria-label="Close"
            v-on:click ="alert=false"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
      </template>

      <!---->
      <form method="post">
        <div class="input-group mb-4">
        <div class="input-group-prepend">
          <span class="input-group-text" id="inputGroup-sizing-sm">Name</span>
        </div>
          <input id ="name" type="text" name="name" class="form-control" v-model ="name">
        </div>

        <table class="table table-hover  table-bordered">
          <thead class="table-dark">
            <tr>
              <th>No</th>
              <th>症状</th>
              <th>いつも出る</th>
              <th>時々出る</th>
              <th>出ない</th>
            </tr>
          </thead>
          <tbody>

            <tr>
              <td>1</td>
              <td>顔が赤くなる</td>
              <td><input type="radio" name="q1" value=-10 v-model="score[0]"></td>
              <td><input type="radio" name="q1" value=5.22 v-model="score[0]"></td>
              <td><input type="radio" name="q1" value=8.95 v-model="score[0]"></td>
            </tr>

            <tr>
              <td>2</td>
              <td>顔以外の部分が赤くなる</td>
              <td><input type="radio" name="q2" value=-0.43 v-model="score[1]"></td>
              <td><input type="radio" name="q2" value=-2.98 v-model="score[1]"></td>
              <td><input type="radio" name="q2" value=-1.2 v-model="score[1]"></td>
            </tr>

            <tr>
              <td>3</td>
              <td>痒くなる</td>
              <td><input type="radio" name="q3" value=3.37 v-model="score[2]"></td>
              <td><input type="radio" name="q3" value=-3.89 v-model="score[2]"></td>
              <td><input type="radio" name="q3" value=0.38 v-model="score[2]"></td>
            </tr>

            <tr>
              <td>4</td>
              <td>めまいがする</td>
              <td><input type="radio" name="q4" value=-0.58 v-model="score[3]"></td>
              <td><input type="radio" name="q4" value=-1.27 v-model="score[3]"></td>
              <td><input type="radio" name="q4" value=0.25 v-model="score[3]"></td>
            </tr>

            <tr>
              <td>5</td>
              <td>眠くなる</td>
              <td><input type="radio" name="q5" value=0.31 v-model="score[4]"></td>
              <td><input type="radio" name="q5" value=0.36 v-model="score[4]"></td>
              <td><input type="radio" name="q5" value=-1.03 v-model="score[4]"></td>
            </tr>

            <tr>
              <td>6</td>
              <td>不安になる</td>
              <td><input type="radio" name="q6" value=0 v-model="score[5]"></td>
              <td><input type="radio" name="q6" value=-4.11 v-model="score[5]"></td>
              <td><input type="radio" name="q6" value=0.1 v-model="score[5]"></td>
            </tr>

            <tr>
              <td>7</td>
              <td>頭が痛くなる</td>
              <td><input type="radio" name="q7" value=-0.79 v-model="score[6]"></td>
              <td><input type="radio" name="q7" value=0.07 v-model="score[6]"></td>
              <td><input type="radio" name="q7" value=0.01 v-model="score[6]"></td>
            </tr>

            <tr>
              <td>8</td>
              <td>頭の中が打つように感じる</td>
              <td><input type="radio" name="q8" value=0.83 v-model="score[7]"></td>
              <td><input type="radio" name="q8" value=0.62 v-model="score[7]"></td>
              <td><input type="radio" name="q8" value=-0.24 v-model="score[7]"></td>
            </tr>

            <tr>
              <td>9</td>
              <td>汗をかく</td>
              <td><input type="radio" name="q9" value=-3.25 v-model="score[8]"></td>
              <td><input type="radio" name="q9" value=1.43 v-model="score[8]"></td>
              <td><input type="radio" name="q9" value=-0.44 v-model="score[8]"></td>
            </tr>

            <tr>
              <td>10</td>
              <td>心臓がドキドキする</td>
              <td><input type="radio" name="q10" value=0.79 v-model="score[9]"></td>
              <td><input type="radio" name="q10" value=0.07 v-model="score[9]"></td>
              <td><input type="radio" name="q10" value=0.01 v-model="score[9]"></td>
            </tr>

            <tr>
              <td>11</td>
              <td>吐き気がする</td>
              <td><input type="radio" name="q11" value=-10.1 v-model="score[10]"></td>
              <td><input type="radio" name="q11" value=0.19 v-model="score[10]"></td>
              <td><input type="radio" name="q11" value=0.03 v-model="score[10]"></td>
            </tr>

            <tr>
              <td>12</td>
              <td>寒気がする</td>
              <td><input type="radio" name="q12" value=8.15 v-model="score[11]"></td>
              <td><input type="radio" name="q12" value=-2.42 v-model="score[11]"></td>
              <td><input type="radio" name="q12" value=0.14 v-model="score[11]"></td>
            </tr>

            <tr>
              <td>13</td>
              <td>息苦しくなる</td>
              <td><input type="radio" name="q13" value=-4.34 v-model="score[12]"></td>
              <td><input type="radio" name="q13" value=2.69 v-model="score[12]"></td>
              <td><input type="radio" name="q13" value=-0.19 v-model="score[12]"></td>
            </tr>

          </tbody>
        </table>
        <!--https://www.tagindex.com/html_tag/form/input_radio.htmlより引用-->
      </form>
    </div>


    <div class ="container">
      <template v-if ="!validation">
        <button v-on:click ="display_alert();" class="btn btn-success btn-lg  col-5">Calculate!</button>
      </template>
      <template v-else>
        <button v-on:click ="sum(); display();" class="btn btn-success btn-lg  col-5">Calculate!</button>
      </template>
      <button type="reset" value ="リセット" v-on:click="pop" class="btn btn-danger btn-lg  col-5 m-4">Reset</button>
    </div>


    <!--https://qiita.com/ykhirao/items/1ff89bd157bc9480d899
      イベントを二つ持たせるとき
    -->

    <div class ="container result" v-show="show">
      <template class="heavy" v-if="totalScore > 0">
        <div class="card mb-3 border-success">
          <div class="card-header bg-success text-white ">{{name}}さんの診断結果</div>
          <div class="card-body">
            <h4 class="card-title text-success">アルコール感受性スコア: {{totalScore}}点</h4>
            <p class="card-text">お酒に強い体質をお持ちのようです！</p>
            <p class="card-text">お酒は快適に飲めますが，くれぐれも飲み過ぎないように！</p>
          </div>
        </div>
      </template>

      <template v-else-if ="totalScore <=0">
        <div class="card mb-3 border-danger">
          <div class="card-header bg-danger text-white">{{name}}さんの診断結果</div>
          <div class="card-body">
            <h4 class="card-title text-danger">アルコール感受性スコア: {{totalScore}}点</h4>
            <p class="card-text">どうやらお酒に弱いみたいです…(´・ω・｀)</p>
            <p class="card-text">でも気を落とさないで！飲めないのは生まれつきの体質で，引け目を感じることはありません！</p>
            <p class="card-text">堂々と飲めないことを宣言して，すすめられてもキッパリ断ってください．</p>
          </div>
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

</style>
