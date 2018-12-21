<template>
<div id="app">
  <v-app id="inspire">
    <v-card id="create">
      <v-container>
   <v-speed-dial
        v-model="fab"
        :direction="direction"
        :open-on-hover="hover"
        :transition="transition"
      >
        <v-btn
          slot="activator"
          v-model="fab"
          color="blue darken-2"
          dark
          fab
        >
          <v-icon>account_circle</v-icon>
          <v-icon>close</v-icon>
        </v-btn>
        <v-btn
          
          dark
          small
          color="green"
        >
          <v-icon>edit</v-icon> &nbsp;&nbsp;login
        </v-btn>
        <v-btn
          dark
          small
          color="indigo"
        >
          <v-icon>add</v-icon>
        </v-btn>
        <v-btn
          dark
          small
          color="red"
        >
          <v-icon>delete</v-icon>
        </v-btn>
      </v-speed-dial>
      </v-container>
   
    </v-card>
  </v-app>
</div>
</template>
<script>
export default{
  el: '#app',
  data: () => ({
    direction: 'bottom',
    fab: false,
    fling: false,
    hover: false,
    tabs: null,
    top: true,
    right: false,
    bottom: false,
    left: true,
    transition: 'slide-y-reverse-transition'
  }),

  computed: {
    activeFab () {
      switch (this.tabs) {
        case 'one': return { 'class': 'purple', icon: 'account_circle' }
        case 'two': return { 'class': 'red', icon: 'edit' }
        case 'three': return { 'class': 'green', icon: 'keyboard_arrow_up' }
        default: return {}
      }
    }
  },

  watch: {
    top (val) {
      this.bottom = !val
    },
    right (val) {
      this.left = !val
    },
    bottom (val) {
      this.top = !val
    },
    left (val) {
      this.right = !val
    }
  }
}
</script>
<style>
#create .v-speed-dial {
  position: absolute;
}

#create .v-btn--floating {
  position: relative;
}
</style>