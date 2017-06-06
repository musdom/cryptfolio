<template>
  <div class="hello">

    <section class="section" style="background-color: #302f33;">
      <div class="hero-head">
        <div class="container " >


          <div class="box">
            <div class="columns is-mobile">
              <div class="column is-narrow">
                <figure class="image is-96x96">
                  <img src="../assets/images/bitcoin.png">
                </figure>
              </div>
              <div class="column cfcenter">
                <h1 class="title">Title</h1>
              </div>
            </div>
          </div>

          <div class="box">
            <div class="columns is-mobile">
              <div class="column is-narrow">
                <figure class="image is-96x96">
                  <img src="../assets/images/nem.png">
                </figure>
              </div>
              <div class="column cfcenter">
                <h1 class="title">Title</h1>
              </div>
            </div>
          </div>

          <div class="box">
            <div class="columns is-mobile">
              <div class="column is-narrow">
                <figure class="image is-96x96">
                  <img src="../assets/images/zcoin.png">
                </figure>
              </div>
              <div class="column cfcenter">
                <h1 class="title">Title</h1>
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
  // name: 'hello',
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
      console.log(this.rates.xem);
    },

  },

  created: function() {
    console.log(`XEM = 1 BTC`);
    this.rates.xem = 1;
    // this.$http.get('https://poloniex.com/public?command=returnTicker')
    //   .then(function(res) {
    //     console.log(`XEM = ${res.data.BTC_XEM.last} BTC`);
    //     this.rates.xem = res.data.BTC_XEM.last;
    //   })
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
