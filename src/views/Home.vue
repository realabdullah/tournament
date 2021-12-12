<template>
  <div class="home">
    <Navbar />
    <content />
  </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Content from '../components/Content'

export default {
  components: {
    Navbar,
    Content
  }
}

</script>
