<template>
  <div>
    <div>
      <router-link to="/">Home</router-link> |
      <router-link :to="{ name: 'About' }">About</router-link> |
      <router-link :to="{ name: 'Profile', params: {id: '1234'} }">Profile</router-link> | 
      <router-link :to="{ name: 'RiskMatrix' }">Risk Matrix</router-link> |
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style>

</style>