<template>
  <v-flex class="CreateDialog">
    <v-row class="ml-0">
      <v-dialog max-width="600px" persistent v-model="dialog">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="primary" large outlined rounded v-bind="attrs" v-on="on">
            <v-icon>mdi-plus</v-icon>
            <span class="text-capitalize">Создать</span>
          </v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="headline">User Profile</span>
            <v-spacer></v-spacer>
            <v-btn @click="dialog = false" class="text-capitalize" color="blue darken-1" icon text>
              <v-icon>mdi-close</v-icon>
            </v-btn>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col class="pa-0" cols="12" md="12">
                  <v-text-field class="font-weight-bold " label="Добавьте название" required></v-text-field>
                </v-col>
                <v-tabs
                  background-color="primary"
                  dark
                  v-model="tab"
                >
                  <v-tab><span class="text-capitalize">Мероприятие</span></v-tab>
                  <v-tab><span class="text-capitalize">Напоминание</span></v-tab>
                  <v-tab><span class="text-capitalize">Задача</span></v-tab>
                </v-tabs>
                <v-tabs-items v-model="tab">
                  <v-tab-item>
                    <v-row>
                      <v-col cols="12" md="3" sm="6">
                        <v-text-field label="n июня 2020"></v-text-field>
                      </v-col>
                      <v-col cols="12" md="2" sm="6">
                        <v-text-field label="2:30 Pm"></v-text-field>
                      </v-col>
                      <v-col cols="12" md="2" sm="6">
                        <v-text-field label="3:30 Pm"></v-text-field>
                      </v-col>
                      <v-col cols="12" md="3" sm="6">
                        <v-text-field label="n июня 2020"></v-text-field>
                      </v-col>
                    </v-row>
                  </v-tab-item>
                </v-tabs-items>

                <!--                <v-col cols="12" md="4" sm="6">-->
                <!--                  <v-text-field label="Legal first name*" required></v-text-field>-->
                <!--                </v-col>-->
                <!--                <v-col cols="12" md="4" sm="6">-->
                <!--                  <v-text-field hint="example of helper text only on focus" label="Legal middle name"></v-text-field>-->
                <!--                </v-col>-->
                <!--                <v-col cols="12" md="4" sm="6">-->
                <!--                  <v-text-field-->
                <!--                    hint="example of persistent helper text"-->
                <!--                    label="Legal last name*"-->
                <!--                    persistent-hint-->
                <!--                    required-->
                <!--                  ></v-text-field>-->
                <!--                </v-col>-->
                <v-col cols="12">
                  <v-text-field label="Email*" required></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-text-field label="Password*" required type="password"></v-text-field>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-select
                    :items="['0-17', '18-29', '30-54', '54+']"
                    label="Age*"
                    required
                  ></v-select>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-autocomplete
                    :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                    label="Interests"
                    multiple
                  ></v-autocomplete>
                </v-col>
              </v-row>
            </v-container>
            <small>*indicates required field</small>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn @click="dialog = false" class="text-capitalize" color="blue darken-1" text>Сохранить</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
  </v-flex>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  name: 'CreateDialog',
})
export default class CreateDialog extends Vue {
  dialog: boolean = false;
  tab = null;
}
</script>
