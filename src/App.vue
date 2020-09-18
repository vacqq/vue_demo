<template>
  <a-config-provider :locale="locale">
    <div id="app">
      <router-view />
    </div>
  </a-config-provider>
</template>

<script>
import { domTitle, setDocumentTitle } from '@/utils/domUtil'
import { i18nRender } from '@/locales'
import { MP } from './map'

export default {
  data () {
    return {
      ak: "SxStCg9e15wDd3a1s6ECPwA0pHHm1TlC",
    }
  },
  computed: {
    locale () {
      // 只是为了切换语言时，更新标题
      const { title } = this.$route.meta
      title && (setDocumentTitle(`${domTitle} - ${i18nRender(title)}`))

      return this.$i18n.getLocaleMessage(this.$store.getters.lang).antLocale
    }
  },
  async mounted () {
     // await MP(this.ak);
  }
}
</script>
