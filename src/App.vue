<template>
  <router-view />
</template>
<script>
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';

export default defineComponent({
  name: 'App',

  setup() {
    const { locale } = useI18n({ useScope: 'global' });
    return {
      locale
    }
  },
  mounted() {
    if (this.$q.localStorage.has('locale')) {
      this.locale = this.$q.localStorage.getItem('locale');
    } else {
      this.locale = 'en-US'
    }
  }
})
</script>
<style>
body{
  background: #26bffc;
}
</style>
