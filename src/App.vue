<template>
  <v-app>
  <my-header @LeftMenu="showLeftMenu"></my-header>
    <v-content class="d-flex">

<!--      <left-menu></left-menu>-->
      <v-layout>
      <left-menu v-show="leftMenu" class="pr-1"></left-menu>
      <quest-container></quest-container>
      </v-layout>
<!--      <div></div>-->
<!--      <HelloWorld/>-->
    </v-content>
  </v-app>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
// import Header from './components/Header/App-Bar/App-Bar.vue'
// import QuestContainer from "@/components/QuestContainer/QuestContainer.vue"

@Component({
  name: 'root-app',
  components: {
    'my-header':()=>import('@/components/Header/App-Bar/App-Bar.vue'),
    // 'my-header': Header,
    'quest-container':()=>import('@/components/QuestContainer/QuestContainer.vue'),
    'left-menu':()=>import('@/components/LeftMenu/LeftMenu.vue')
    // 'quest-container': QuestContainer,
  }
})
export default class RootVue extends Vue {
  @Prop() private msg!: string;
  public leftMenu: boolean = true
  public showLeftMenu(val:boolean){
    console.log('fasdlk',val)
    this.leftMenu=val
  }
}
</script>
