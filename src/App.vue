<!-- ---- SCRIPT ---- -->
<script>

// ---- IMPORTS ----
import Contador from './views/contador.vue'
import Change from './views/change.vue'
import Selector from './views/selector.vue'
import Year from './views/year.vue'
import GeratorColor from './views/geratorColor.vue'
import CounterInput from './views/counterInput.vue'
import Celsius from './views/celsius.vue'

// ---- COMPONENTS ----
export default {
  components: {
    Contador,
    Change,
    Selector,
    Year,
    CounterInput,
    Celsius,
    GeratorColor
  }
}
</script>
<!-- ---- SCRIPT ---- -->

<!-- ---- TEMPLATE ---- -->
<template>
  <Contador />
  <Change />
  <Selector />
  <Year />
  <CounterInput />
  <Celsius />
  <GeratorColor />
</template>
<!-- ---- TEMPLATE ---- -->