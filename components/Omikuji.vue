<template>
  <div class="omikuji">
    <h1>{{ msg }}</h1>
    <div @click="btnChange()" id="btn">おみくじルーレット</div>
    <div @click="btnChangeTwo()" id="btnTwo">おみくじルーレット</div>
  </div>
</template>

<script>
export default {
  name: "Omikuji",
  props: {
    msg: String,
  },
  methods: {
    //配列の中身をrandomに行うやり方
    btnChange() {
      const results = ["大吉", "中吉", "小吉", "末吉"]
      const btn = document.getElementById("btn")
      const n = Math.floor(Math.random() * results.length)
      btn.textContent = results[n]
    },
    //確率を与えたい場合
    btnChangeTwo() {
      const btnTwo = document.getElementById("btnTwo")
      const n = Math.random();
      if (n < 0.05) {
        btnTwo.textContent = '大吉'; // 5%
      } else if (n < 0.2) {
        btnTwo.textContent = '中吉'; // 15%
      } else {
        btnTwo.textContent = '凶'; // 80%
      }
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#btn {
  width: 100px;
  height: 100px;
  background: #ef454a;
  border-radius: 50%;
  margin: 30px auto;
  text-align: center;
  line-height: 100px;
  color: #fff;
  font-weight: bold;
  font-size: 10px;
  cursor: pointer;
  box-shadow: 0 10px 0 #d1483e;
  user-select: none;
}
#btn:hover {
  opacity: 0.9;
}
#btn:active {
  box-shadow: 0 5px 0 #d1483e;
  margin-top: 35px;
}
h1 {
  font-size: 10px;
}
#btnTwo {
  width: 100px;
  height: 100px;
  background: #ef454a;
  border-radius: 50%;
  margin: 30px auto;
  text-align: center;
  line-height: 100px;
  color: #fff;
  font-weight: bold;
  font-size: 10px;
  cursor: pointer;
  box-shadow: 0 10px 0 #d1483e;
  user-select: none;
}
#btnTwo:hover {
  opacity: 0.9;
}
#btnTwo:active {
  box-shadow: 0 5px 0 #d1483e;
  margin-top: 35px;
}
</style>