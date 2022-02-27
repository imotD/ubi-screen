<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-icon small color="green lighten-1">
          mdi-checkbox-blank-circle
        </v-icon>
        <span class="text-caption font-weight-bold">Turned On</span>
      </v-col>
      <v-col cols="6">
        <v-row>
          <v-col cols="12">
            <v-img
              class="rounded"
              src="https://picsum.photos/510/300?random"
              aspect-ratio="1.7"
            ></v-img>
          </v-col>
        </v-row>
        <v-row>
          <v-col v-for="i in 4" cols="3" :key="i" class="py-0">
            <v-img
              class="rounded"
              src="https://picsum.photos/510/300?random"
              aspect-ratio="1.7"
            ></v-img>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="6">
        <v-row no-gutters>
          <v-col>
            <v-col>
              <p>
                <span class="font-weight-bold"> Videotron 001</span> <br />
                <span class="text--secondary">ID: UB0012341</span>
              </p>
            </v-col>
            <v-col class="rounded grey lighten-4">
              <v-row no-gutters>
                <v-col cols="1">
                  <v-icon> mdi-map-marker </v-icon>
                </v-col>
                <v-col>
                  <p class="caption">
                    Mall Taman Pelem lt 8, Cengkareng, Jakarta Barat. DKI
                    Jakarta
                  </p>
                  <v-btn class="pl-0" small text color="orange">
                    See on maps <v-icon right> mdi-chevron-right </v-icon>
                  </v-btn>
                </v-col>
              </v-row>
            </v-col>
          </v-col>
          <v-col cols="3" class="text-right">
            <v-btn outlined color="orange">
              <v-icon left> mdi-square-edit-outline </v-icon> Edit
            </v-btn>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="6">
            <span class="text-body-2 font-weight-bold">Type</span> <br />
            <span class="text--secondary"> Videotron </span>
          </v-col>
          <v-col cols="6">
            <span class="text-body-2 font-weight-bold">Resolution</span> <br />
            <span class="text--secondary"> Widescreen 16:9 (1920x1080) </span>
          </v-col>
          <v-col cols="6">
            <span class="text-body-2 font-weight-bold">Size</span> <br />
            <span class="text--secondary"> 40 inch </span>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Details",
};
</script>

<style lang="scss" scoped>
</style>