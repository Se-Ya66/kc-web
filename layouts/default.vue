<template>
  <v-app dark>
    <Header />
    <nuxt />
    <Footer />
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import loadingMixin from '@/components/loadingMixin';

export default {
  mixins: [loadingMixin],
  components: {
    Header,
    Footer
  }
}
</script>
