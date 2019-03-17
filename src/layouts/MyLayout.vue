<template>
  <q-layout view="hHh LpR lFf">
    <q-header elevated class="glossy">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <q-space/>
        <q-btn-toggle 
          flat
          color="white"
          toggle-color="yellow"
          v-model='locale'
          @input="setLocale"
          :options="[{ label: 'Ar', value: 'ar'},
          { label: 'En', value: 'en-us'},
          { label: 'Fr', value: 'fr'}]"/>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      content-class="bg-grey-2"
    >
      <q-list>
        <q-item clickable tag="a" to="/products">
          <q-item-section avatar>
            <q-icon name="school" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ $t("mainMenu.products") }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'

export default {
  name: 'MyLayout',
  data () {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop,
      locale: this.$q.lang.isoName
    }
  },
  methods: {
    openURL,

    setLocale (locale) {
      import(`quasar/lang/${locale}`).then(({ default: messages }) => {
        this.$q.lang.set(messages)
      })
      import(`src/i18n/${locale}`).then(({ default: messages}) => {
        this.$i18n.locale = locale
        this.$i18n.setLocaleMessage(locale, messages)
      })

    }
  }
}
</script>

<style>
</style>
