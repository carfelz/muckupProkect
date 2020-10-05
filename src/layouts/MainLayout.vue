<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
        <q-space></q-space>
        <q-space></q-space>

        <AccountMenu />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
      class="left-drawer"
    >
      <q-item>
        <img
          alt="Vpsie log"
          src="~assets/logo.png"
    >
      </q-item>
      <q-separator />

      <q-item
       style="display: flex"
      >
        <q-item-section top avatar>
          Carlos Feliz
          <q-item-section>
            <q-btn
            label="Earn credits"
            color="green"
            size="sm"
            outline
            ripple
            />
          </q-item-section>
        </q-item-section>

      </q-item>
      <q-scroll-area style="height: calc(100% - 350px); border-right: 1px solid #ddd;">
          <q-list clickable v-ripple>
            <EssentialLink
              v-for="link in essentialLinks"
              :key="link.title"
              v-bind="link"
            />
         </q-list>
      </q-scroll-area>

      <q-separator />
      <q-item>
        <q-item-section top avatar>
          Settings
        </q-item-section>
      </q-item>

      <q-scroll-area style="height: calc(100% - 350px); border-right: 1px solid #ddd;">
        <q-list clickable v-ripple>
          <EssentialLink
            v-for="link in settinglist"
            :key="link.title"
            v-bind="link"
          />
        </q-list>
      </q-scroll-area>


    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue';
import AccountMenu from 'components/AcountMenu.vue'


export default {
  name: 'MainLayout',
  components: { EssentialLink, AccountMenu },
  data () {
    return {
      leftDrawerOpen: false,
      settinglist:[
              {
                title: 'Add SSH Key',
              },
              {
                title: 'Add Custom ISO Image',
              },
              {
                title: 'Add Startup Script',
              },
              {
                title: 'Add IP to VPSiw',
              },
    ],
      essentialLinks:  [
  {
    title: 'VPSis',
    caption: 'quasar.dev',
  },
  {
    title: 'PCS',
    caption: 'github.com/quasarframework',
  },
  {
    title: 'Recovery',
    caption: 'chat.quasar.dev',
  },
  {
    title: 'Billing',
    caption: 'forum.quasar.dev',
  },
  {
    title: 'DNS',
    caption: '@quasarframework',
  },
  {
    title: 'Support',
    caption: '@QuasarFramework',
  },
  {
    title: 'Activities',
    caption: 'Community Quasar projects',
  },
  {
    title: 'FAQ',
    caption: 'Community Quasar projects',
  },
  {
    title: 'Settings',
    caption: 'Community Quasar projects',
  }
]
    }
  }
}
</script>
<style>
 .q-drawer__content{
   overflow-y: hidden;
 }
</style>
