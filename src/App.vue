<template>
  <div id="app">
    <hello></hello>
  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  components: {
    Hello
  }
}
</script>

<style lang="sass">
  @import "~bulma/sass/utilities/initial-variables";
  $body-background: #3273dc;
  // $html-background: #3273dc
  @import "~bulma/bulma.sass";
</style>
