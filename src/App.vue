<template>
  <div id="app">
    <header>
      <HeaderComponent />
    </header>

    <main>
      <CardContainer />
    </main>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import CardContainer from './components/CardContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    CardContainer
  }
}
</script>

<style lang="scss">
@import './style/common'

</style>
