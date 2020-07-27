<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <contact/>
  </div>
</template>

<script>
// @ is an alias to /src
import contact from '@/components/contact.vue'

export default {
  name: 'Contact',
  components: {
    contact
  }
}
</script>
