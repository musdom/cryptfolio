<template>
  <div id="app">

    <section class="section" style="background-color: #302f33;">
      <div class="hero-head">
        <div class="container " >

          <display-asset
            v-for="(asset, id) in assets"
            v-bind:asset="asset"
            v-bind:key="asset.id">
          </display-asset>

        </div>
      </div>
    </section>


  </div>
</template>

<script>
import DisplayAsset from './components/DisplayAsset'

export default {
  name: 'app',
  components: {
    DisplayAsset
  },

  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      rates: {
        xem: null,
        xzc: null,
      },
      assets: [
        {
          name: "bitcoin",
          // id: 0,
          addresses: [],
          imgSrc: "../assets/images/bitcoin.png"
        },
        {
          name: "nem",
          // id: 1,
          addresses: [],
          imgSrc: "../assets/images/nem.png"
        },
        {
          name: "zcoin",
          // id: 2,
          addresses: [
            "a5TKgRkNLahApJ6amFvkGZPiCeNioRUjnt"
          ],
          imgSrc: "../assets/images/zcoin.png"
        },
      ],

    }
  },

}
</script>

<style lang="sass">
  @import "~bulma/sass/utilities/initial-variables";
  $bgcol: #302f33;
  $body-background: $bgcol;
  // $html-background: #3273dc
  @import "~bulma/bulma.sass";
</style>

<style>
.cfcenter{
  margin: auto;
  text-align: center;
}
.box {
  background-color: #dcd3d3;
}
.column.cfheader {
  padding: 0;
}
.tabs li.is-active a {
    border-bottom-color: #363636;
    color: #3273dc;
}

.tabs:not(:last-child) {
    margin-bottom: 0;
}

.input:focus, .input.is-focused, .input:active, .input.is-active, .textarea:focus, .textarea.is-focused, .textarea:active, .textarea.is-active {
    border-color: #3273dc;
}
/*h1, h2 {
  font-weight: normal;
  color: black;
}*/

/*ul {
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
