<template>
  <VContainer class="flex-column">
    <VLayout column>
      <VFlex
          flex-column
          xs12
      >

        <v-expansion-panels>

          <v-expansion-panel>
            <v-expansion-panel-header>
              Item
              <template v-slot:actions>
                <v-icon color="primary">
                  mdi-timer-sand
                </v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              <VLayout column>
                <VFlex
                    d-flex
                    xs12
                >
                  <VCol
                      class="d-flex"
                      cols="12"
                      sm="4"
                  >
                    <div class="if-notes">
                      <h6 class="title">
                        IF
                      </h6>
                      <p class="if-description caption">
                        Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
                      </p>
                    </div>
                  </VCol>
                  <VCol
                      class="d-flex"
                      cols="12"
                      sm="4"
                  >
                    <div class="if-notes">
                      <h6 class="title">
                        IF
                      </h6>
                      <p class="if-description caption">
                        Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
                      </p>
                    </div>
                  </VCol>
                </VFlex>
              </VLayout>
            </v-expansion-panel-content>
          </v-expansion-panel>

          <v-expansion-panel>
            <v-expansion-panel-header disable-icon-rotate>
              Item
              <template v-slot:actions>
                <v-icon color="teal">
                  mdi-check
                </v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </v-expansion-panel-content>
          </v-expansion-panel>

          <v-expansion-panel>
            <v-expansion-panel-header disable-icon-rotate>
              Item
              <template v-slot:actions>
                <v-icon color="error">
                  mdi-alert-circle
                </v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </v-expansion-panel-content>
          </v-expansion-panel>

        </v-expansion-panels>

        <v-pagination class="pagination-tasks-custom"
            v-model="page"
            :length="4"
            prev-icon="mdi-menu-left"
            next-icon="mdi-menu-right"
        ></v-pagination>
      </VFlex>
    </VLayout>
  </VContainer>

</template>

<script>
export default {
    name: 'TasksTab',
  panel: [0, 1],
  disabled: false,
  readonly: false,
};




</script>

</script>

<style scoped>

.block-margin-custom{
  margin-top: 0;
}

.pagination-tasks-custom {
  justify-content: center;
  margin-top: 4%;
}

</style>