<template>
  <VContainer class="flex-column">
    <!-- IF -->
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
        <VSpacer />
        <VCol
          class="d-flex"
          cols="12"
          sm="7"
        >
          <VSheet
            class="content-section"
            color="white"
            elevation="1"
            rounded
          >
            <VLayout class="flex-column">
              <VSelect
                :items="items"
                label="Select parameter"
                dense
                outlined
              />
              <VSpacer />
              <VSelect
                :items="items"
                label="Select parameter"
                dense
                outlined
              />
              <VSpacer />
              <VTextField
                label="Enter the value"
                outlined
                dense
              />
              <VRow align="center">
                <VCol
                  cols="12"
                  sm="6"
                >
                  <VSubheader v-text="'Additional condition'" />
                </VCol>
                <VCol
                  cols="12"
                  sm="6"
                >
                  <VSelect
                    v-model="e6"
                    :items="states"
                    :menu-props="{ maxHeight: '400' }"
                    label="Select"
                    multiple
                    persistent-hint
                  />
                </VCol>
              </VRow>
            </VLayout>
          </VSheet>
        </VCol>
      </VFlex>
    </VLayout>
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
              AND
            </h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
            </p>
          </div>
        </VCol>
        <VSpacer />
        <VCol
          class="d-flex"
          cols="12"
          sm="7"
        >
          <VSheet
            class="content-section"
            color="white"
            elevation="1"
            rounded
          >
            <VLayout class="flex-column">
              <VSelect
                :items="items"
                label="Select parameter"
                dense
                outlined
              />
              <VSpacer />
              <VSelect
                :items="items"
                label="Select parameter"
                dense
                outlined
              />
              <VSpacer />
              <VTextField
                label="Enter the value"
                outlined
                dense
              />
            </VLayout>
          </VSheet>
        </VCol>
      </VFlex>
    </VLayout>
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
              THEN
            </h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.
            </p>
          </div>
        </VCol>
        <VSpacer />
        <VCol
          class="d-flex"
          cols="12"
          sm="7"
        >
          <VSheet
            class="content-section"
            color="white"
            elevation="1"
            rounded
          >
            <VLayout class="flex-column">
              <VRow class="row-style-custom">
                <VCol
                  cols="12"
                  sm="6"
                >
                  <VSubheader v-text="'Select Character Count'" />
                </VCol>
                <VCol
                  cols="12"
                  sm="6"
                >
                  <VSelect
                    :items="items"
                    label="Select"
                    dense
                    outlined
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol
                  cols="12"
                  sm="6"
                >
                  <VSubheader v-text="'Select Seperator Style'" />
                </VCol>
                <VCol
                  cols="12"
                  sm="6"
                >
                  <VSelect
                    :items="items"
                    label="Select"
                    dense
                    outlined
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol
                  cols="12"
                  sm="4"
                >
                  <VSubheader v-text="'Take option 1'" />
                </VCol>
                <VCol
                  cols="12"
                  sm="8"
                >
                  <VSelect
                    :items="items"
                    label="Select parameter"
                    dense
                    outlined
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol
                  cols="12"
                  sm="4"
                >
                  <VSubheader v-text="'Take option 2'" />
                </VCol>
                <VCol
                  cols="12"
                  sm="8"
                >
                  <VSelect
                    :items="items"
                    label="Select parameter"
                    dense
                    outlined
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol
                  cols="12"
                  sm="4"
                >
                  <VSubheader v-text="'Take option 3'" />
                </VCol>
                <VCol
                  cols="12"
                  sm="8"
                >
                  <VSelect
                    :items="items"
                    label="Select parameter"
                    dense
                    outlined
                  />
                </VCol>
              </VRow>
            </VLayout>
          </VSheet>
        </VCol>
      </VFlex>
    </VLayout>
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
        </VCol>
        <VSpacer />
        <VCol
            class="d-flex justify-space-between"
            cols="12"
            sm="7"
        >
          <v-btn
              depressed
              color="error"
          >
            Clear
          </v-btn>
          <v-btn
              depressed
              color="primary"
          >
            Run
          </v-btn>
        </VCol>
      </VFlex>
    </VLayout>

    <v-alert
        class="mx-4"
        dense
        type="info"
    >
      I'm a dense alert with a <strong>type</strong> of info
    </v-alert>
  </VContainer>
</template>

<script>
export default {
    name: 'IndexTab',
    data: () => ({
        items: [
            { title: 'And' },
            { title: 'Or' },
            { title: 'Copy' },
        ],
    }),
};
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