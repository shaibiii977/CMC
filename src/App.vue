<template>
  <div id="app">
    <ClientStatus />
    <HDFProtectionStatus />
    <IOActivities />
    <ControlledIOActivities />
    <PacketActivity />
  </div>
</template>

<script>

import ClientStatus from './components/ClientStatus.vue'
import HDFProtectionStatus from './components/HDFProtectionStatus.vue'
import IOActivities from './components/IOActivities.vue'
import ControlledIOActivities from './components/ControlledIOActivities.vue'
import PacketActivity from './components/PacketActivity.vue'

export default {
  name: 'CMC',
  components: {
    ClientStatus,
    HDFProtectionStatus,
    PacketActivity,
    ControlledIOActivities,
    IOActivities,
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
