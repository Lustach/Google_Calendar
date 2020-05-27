<template>
  <div class="CalendarHeader">
    <!--        <v-flex>-->
    <v-container class="pa-0">
      <v-flex>
        <v-layout>
          <v-row class="d-flex justify-center" v-for="cols in 7">
            <v-col class="header-cell text-center">
              {{cols}}/weekkday
<!--              {{cols}}-->
            </v-col>
          </v-row>
        </v-layout>
      </v-flex>
    </v-container>
    <!--        </v-flex>-->
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class CalendarHeader extends Vue {
  @Prop() private msg!: string
}
</script>
<style lang="scss">
.header{
    &-cell{
        /*width:150px;*/
    }
}
</style>