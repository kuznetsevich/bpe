<template>
  <v-container>
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
            <v-layout>
              <v-select
                  :items="items"
                  label="Select parameter"
                  dense
                  outlined
              ></v-select>
            </v-layout>
          </v-sheet>

        </v-col>
      </v-flex>
    </v-layout>
  <!--  <v-sheet class="sheet-custom"
        color="white"
        elevation="1"
        rounde
    >
      <v-list-item-title class="text-lg-h5">
      Set the rule for generator
        <v-divider class="divider"></v-divider>
      </v-list-item-title>
      <v-card class="card-custom d-flex"
        flat>
        <v-col
            class="d-flex first-col-color"
            cols="12"
            sm="1"
        >
          <v-card-text class="text-lg-h6">
            If
          </v-card-text>
        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="3"
        >
          <v-select
              :items="items"
              dense
              outlined
          ></v-select>
        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="3"
        >
          <v-select
              :items="items"
              dense
              outlined
          ></v-select>
        </v-col>
        <v-spacer></v-spacer>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
      >
          <v-text-field
              outlined
              dense
              clearable
          ></v-text-field>
      </v-col>
      <v-col
          class="d-flex add-button-custom"
          cols="12"
          sm="2"
      >
        <div class="text-center">

          <v-menu
              top
              :close-on-content-click="closeOnContentClick"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                  elevation="1"
                  white
                  v-bind="attrs"
                  v-on="on"
              >
                <v-icon>mdi-plus</v-icon>
              </v-btn>
            </template>

            <v-list>
              <v-list-item
                  v-for="(item, index) in items"
                  :key="index"
              >
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>
      </v-col>
      </v-card>

    </v-sheet>
    <v-sheet class="sheet-custom"
             color="white"
             elevation="1"
             rounde
    >
      <v-card class="card-custom d-flex"
              flat>
        <v-col
            class="d-flex first-col-color"
            cols="12"
            sm="1"
        >
          <v-card-text class="text-lg-h6">
            And
          </v-card-text>
        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="3"
        >
          <v-select
              :items="items"
              dense
              outlined
          ></v-select>
        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="3"
        >
          <v-select
              :items="items"
              dense
              outlined
          ></v-select>
        </v-col>
        <v-spacer></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="3"
        >
          <v-text-field
              outlined
              dense
              clearable
          ></v-text-field>
        </v-col>
        <v-col
            class="d-flex add-button-custom"
            cols="12"
            sm="2"
        >
          <div class="text-center">

            <v-menu
                top
                :close-on-content-click="closeOnContentClick"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                    elevation="1"
                    white
                    v-bind="attrs"
                    v-on="on"
                >
                  <v-icon>mdi-plus</v-icon>
                </v-btn>
              </template>

              <v-list>
                <v-list-item
                    v-for="(item, index) in items"
                    :key="index"
                >
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </div>
        </v-col>
      </v-card>

    </v-sheet> -->
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
}

.sheet-custom {
  padding: 18px;
  margin-bottom: 20px;
    .divider {
      margin: 10px 0;
    }
}

.row-custom {
  margin: 0px;
 }

.first-col-color {
  background-color: #F5F5F5;
  padding: 2px;
  text-align: center;
}
.card-custom{
  align-items: baseline;
  justify-content: space-between;
}

.add-button-custom{
  align-items: center;
  justify-content: flex-end;
}


</style>