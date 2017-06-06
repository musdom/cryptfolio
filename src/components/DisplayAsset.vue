<template>

          <div class="box">
            <div class="columns is-mobile">
              <div class="column is-narrow">
                <figure class="image is-96x96">
                  <img :src="getIcon(asset.name)">
                </figure>
              </div>
              <div class="column cfcenter">
                <h1 class="title">{{getBalance}}</h1>
                <h3 class="subtitle">{{asset.imgSrc}}</h3>
                <p>{{asset.addresses}}</p>
              </div>
            </div>
          </div>

</template>

<script>
export default {
  name: 'display-asset',
  props: ['asset'],

  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      rates: {
        xem: null,
        xzc: null,
      },
    }
  },
  methods: {
    getIcon(pic) {
      let images = require.context('../assets/images', false, /\.png$/);
      return images('./' + pic + ".png");
    },
    getBalance: function() {
      this.$http.get("https://explorer.zcoin.io/ext/getbalance/" + this.asset.addresses[0])
        .then(function(res) {
          console.log(res);
          return res;
        })

    },
    convertToBTC: function() {
      console.log(this.msg);
      console.log(this.rates.xem);
    },

  },

  created: function() {
    console.log(`XEM = 1 BTC`);
    console.log(this.asset.imgSrc);
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
