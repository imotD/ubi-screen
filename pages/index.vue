<template>
  <div class="content">
    <v-row>
      <v-col cols="12" class="pa-0">
        <v-breadcrumbs :items="breadcrumbs" divider=">">
          <template v-slot:item="{ item }">
            <v-breadcrumbs-item :href="item.href" :disabled="item.disabled">
              <span :style="`color: ${item.color}`">
                {{ item.text }}
              </span>
            </v-breadcrumbs-item>
          </template>
        </v-breadcrumbs>
      </v-col>
      <v-col cols="12">
        <v-tabs
          class="content__border--bottom"
          v-model="tab"
          background-color="transparent"
          color="orange"
        >
          <v-tab v-for="item in items" :key="item">
            {{ item }}
          </v-tab>
        </v-tabs>

        <v-tabs-items v-model="tab">
          <v-tab-item>
            <Details />
          </v-tab-item>
          <v-tab-item>
            <Schedule />
          </v-tab-item>
        </v-tabs-items>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      tab: null,
      items: ["Detail", "Schedule"],
      text: "content",
      breadcrumbs: [
        {
          text: "Videotron",
          disabled: false,
          color: "orange",
          href: "link_1",
        },
        {
          text: "UB0022373 - Videotron 001",
          disabled: true,
          href: "link_2",
        },
      ],
    };
  },
};
</script>
