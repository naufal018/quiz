<template>
  <div class="hello">
    <h1 v-if="show">{{ msg }}</h1>
    <h1 v-else>Judul Disembunyikan</h1>
    <p>Skor : {{skor}}/3</p>
    <p>{{ nama}}</p>
    <input type="text" v-model="nama">
    <button type="button" v-on:click="hideTitle">Click Me</button>
    <br>
    <!--SOAL1-->
    <li v-for="s in soal">
    <h3>{{s}}</h3>
    <jawaban1 v-for="j in jawaban1">
    <br>
    <input type="radio" v-on:click="increment" value="A. Palembang">
    {{j}}
    </jawaban1>
    <br>
    <jawaban2 v-for="a in jawaban2">
    <input type="radio" v-on:click="increment" value="B. Jakarta">
    {{a}}
    </jawaban2>
    <br>
    <jawaban3 v-for="w in jawaban3">
    <input type="radio" v-on:click="increment" value="C. Papua">
    {{w}}
    </jawaban3>
    <br>
    <jawaban4 v-for="b in jawaban4">
    <input type="radio" v-on:click="increment" value="D. Bali">
    {{b}}
    </jawaban4>
    <!--SOAL2-->
      <li v-for="o in soal2">
    <h3>{{o}}</h3>
    <option1 v-for="p in option1">
    <br>
    <input type="radio" v-on:click="increment" value="A. Bandung">
    {{p}}
    </option1>
    <br>
    <option2 v-for="t in option2">
    <input type="radio" v-on:click="increment" value="B. Jakarta">
    {{t}}
    </option2>
    <br>
    <option3 v-for="i in option3">
    <input type="radio" v-on:click="increment" value="C. Yogyakarta">
    {{i}}
    </option3>
    <br>
    <option4 v-for="n in option4">
    <input type="radio" v-on:click="increment" value="D. Semarang">
    {{n}}
    </option4>
     <!--SOAL3-->
      <li v-for="l in soal3">
    <h3>{{l}}</h3>
    <choose1 v-for="c in choose1">
    <br>
    <input type="radio" v-on:click="increment" value="A. Soekarno">
    {{c}}
    </choose1>
    <br>
    <choose2 v-for="e in choose2">
    <input type="radio" v-on:click="increment" value="B. Prabowo">
    {{e}}
    </choose2>
    <br>
    <choose3 v-for="s in choose3">
    <input type="radio" v-on:click="increment" value="C. Megawati">
    {{s}}
    </choose3>
    <br>
    <choose4 v-for="h in choose4">
    <input type="radio" v-on:click="increment" value="D. SBY">
    {{h}}
    </choose4>
    </li>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data : function() {
  return{
    nama: 'Naufal',
    show: true,
    skor: 0,
    soal : ['1. Apakah Ibukota dari negara Indonesia ?'],
    jawaban1 : ['A. Palembang'],
    jawaban2 : ['B. Jakarta'],
    jawaban3 : ['C. Papua'],
    jawaban4 : ['D. Bali'],
    soal2 : ['2. Dimana letak Candi Borobudur ?'],
    option1 : ['A. Bandung'],
    option2 : ['B. Jakarta'],
    option3 : ['C. Yogyakarta'],
    option4 : ['D. Semarang'],
    soal3 : ['3. Presiden pertama Indonesia adalah......'],
    choose1 : ['A. Soekarno'],
    choose2 : ['B. Prabowo'],
    choose3 : ['C. Megawati'],
    choose4 : ['D. SBY']
    }
    },
  methods: {
    hideTitle() {
      this.show = !this.show
    },
    increment() {
    var value = event.target.value;
    if (value === "B. Jakarta"){
    this.skor++;
    }else if (value === "C. Yogyakarta"){
    this.skor++;
    }else if (value === "A. Soekarno"){
    this.skor++;
    }else{
			this.skor--;
		}
    }
  },
  mounted: function () {
    this.nama = 'Naufal'
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
