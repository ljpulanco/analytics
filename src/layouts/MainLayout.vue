<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white">
      <q-toolbar>
        <q-btn color="blue-grey-10"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title
        color="grey-8">
           Kollab
        </q-toolbar-title>

        <q-btn-dropdown
        class="d-shadow-none"
      color="purple"
      label="Account Settings"
    >
      <div class="row no-wrap q-pa-md">
        <div class="column">
          <div class="text-h6 q-mb-md">Settings</div>
          <q-toggle v-model="mobileData" label="Use Mobile Data" />
          <q-toggle v-model="bluetooth" label="Bluetooth" />
        </div>

        <q-separator vertical inset class="q-mx-lg" />

        <div class="column items-center">
          <q-avatar size="72px">
            <img src="https://cdn.quasar.dev/img/boy-avatar.png">
          </q-avatar>

          <div class="text-subtitle1 q-mt-md q-mb-xs">Katrina</div>

          <q-btn
            color="primary"
            label="Logout"
            push
            size="sm"
            v-close-popup
          />
        </div>
      </div>
    </q-btn-dropdown>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Follow me
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data () {
    return {
      mobileData: true,
      bluetooth: false,
      leftDrawerOpen: true,
      essentialLinks: [
        {
          title: 'Github',
          caption: 'github.com/ljpulanco',
          icon: 'code',
          link: 'https://github.com/ljpulanco'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.d-shadow-none{
  box-shadow: none;
}
</style>
