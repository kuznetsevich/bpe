<template>
  <v-container class="flex-column">

<!-- IF -->
    <v-layout column>
      <v-flex d-flex xs12>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
        >
          <div class="if-notes">
            <h6 class="title">IF</h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
            </p>
          </div>

        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="7"
        >
          <v-sheet class="content-section"
           color="white"
           elevation="1"
           rounded
          >
            <v-layout class="flex-column">
              <v-select
                  :items="items"
                  label="Select parameter"
                  dense
                  outlined
              ></v-select>
              <v-spacer></v-spacer>
              <v-select
                  :items="items"
                  label="Select parameter"
                  dense
                  outlined
              ></v-select>
              <v-spacer></v-spacer>
              <v-text-field
                  label="Enter the value"
                  outlined
                  dense
              ></v-text-field>
              <v-row align="center">
                <v-col
                    cols="12"
                    sm="6"
                >
                  <v-subheader v-text="'Additional condition'"></v-subheader>
                </v-col>
                <v-col
                    cols="12"
                    sm="6"
                >
                  <v-select
                      v-model="e6"
                      :items="states"
                      :menu-props="{ maxHeight: '400' }"
                      label="Select"
                      multiple
                      persistent-hint
                  ></v-select>
                </v-col>
              </v-row>
            </v-layout>
          </v-sheet>

        </v-col>
      </v-flex>
    </v-layout>
    <v-layout column>
      <v-flex d-flex xs12>
        <v-col
            class="d-flex"
            cols="12"
            sm="4"
        >
          <div class="if-notes">
            <h6 class="title">AND</h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
            </p>
          </div>

        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="7"
        >
          <v-sheet class="content-section"
                   color="white"
                   elevation="1"
                   rounded
          >
            <v-layout class="flex-column">
              <v-select
                  :items="items"
                  label="Select parameter"
                  dense
                  outlined
              ></v-select>
              <v-spacer></v-spacer>
              <v-select
                  :items="items"
                  label="Select parameter"
                  dense
                  outlined
              ></v-select>
              <v-spacer></v-spacer>
              <v-text-field
                  label="Enter the value"
                  outlined
                  dense
              ></v-text-field>
            </v-layout>
          </v-sheet>

        </v-col>
      </v-flex>
    </v-layout>
    <v-layout column>
      <v-flex d-flex xs12>
        <v-col
            class="d-flex"
            cols="12"
            sm="4"
        >
          <div class="if-notes">
            <h6 class="title">THEN</h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
            </p>
          </div>

        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="7"
        >
          <v-sheet class="content-section"
                   color="white"
                   elevation="1"
                   rounded
          >
            <v-layout class="flex-column">
              <v-row class="row-style-custom">
                <v-col
                    cols="12"
                    sm="6"
                >
                  <v-subheader v-text="'Select Character Count'"></v-subheader>
                </v-col>
                <v-col
                    cols="12"
                    sm="6"
                >
                  <v-select
                      :items="items"
                      label="Select"
                      dense
                      outlined
                  ></v-select>
                </v-col>
              </v-row>
              <v-row class="row-style-custom">
                <v-col
                    cols="12"
                    sm="6"
                >
                  <v-subheader v-text="'Select Seperator Style'"></v-subheader>
                </v-col>
                <v-col
                    cols="12"
                    sm="6"
                >
                  <v-select
                      :items="items"
                      label="Select"
                      dense
                      outlined
                  ></v-select>
                </v-col>
              </v-row>
              <v-row class="row-style-custom">
                <v-col
                    cols="12"
                    sm="4"
                >
                  <v-subheader v-text="'Take option 1'"></v-subheader>
                </v-col>
                <v-col
                    cols="12"
                    sm="8"
                >
                  <v-select
                      :items="items"
                      label="Select parameter"
                      dense
                      outlined
                  ></v-select>
                </v-col>
              </v-row>
              <v-row class="row-style-custom" >
                <v-col
                    cols="12"
                    sm="4"
                >
                  <v-subheader v-text="'Take option 2'"></v-subheader>
                </v-col>
                <v-col
                    cols="12"
                    sm="8"
                >
                  <v-select
                      :items="items"
                      label="Select parameter"
                      dense
                      outlined
                  ></v-select>
                </v-col>
              </v-row>
              <v-row class="row-style-custom">
                <v-col
                    cols="12"
                    sm="4"
                >
                  <v-subheader v-text="'Take option 3'"></v-subheader>
                </v-col>
                <v-col
                    cols="12"
                    sm="8"
                >
                  <v-select
                      :items="items"
                      label="Select parameter"
                      dense
                      outlined
                  ></v-select>
                </v-col>
              </v-row>
            </v-layout>
          </v-sheet>

        </v-col>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    items: [
      { title: 'And' },
      { title: 'Or' },
      { title: 'Copy' },
    ],

  }),
}




</script>



<style style scoped lang="scss">

.container{
  padding: 4px;
}
.if-notes {
  .title {
    margin-bottom: 10px;
    .if-description {
      margin-top: 10px;
    }
  }
}
.content-section{
  width: 100%;
  padding: 20px;
  .sheet-custom {
    padding: 18px;
    margin-bottom: 20px;
    .divider {
      margin: 10px 0;
    }
  }
}

.row-style-custom {
  max-height: 65px;
}

</style>