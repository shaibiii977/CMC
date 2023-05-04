<template>
  <div id="app">
    <ClientStatus />
    <HDFProtectionStatus />
    <IOActivities />
    <ControlledIOActivities />
  </div>
</template>

<script>

import ClientStatus from './components/ClientStatus.vue'
import HDFProtectionStatus from './components/HDFProtectionStatus.vue'
import IOActivities from './components/IOActivities.vue'
import ControlledIOActivities from './components/ControlledIOActivities.vue'

export default {
  name: 'CMC',
  components: {
    ClientStatus,
    HDFProtectionStatus,
    ControlledIOActivities,
    IOActivities
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
