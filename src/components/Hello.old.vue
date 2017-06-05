<template>
  <div class="hello">
    <div class="tabs" style="background-color: #fff;">
      <div class="column cfheader is-narrow">
        <a>
          Cryptofolio
        </a>
      </div>
      <div class="column cfheader">
        <ul>
          <li v-for="item in headerTabs" v-bind:class='{"is-active": isActive(item)}' v-on:click='toggle(item)'><a>{{ item.message }}</a></li>
        </ul>
    </div>
    </div>

    <section class="section" style="background-color: #3273dc;">
      <div class="hero-head">
        <div class="container " >

          <div class="box">

            <div class="notification" style="background-color: #dcdcdc;">
              <h1 class="title is-1 has-text-centered" >{{msg}}</h1>
              <p v-if="rates.xem">XEM = {{rates.xem}} BTC</p>
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
      activeMessage: {
        message: 'Dashboard'
      },
      headerTabs: [{
        message: 'Dashboard'
      }, {
        message: 'Create'
      }, {
        message: 'Audit'
      }],
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

    toggle: function(item) {
      console.log(JSON.stringify(item));
      this.activeMessage = item;
    },
    isActive: function(item) {
      return this.activeMessage.message === item.message
    }
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
