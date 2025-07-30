
<template>
  <div>
    <Header/>
    <h2>Trang Home</h2>
    <p>Nội dung chính của trang Home ở đây.</p>
  </div>
</template>

<script>
import Header from '@/components/user/Header.vue'

export default {
  name: 'Home',
  components: {
    Header
  }
}
</script>