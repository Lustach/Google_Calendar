<template>
  <v-flex class="LeftMenu pl-2 pt-5" xs2>
    <!--    <pre v-text="$attrs"/>-->
<!--    <v-btn large rounded>-->
<!--      <v-icon>mdi-plus</v-icon>-->
<!--      <span class="text-capitalize">Создать</span>-->
<!--    </v-btn>-->
    <create-dialog v-if="dialog"></create-dialog>
    <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Culpa, quaerat tempora. Earum ex fugiat iure quaerat
      tempora? Assumenda aut cum fugit ipsa nesciunt possimus quisquam tempora, ullam veritatis vitae voluptates.
    </div>
    <div>Dolorum eius illo iusto, qui saepe ullam velit. Atque consectetur consequuntur, distinctio fuga officiis rem
      repellendus vel. Dolor enim, expedita impedit ipsa nisi officiis quas quia quis, quos reiciendis soluta?
    </div>

  </v-flex>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component({
  name: 'left-menu',
  components: {
    'create-dialog': () => import('@/components/CreateDialog/CreateDialog.vue'),
    'calendar-header': () => import('@/components/CalendarHeader/CalendarHeader.vue')
  }
})
export default class LeftMenu extends Vue {
  dialog: boolean = true;
  @Prop() private msg!: string;
}
</script>

