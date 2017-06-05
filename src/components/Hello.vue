<template>
  <div class="hello">

    <section class="section" style="background-color: #3273dc;">
      <div class="hero-head ">
        <div class="container " >

          <div class="box">

            <div class="notification" style="background-color: #dcdcdc;">
              <h1 class="title is-1 has-text-centered" >{{msg}}</h1>
              <p v-if=rates.xem>XEM = {{rates.xem}} BTC</p>
            </div>

            <div class="columns">
              <div class="column is-4">
                <input class="input is-large" v-model="msg" type="text">
              </div>

              <div class="column">
                <a class="button is-large is-info" v-on:click="convertToBTC" >Submit</a>
              </div>
            </div>

          </div>
        </div>
      </div>
    </section>


  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      rates: {
        xem: null,
        xzc: null,
      }
    }
  },
  methods: {
    convertToBTC: function() {
      console.log(this.msg);
    }
  },

  created: function() {
    this.$http.get('https://poloniex.com/public?command=returnTicker')
      .then(function(res) {
        console.log(`XEM = ${res.data.BTC_XEM.last} BTC`);
        this.rates.xem = res.data.BTC_XEM.last;
      })
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/*h1, h2 {
  font-weight: normal;
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
}*/
</style>
