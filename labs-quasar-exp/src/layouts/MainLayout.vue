<template>
  <q-layout view="lHr lpR lFr">
    <q-header bordered class="header">
      <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
      <q-toolbar>
        <q-toolbar-title class="text-weight-bold">
          {{ $route.name }}
        </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered class="" :width="250">
      <div class="sidebar">
        <q-list>
          <q-item to="/" clickable v-ripple>
            <q-item-section avatar>
              <q-icon color="black" name="home" />
            </q-item-section>
            <q-item-section class="text-h6 text-weight-bold">Home </q-item-section>
          </q-item>
          <q-item to="/about" clickable v-ripple>
            <q-item-section avatar>
              <q-icon color="black" name="person" />
            </q-item-section>
            <q-item-section class="text-h6 text-weight-bold">About</q-item-section>
          </q-item>
        </q-list>
      </div>
    </q-drawer>
    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <q-input color="black" outlined dense rounded v-model="text" placeholder="Search Topic..." class="q-ma-md">
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
      </q-input>
      <q-list padding separator>
        <q-item class="spacer">
          <q-item-section>
            <q-item-label class="q-mb-sm"> <Badge label="Politics" /> </q-item-label>
              <q-item-label class="text-weight-bold">Donald Trump is back</q-item-label>
            <q-item-label caption lines="4" class="q-pt-xs">
              The former president of the United States of American, Donald J. Trump is now back at the White House.
              His first action as the president was to end the war in Ukraine and find a bilateral relationship with Russia, the first in American History.
            </q-item-label>
          </q-item-section>
          <q-item-section side top>
            <q-item-label class="text-weight-medium" caption>75 min ago</q-item-label>
          </q-item-section>
        </q-item>
        <q-item class="spacer">
          <q-item-section>
            <q-item-label class="q-mb-sm"> <Badge label="France" /> </q-item-label>
            <q-item-label class="text-weight-bold">Tibo Inshape N°1 in France </q-item-label>
            <q-item-label caption lines="3" class="q-pt-xs">
              French Fitness influencer Tibo Inshape is now the first Youtube channel with the most amount of subscribers in France.
            </q-item-label>
          </q-item-section>
          <q-item-section side top>
            <q-item-label class="text-weight-medium" caption>75 min ago</q-item-label>
          </q-item-section>
        </q-item>
        <q-item class="spacer">
          <q-item-section>
            <q-item-label class="q-mb-sm"> <Badge label="Tech" /> </q-item-label>
            <q-item-label class="text-weight-bold">Microsoft is starting to investing in ARM Chips</q-item-label>
            <q-item-label caption lines="3" class="q-pt-xs">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Facer facilisi
              erat cillum anim luptatum voluptate elitr clita invidunt nobis nihil augue.
            </q-item-label>
          </q-item-section>
          <q-item-section side top>
            <q-item-label class="text-weight-medium" caption>75 min ago</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<style>
.header {
  display: flex;
  padding-left: 2rem;
  padding-right: 2rem;
  align-items: center;
  height: 4rem;
  color: #000000;
  background-color: #ffffff;
}

.sidebar {
  padding-top: 2rem;
}

.spacer {
  padding-top: 1rem;
  padding-bottom: 1rem;
  padding-right: 1.25rem;
  padding-left: 1.25rem;
}
</style>

<script>
import { ref } from 'vue'
import Badge from 'components/ui/Badge.vue'

export default {
  components: { Badge },
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer () {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
}
</script>
