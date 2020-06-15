<template>
  <div class="App-Bar">
    <v-app-bar
      app
      color="grey lighten-5"
    >

      <v-flex class="">
        <v-layout align-center justify-space-between>
          <v-btn icon @click="showLeftMenu()" color="indigo">
            <v-icon>mdi-menu</v-icon>
          </v-btn>
          <v-icon class="mr-3">mdi-calendar</v-icon>
          <div>Календарь</div>
          <v-btn class="ml-3" small outlined color="indigo">
            <span class="text-capitalize">Сегодня</span>
          </v-btn>
          <v-btn icon small color="indigo">
            <v-icon>mdi-chevron-left</v-icon>
          </v-btn>
          <v-btn icon small color="indigo">
            <v-icon>mdi-chevron-right</v-icon>
          </v-btn>
          <div class="headline">Май-Июнь 2020</div>
          <v-spacer></v-spacer>
          <v-btn icon color="indigo">
            <v-icon>mdi-magnify</v-icon>
          </v-btn>
          <v-btn icon color="indigo">
            <v-icon>mdi-help</v-icon>
          </v-btn>
          <v-btn icon color="indigo">
            <v-icon>mdi-cog</v-icon>
          </v-btn>
          <v-col cols="1" class="pa-0">
          <v-select hide-details label="Неделя" color="indigo"></v-select>
          </v-col>
          <v-btn icon color="indigo">
            <v-icon>mdi-apps</v-icon>
          </v-btn>
        </v-layout>
      </v-flex>
    </v-app-bar>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component({
  name: 'Header'
})
export default class Header extends Vue {
  // @Prop({ default: null }) public cardVue!: any;
  public leftMenu: boolean = true;
  public showLeftMenu(){
    this.leftMenu=!this.leftMenu
    console.log('App-Bar')
    this.$emit('LeftMenu',this.leftMenu)
  }
}
</script>
