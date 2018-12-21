<template>
  <div id="app">
    <v-app>
    <!-- <v-navigation-drawer
      fixed
      clipped
      class="grey lighten-4"
      app
      v-model="drawer"
    >
      <v-list
        dense
        class="grey lighten-4"
      >
        <template v-for="(item, i) in items">
          <v-layout
            row
            v-if="item.heading"
            align-center
            :key="i"
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
            <v-flex xs6 class="text-xs-right">
              <v-btn small flat>edit</v-btn>
            </v-flex>
          </v-layout>
          <v-divider
            dark
            v-else-if="item.divider"
            class="my-3"
            :key="i"
          ></v-divider>
          <v-list-tile
            :key="i"
            v-else
            @click=""
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="grey--text">
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer> -->

      <v-toolbar dark color="elevation-0" app fixed clipped-left>
        <v-toolbar-side-icon @click.native="drawer = !drawer"></v-toolbar-side-icon>

        <!-- <v-toolbar-side-icon><v-icon>face</v-icon></v-toolbar-side-icon> -->
        <v-toolbar-title class="headline text-uppercase">
          <span class="font-weight-BOLD" STYLE="font-family: 'Patua One', cursive;">PASSION FASHION</span>
        </v-toolbar-title>
        <v-text-field clearable style="padding-left:3%;margin-top:5px;width:30%" append-icon="search" class="mx-12"
          flat label="Search"></v-text-field>
        <v-spacer></v-spacer>

        <!-- prepend-inner-icon="search" -->
        <v-toolbar-items>
          <v-btn flat>MAGAZINE</v-btn>
          <v-btn flat>SNAP</v-btn>
          <v-btn flat>COMMUNITY</v-btn>
          <v-btn flat>STORE</v-btn>
          <v-divider></v-divider>
          <v-menu bottom offset-y>
            <v-btn slot="activator" v-model="fab" medium dark icon fab>
              <v-icon>account_circle</v-icon>
            </v-btn>

            <v-list>
              <v-list-tile v-for="(item, i) in items1" :key="i" @click="">
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile>
            </v-list>
          </v-menu>
        </v-toolbar-items>

      </v-toolbar>

      <v-content fluid fill-height >
        <HelloWorld />
      </v-content>
    </v-app>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
    data: () => ({
      items1: [
        { title: '마이페이지' },
        { title: '로그아웃' }
        // { title: 'Click Me' },
        // { title: 'Click Me 2' }
      ],
       drawer: null,
      items: [
        { icon: 'lightbulb_outline', text: 'Notes' },
        { icon: 'touch_app', text: 'Reminders' },
        { divider: true },
        { heading: 'Labels' },
        { icon: 'add', text: 'Create new label' },
        { divider: true },
        { icon: 'archive', text: 'Archive' },
        { icon: 'delete', text: 'Trash' },
        { divider: true },
        { icon: 'settings', text: 'Settings' },
        { icon: 'chat_bubble', text: 'Trash' },
        { icon: 'help', text: 'Help' },
        { icon: 'phonelink', text: 'App downloads' },
        { icon: 'keyboard', text: 'Keyboard shortcuts' }
      ]
    })
}
</script>
<style>
@import url('https://fonts.googleapis.com/css?family=Francois+One|Noto+Sans+KR|Oswald|Patua+One');
#keep main .container {
    /* height: 660px; */
  }

  .navigation-drawer__border {
    /* display: none; */
  }

  .text {
    /* font-weight: 400; */
  }
/* #toolbar{
/* font-family: 'Patua One', cursive;

} */
#app {
  font-family: 'Noto Sans KR', sans-serif;

}
</style>