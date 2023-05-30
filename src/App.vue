<template>
  <Nav />
  <Main />
  <Notice />
  <Content />
  <Footer />
</template>

<script>
import Nav from './components/Nav.vue';
import Main from './components/Main.vue';
import Notice from './components/Notice.vue'
import Content from './components/Content.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Main,
    Notice,
    Content,
    Footer
  }
}
</script>

<style>

</style>
