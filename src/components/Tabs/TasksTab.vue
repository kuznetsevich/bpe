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
                        AND
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
                        THEN
                      </h6>
                      <p class="if-description caption">
                        Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
                      </p>
                    </div>
                  </VCol>
                </VFlex>
                <v-divider
                    class="pa-2"
                ></v-divider>
                <VFlex
                    align-baseline
                    d-flex
                    xs12
                >
                  <VCol
                      class="d-flex"
                      cols="12"
                      sm="6"
                  >
                    <v-btn
                        disabled
                        color="primary"
                    >
                      Download CSV
                    </v-btn>
                  </VCol>
                  <VCol
                      class="d-flex task-restore-btn"
                      cols="12"
                      sm="6"
                  >
                    <p class="subheading">Processing...</p>
                  </VCol>
                </VFlex>
                <v-progress-linear
                    color="deep-purple accent-4"
                    indeterminate
                    rounded
                    height="6"
                ></v-progress-linear>
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
                        AND
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
                        THEN
                      </h6>
                      <p class="if-description caption">
                        Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
                      </p>
                    </div>
                  </VCol>
                </VFlex>
                <v-divider
                    class="pa-2"
                ></v-divider>
                <VFlex
                    d-flex
                    xs12
                >
                  <VCol
                      class="d-flex"
                      cols="12"
                      sm="6"
                  >
                    <v-btn
                        depressed
                        color="primary"
                    >
                      Download CSV
                    </v-btn>
                  </VCol>
                  <VCol
                      class="d-flex task-restore-btn"
                      cols="12"
                      sm="6"
                  >
                    <v-btn
                        depressed
                        color="error"
                    >
                      Restore
                    </v-btn>
                  </VCol>
                </VFlex>
              </VLayout>
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
                        AND
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
                        THEN
                      </h6>
                      <p class="if-description caption">
                        Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
                      </p>
                    </div>
                  </VCol>
                </VFlex>
                <v-divider
                    class="pa-2"
                ></v-divider>
                <VFlex
                    d-flex
                    xs12
                >
                  <VCol
                      class="d-flex"
                      cols="12"
                      sm="6"
                  >
                    <v-btn
                        disabled
                        color="primary"
                    >
                      Download CSV
                    </v-btn>
                  </VCol>
                  <VCol
                      class="d-flex task-restore-btn"
                      cols="12"
                      sm="6"
                  >
                    <v-btn
                        depressed
                        color="error"
                    >
                      Push
                    </v-btn>
                  </VCol>
                </VFlex>
              </VLayout>
            </v-expansion-panel-content>
          </v-expansion-panel>

        </v-expansion-panels>
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

.task-restore-btn {
  justify-content: flex-end;
}

</style>