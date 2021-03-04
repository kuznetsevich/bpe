<template>
    <v-sheet class="sheet-custom"
        color="white"
        elevation="1"
        rounde
    >
      <v-list-item-title>
      Set the rule
        <v-divider class="divider"></v-divider>
      </v-list-item-title>
      <v-card class="card-custom d-flex"
        flat>
        <v-row class="row-custom"
               cols="12"
               sm="8"
               md="3">
          <v-checkbox
              label="Only for products without SKU"
          ></v-checkbox>
        </v-row>
        <v-spacer class="spacer-custom"></v-spacer>
        <v-col
            class="d-flex"
            cols="12"
            sm="3"
        >
          <v-select
              :items="items"
              label="Character Count"
              dense
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
            label="Seperator"
            dense
        ></v-select>
      </v-col>
      </v-card>


    </v-sheet>



</template>

<script>
export default {
name: "AppGenerator"
}
</script>

<style style scoped lang="scss">

.sheet-custom {
  padding: 18px;
    .divider {
      margin: 10px 0;
    }
}

.row-custom {
  margin: 0px;
  .spacer-custom{
    width:3%;
  }
 }



</style>