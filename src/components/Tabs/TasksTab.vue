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
                  $expand
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