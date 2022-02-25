<template>
  <div>
    <v-breadcrumbs :items="breadcrumbs" divider=">"></v-breadcrumbs>
    <v-row>
      <v-col>
        <v-tabs v-model="tab" background-color="transparent" color="orange">
          <v-tab v-for="item in items" :key="item">
            {{ item }}
          </v-tab>
        </v-tabs>

        <v-tabs-items v-model="tab">
          <v-tab-item v-for="item in items" :key="item">
            <v-card color="basil" flat>
              <v-card-text>{{ text }}</v-card-text>
            </v-card>
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
