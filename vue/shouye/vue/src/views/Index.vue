<template>
  <div>
    <Header></Header>
    <MainBanner></MainBanner>
    <Main></Main>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from '@/components/Header.vue'
import MainBanner from '@/components/MainBanner.vue'
import Footer from '@/components/Footer.vue'
import Main from '@/components/Main.vue'

export default {
  name: 'Index',
  components: {
    Header,
    MainBanner,
    Main,
    Footer
  }
}
</script>
