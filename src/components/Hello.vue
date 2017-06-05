<template>
  <div class="hello">
    
    <section class="section">
      <div class="hero-head">
        <div class="container">

          <div class="box">

            <div class="notification" id="output-main" style="background-color: #dcdcdc;">
              <h1 class="title is-1 has-text-centered" >XEM to BTC</h1>
            </div>

            <div class="columns" id="input-main">
              <div class="column is-4">
                <input class="input is-large" id="input-amount" type="number" min="0" placeholder="Amount in XEM">
              </div>
              <div class="column">
                <a class="button is-large is-info" onclick="getRate()" >Submit</a>
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
      msg: 'Welcome to Your Vue.js App'
    }
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
