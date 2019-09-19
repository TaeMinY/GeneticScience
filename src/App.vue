<template>
  <div id="app">
    <div id="screen">

      <v-text-field  required v-model="viewtext" autocomplete="off" type="text" placeholder="띄여쓰기,소문자 금지"></v-text-field>
      <div>{{view}}</div>
      <div>
        전사:
        <span v-for="a in arr" :key="a">
          {{a}}
        </span>
      </div>
      <div>
        번역:
        <span v-for="a in end" :key="a">
          {{a}}
        </span>
      </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      view : "입력해주세요",
      viewtext: "",
      changea : "",
      end: [],
      arr : [],
      tra : [{
        name : "UUU",
        opt : "페닐알라닌",
      },
      {
        name : "페닐알라닌",
        opt : "UUC"
      },
      {
        name : "류신",
        opt : "UUA"
      },
      {
        name : "류신",
        opt : "UUG"
      },
      {
        name : "류신",
        opt : "CUU"
      },
      {
        name : "류신",
        opt : "CUC"
      },
      {
        name : "류신",
        opt : "CUA"
      },
      {
        name : "류신",
        opt : "CUG"
      },
      {
        name : "아이소류신",
        opt : "AUU"
      },
      {
        name : "아이소류신",
        opt : "AUC"
      },
      {
        name : "아이소류신",
        opt : "AUA"
      },
      {
        name : "메싸이오닌",
        opt : "AUG" 
      },
      {
        name : "발린",
        opt :  "GUU"
      },
      {
        name : "발린",
        opt : "GUC"
      },
      {
        name : "발린",
        opt : "GUA" 
      },
      {
        name : "발린",
        opt : "GUG" 
      },
      {
        name : "세린",
        opt : "UCU" 
      },
      {
        name : "세린",
        opt : "UCC" 
      },
      {
        name : "세린",
        opt : "UCA" 
      },
      {
       name : "세린",
        opt :  "UCG"
        
      },
      {
        name : "프롤린",
        opt :  "CCU"
      },
      {
        name : "프롤린",
        opt : "CCC" 
      },
      {
        name : "프롤린",
        opt : "CCA" 
      },
      {
        name : "프롤린",
        opt : "CCG" 
      },
      {
        name : "트레오닌",
        opt : "ACU" 
      },
      {
        name : "트레오닌",
        opt : "ACC"
      },
      {
        name : "트레오닌",
        opt :  "ACA"
        
      },
      {
         name: "트레오닌",
        opt :"ACG"  
      },
      { 
        name : "알라닌",
        opt : "GCU" 
      },
      {
        name:"알라닌",
        opt : "GCC" 
      },
      {
        name:"알라닌",
        opt :"GCA" 
      },
      {
        name:"알라닌",
        opt : "GCG" 
      },
      {
        name:"타이로신",
        opt : "UAU"
      },
      {
        name:"타이로신",
        opt :"UAC" 
      },
      {
        name :"종결코돈",
        opt :"UAA" 
      },
      {
        name :"종결코돈",
        opt : "UAG"
      },
      {
        name :"종결코돈",
        opt : "UGA"
      },
      {
        name :"히스티딘",
        opt : "CAU"
      },
      {
        name :"히스티딘",
        opt : "CAC" 
      },
      {
        name :"글루타민",
        opt : "CAA"
      },
      {
        name :"글루타민",
        opt :"CAG" 
      },
      {
        name :"아스파라진",
        opt : "AAU"
      },
      {
        name :"아스파라진",
        opt :"AAC" 
      },
      {
        name :"라이신",
        opt :"AAA" 
      },
      {
        name :"라이신",
        opt :"AAG" 
      },
      {
        name :"아스파트산",
        opt : "GAU"
      },
      {
        name :"아스파트산",
        opt : "GAC" 
      },
      {
        name :"글루탐산",
        opt :"GAA" 
      },
      {
        name :"글루탐산",
        opt : "GAG"
      },
      {
        name :"시스테인",
        opt : "UGU"
      },
      {
        name :"시스테인",
        opt : "UGC"
      },
      {
        name :"트립토판",
        opt : "UGG"
      },
      {
        name :"아르지닌",
        opt :"CGU" 
      },
      {
        name :"아르지닌",
        opt : "CGC"
      },
      {
        name :"아르지닌",
        opt :"CGA" 
      },
      {
        name :"아르지닌",
        opt :"CGG" 
      },
      {
        name :"세린",
        opt :"AGU" 
      },
      {
        name :"세린",
        opt :"AGC" 
      },
      {
        name :"아르지난",
        opt :"AGA" 
      },
      {
        name :"아르지난",
        opt : "AGG"
      },
      {
        name :"글라이신",
        opt : "GGU"
      },
      {
        name :"글라이신",
        opt :"GGC" 
      },
      {
        name :"글라이신",
        opt :"GGA" 
      },
      {
        name :"글라이신",
        opt :"GGG" 
      },
      ]
    }
  },
  watch: {
    viewtext : function() {
              this.arr = []
              this.end = []
      if(this.viewtext == ""){
        this.view = "현재 입력하지 않았습니다"
      }
      else{
        for(let i = 0; i < this.viewtext.length ; i++){
          if(this.viewtext[i] == "G"){
            this.arr[i] = "C"
          }else if(this.viewtext[i] == "C"){
            this.arr[i] = "G"
          }else if(this.viewtext[i] == "T"){
            this.arr[i] = "A"
          }else if(this.viewtext[i] == "A"){
            this.arr[i] = "U"
          }else{
            this.view = "이상합니다...."
            break;
          }
          this.view = ""
        }
      }
      if(this.view != "이상합니다...."){
        for(let j = 0; j < this.arr.length ; j = j+3){
          var gg = "";
          for(let k = 0 ; k < 3 ;k++){
            gg+=this.arr[k+j]
          }
          if(this.arr.length > 2){
            for(let k = 0 ; k < this.tra.length; k++){
              if(gg == this.tra[k].opt){
                this.end.push(this.tra[k].name)
              }
           }
          }
          if(this.end[0] != "메싸이오닌"){
        this.end = [];
        this.view = "개시코돈을 작성하지 않았습니다."
      }
        }
        
      }else{
      }
      
      
      
  }
},
  methods: {
  },
};
</script>
<style scoped>
#app{
  width: 100vw;
  height:100vh;
  display:flex;
  justify-content: center;
  align-items: center;
}
#screen{
  width: 80%;
  height: 70%;
}
</style>