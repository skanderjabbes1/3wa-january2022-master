<template>
  <NavBar></NavBar>
  <router-view class="container py-3"/>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
export default {
  components: {
    NavBar,
  },
}
</script>