<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list class="py-1">
        <v-list-item class="px-2">
          <v-list-item-avatar>
            <v-img :src="require('@/static/icon.png')"></v-img>
          </v-list-item-avatar>
          <v-img max-width="100" :src="require('@/static/logo.svg')"></v-img>
        </v-list-item>
      </v-list>

      <v-divider></v-divider>
      <v-list :rounded="!miniVariant">
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          color="orange darken-2"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      fixed
      app
      flat
      style="border-bottom: 1px solid rgba(0, 0, 0, 0.12); background: white"
    >
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>

      <v-text-field
        dense
        single-line
        outlined
        flat
        clearable
        hide-details
        label="Search screen, media, playlist or schedule"
        prepend-inner-icon="mdi-magnify"
      ></v-text-field>
      <v-spacer />
      <v-btn icon>
        <v-icon>mdi-bell-outline</v-icon>
      </v-btn>
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-list-item-avatar class="mx-auto">
          <v-img src="https://cdn.vuetifyjs.com/images/lists/1.jpg"></v-img>
        </v-list-item-avatar>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list-item two-line>
        <v-list-item-avatar>
          <v-img src="https://cdn.vuetifyjs.com/images/lists/1.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Jhon Doe</v-list-item-title>
          <v-list-item-subtitle>admin</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>

      <v-list dense>
        <v-list-item v-for="item in profile" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- footer -->
    <!-- <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer> -->
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-view-dashboard-outline",
          title: "Overview",
          to: "/",
        },
        {
          icon: "mdi-monitor-screenshot",
          title: "Screen",
          to: "/screen",
        },
        {
          icon: "mdi-television-play",
          title: "Media",
          to: "/media",
        },
        {
          icon: "mdi-format-list-bulleted",
          title: "Playlist",
          to: "/playlist",
        },
        {
          icon: "mdi-calendar-check-outline",
          title: "Schedule",
          to: "/schedule",
        },
        {
          icon: "mdi-chart-bar-stacked",
          title: "Statistics",
          to: "/statistics",
        },
        {
          icon: "mdi-credit-card-outline",
          title: "Payouts",
          to: "/payouts",
        },
        {
          icon: "mdi-cog-outline",
          title: "Settings",
          to: "/settings",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js",
    };
  },
};
</script>
