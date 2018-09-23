<template>
  <v-app dark>
    <v-content>
      <v-navigation-drawer v-model="drawer" app>
        <v-toolbar flat class="transparent">
          <v-list class="pa-0">
            <v-list-tile avatar>
              <v-list-tile-avatar>
              </v-list-tile-avatar>

              <v-list-tile-content>
                <v-list-tile-title>Menu</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list>
        </v-toolbar>
        <v-list class="pt-0" dense>
          <v-divider></v-divider>

          <v-list-tile v-for="item in items" :key="item.title">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>

      <v-toolbar app>
        <v-btn flat icon @click="onMenuToggle">
          <v-icon>menu</v-icon>
        </v-btn>
      </v-toolbar>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-content>
    <v-footer app></v-footer>
  </v-app>
</template>
<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import { Prop } from 'vue-property-decorator';

@Component({})
export default class App extends Vue {
  private drawer: boolean | null = null;

  private items = [
    { title: 'Home', icon: 'dashboard' },
    { title: 'About', icon: 'question_answer' },
  ];

  private onMenuToggle() {
    this.drawer = !this.drawer;
  }
}
</script>

<style lang="scss">
</style>
