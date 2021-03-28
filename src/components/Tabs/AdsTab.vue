<template>
  <v-container>
    <v-row d-flex justify-space-between>
      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="260"
          max-height="522"
      >
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-img
            height="240"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>Bulk Price Editor</v-card-title>

        <v-card-text>
          <v-row
              align="center"
              class="mx-0"
          >
            <v-rating
                :value="4.8"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
            ></v-rating>

            <div class="grey--text ml-4">
              4.8 (413)
            </div>
          </v-row>

          <div class="my-4 subtitle-1">
            $ 4.99 / month
          </div>

          <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn block
                 color="primary"
                 elevation="2"
                 @click="get_it"
          >
            Get it
          </v-btn>
        </v-card-actions>
      </v-card>
      <v-spacer></v-spacer>
      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="260"
          max-height="522"
      >
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-img
            height="240"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>Bulk Title & Tags Editor</v-card-title>

        <v-card-text>
          <v-row
              align="center"
              class="mx-0"
          >
            <v-rating
                :value="4.5"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
            ></v-rating>

            <div class="grey--text ml-4">
              4.5 (413)
            </div>
          </v-row>

          <div class="my-4 subtitle-1">
            $ 4.99 / month
          </div>

          <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn block
                 color="primary"
                 elevation="2"
                 @click="get_it"
          >
            Get it
          </v-btn>
        </v-card-actions>
      </v-card>
      <v-spacer></v-spacer>
      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="260"
          max-height="522"
      >
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-img
            height="240"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>SEO Assistant</v-card-title>

        <v-card-text>
          <v-row
              align="center"
              class="mx-0"
          >
            <v-rating
                :value="4.5"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
            ></v-rating>

            <div class="grey--text ml-4">
              4.5 (413)
            </div>
          </v-row>

          <div class="my-4 subtitle-1">
            $ 4.99 / month
          </div>

          <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn block
              color="primary"
              elevation="2"
              @click="get_it"
          >
            Get it
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-row>
    <v-row d-flex justify-space-between>
      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="260"
          max-height="522"
      >
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-img
            height="240"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>Bulk Price Editor</v-card-title>

        <v-card-text>
          <v-row
              align="center"
              class="mx-0"
          >
            <v-rating
                :value="4.8"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
            ></v-rating>

            <div class="grey--text ml-4">
              4.8 (413)
            </div>
          </v-row>

          <div class="my-4 subtitle-1">
            $ 4.99 / month
          </div>

          <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn block
                 color="primary"
                 elevation="2"
                 @click="get_it"
          >
            Get it
          </v-btn>
        </v-card-actions>
      </v-card>
      <v-spacer></v-spacer>
      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="260"
          max-height="522"
      >
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-img
            height="240"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>Bulk Title & Tags Editor</v-card-title>

        <v-card-text>
          <v-row
              align="center"
              class="mx-0"
          >
            <v-rating
                :value="4.5"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
            ></v-rating>

            <div class="grey--text ml-4">
              4.5 (413)
            </div>
          </v-row>

          <div class="my-4 subtitle-1">
            $ 4.99 / month
          </div>

          <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn block
                 color="primary"
                 elevation="2"
                 @click="get_it"
          >
            Get it
          </v-btn>
        </v-card-actions>
      </v-card>
      <v-spacer></v-spacer>
      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="260"
          max-height="522"
      >
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-img
            height="240"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>SEO Assistant</v-card-title>

        <v-card-text>
          <v-row
              align="center"
              class="mx-0"
          >
            <v-rating
                :value="4.5"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
            ></v-rating>

            <div class="grey--text ml-4">
              4.5 (413)
            </div>
          </v-row>

          <div class="my-4 subtitle-1">
            $ 4.99 / month
          </div>

          <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn block
                 color="primary"
                 elevation="2"
                 @click="get_it"
          >
            Get it
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {
    name: 'AdsTab'
};
</script>

<style scoped>

</style>