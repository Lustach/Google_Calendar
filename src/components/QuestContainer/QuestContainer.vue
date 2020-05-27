<template>
  <!--  <div class="QuestContainer mt-5 xs8">-->

  <!--    <v-flex>-->
  <!--      <v-flex class="d-flex justify-end">fsdfl</v-flex>-->
  <!--      <v-layout>-->
  <!--        <left-menu class="d-inline ml-1" md4></left-menu>-->
  <!--        <v-flex v-for="cols in 7" md8>-->
  <!--          <v-col-->
  <!--            class="grey lighten-5 pa-0 ma-0"-->
  <!--          >-->
  <!--            <v-flex-->
  <!--              :key="rows"-->
  <!--              class="calendar-cell d-flex align-center justify-center"-->
  <!--              outlined-->
  <!--              tile-->
  <!--              v-for="rows in 25"-->
  <!--            >-->
  <!--              {{rows}}-->
  <!--              Column-->
  <!--            </v-flex>-->
  <!--          </v-col>-->
  <!--        </v-flex>-->
  <!--      </v-layout>-->
  <!--    </v-flex>-->

  <v-container class="ma-0">
    <v-flex>
      <!--      <v-layout></v-layout>-->
      <v-layout>
<!--        <left-menu></left-menu>-->
        <v-flex>
          <calendar-header></calendar-header>
          <v-layout>
<!--            <v-row class="d-block" no-gutters>-->
<!--              <v-col class="" style="height:50px;display:flex;align-items: flex-end;justify-content: flex-end;" v-for="time in 25">{{time}}-->
<!--              </v-col>-->
<!--            </v-row>-->
            <v-row class="d-flex justify-center" v-for="cols in 7">
              <v-col class="pt-0">
                <v-flex
                  :key="rows"
                  class="calendar-cell d-flex align-center justify-center"
                  outlined
                  tile
                  v-for="rows in 25"
                >
                  {{rows}}
                  Column
                </v-flex>
              </v-col>
            </v-row>
          </v-layout>
          <!--      <v-flex md8 v-for="cols in 7">-->
          <!--        <v-col-->
          <!--          class="grey lighten-5 pa-0 ma-0"-->
          <!--        >-->
          <!--          <v-flex-->
          <!--            :key="rows"-->
          <!--            class="calendar-cell d-flex align-center justify-center"-->
          <!--            outlined-->
          <!--            tile-->
          <!--            v-for="rows in 25"-->
          <!--          >-->
          <!--            {{rows}}-->
          <!--            Column-->
          <!--          </v-flex>-->
          <!--        </v-col>-->
          <!--      </v-flex>-->
        </v-flex>
      </v-layout>
    </v-flex>
  </v-container>

  <!--  </div>-->
  <!--      Вместо таблицы получилось дерево:)-->
  <!--      <v-col v-for="rows in 25">-->
  <!--        {{rows}}-->
  <!--        <v-col v-for="cols in 7">-->
  <!--  {{cols}}-->
  <!--        </v-col>-->
  <!--      </v-col>-->
  <!--        <v-col cols="12">-->
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({
  name: 'quest-container',
  components: {
    'left-menu': () => import('@/components/LeftMenu/LeftMenu.vue'),
    'calendar-header': () => import('@/components/CalendarHeader/CalendarHeader.vue')
  }
})
export default class QuestContainer extends Vue {
  @Prop() private msg!: string

}
</script>
<style lang="scss">
.QuestContainer {
  height: calc(90vh);
  overflow-y: auto;
  overflow-x: hidden;
}

/*style="max-width:250px;min-width:90px;height:50px;"*/
.calendar-cell {
  border: 1px solid #DADCE0;
  height: 50px;
  /*display:flex;*/
}

.rows_time {
  /*width: 40px;*/
  margin-right: 5px;
  font-size: 12px;
  /*display:flex;*/
  /*justify-content: center;*/
  /*align-content: center;*/
}
</style>