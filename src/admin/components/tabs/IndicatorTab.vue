<template>
    <div class="tab-container">
        <h2>Indicator Tab</h2>
        <p>The value of the dollar in Chile is consulted through a rest api: {{ info }}</p>
    </div>
</template>

<script>
import Axios from 'axios'
export default {
    name: 'IndicatorTab',

    data () {
    return {
      info: null
    }
  },
  mounted () {
    Axios
      .get('https://mindicador.cl/api')
      .then(response => (this.info = response.data.dolar.valor))
  }
}
</script>

<style>

</style>