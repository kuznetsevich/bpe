<template>
  <div class=" flag_wrap" mb-5тзь>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn tile outlined color="success" v-bind="attrs" v-on="on">
          <v-icon left>mdi-flag</v-icon>
          {{ currentLang.code }}
        </v-btn>
      </template>
      <v-list>
        <v-list-item v-for="(item, index) in lang" :key="index" @click="setLanguage(item.code)">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "Language",
  data: () => ({
    tab: null,
    lang: [
      { title: 'English', code: 'en', icon: '' },
      { title: 'Russian', code: 'ru', icon: '' },
    ],
    currentLang: {
      title: '',
      code: '',
      icon: '',
    }
  }),
  mounted() {
    this.setLanguage(localStorage.lang || 'en');
  },
  computed: {
    width () {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs': return 220;
        case 'sm': return 400;
        case 'md': return 500;
        case 'lg': return 600;
        case 'xl': return 800;
      }
    },
  },
  methods: {
    setLanguage(code) {
      let langCode = 0;
      let userLang = this.lang.findIndex(l => l.code === code);
      if (userLang) {
        langCode = userLang;
      }
      this.currentLang = this.lang[langCode];
      this.$i18n.locale = this.currentLang.code;
      this.$vuetify.lang.current = this.currentLang.code;
      localStorage.lang = code;
    },
  },
}
</script>

<style scoped>

</style>