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
                :items="if_first_selector"
                label="Select parameter"
                dense
                outlined
              />
              <VSpacer />
              <VSelect
                :items="if_second_selector"
                label="Select parameter"
                dense
                outlined
              />
              <VSpacer />
              <VTextField input
                  label="Enter the value"
                  outlined
                  dense
                  :rules="rules"
                  v-model="UserValue"
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
                    :items="additional_selector"
                    :menu-props="{ maxHeight: '400' }"
                    label="Select"
                    persistent-hint
                    @select="additional_selector"
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
        />
        <VSpacer />
        <VCol
          class="d-flex justify-space-between"
          cols="12"
          sm="7"
        >
          <VBtn
            depressed
            color="error"
          >
            Clear
          </VBtn>
          <VBtn
            depressed
            color="primary"
          >
            Run
          </VBtn>
        </VCol>
      </VFlex>
    </VLayout>
  </VContainer>
</template>

<script>
export default {
    name: 'IndexTab',
    data: () => ({
        if_first_selector: [ 'All', 'Vendor', 'Collection', 'Product type', 'Inventory quantity', 'Price', 'Compare at price', 'Cost per item' ],
        if_second_selector: [ 'is', 'is not', 'contains', 'does not contain', 'is empty', 'is not empty', 'is greater then', 'is greater or equal to', 'is less then', 'is less or equal to' ],
        additional_selector: [ 'And', 'Or' ],
        conditions: [
            [
                { action: 'all', value: 'foot' },
                { action: 'vendor_is', value: 'reebok' },
                { action: 'collection_is', value: 'foot' },
                { action: 'product_type_is', value: 'reebok' },
                { action: 'inventory_quantity', value: 'foot' },
                { action: 'price', value: 'reebok' },
                { action: 'compare_at_price', value: 'foot' },
                { action: 'cost', value: 'foot' },
            ],
            [
                { action: 'all', value: 'foot' },
                { action: 'vendor_is', value: 'reebok' },
                { action: 'collection_is', value: 'foot' },
                { action: 'product_type_is', value: 'reebok' },
                { action: 'inventory_quantity', value: 'foot' },
                { action: 'price', value: 'reebok' },
                { action: 'compare_at_price', value: 'foot' },
                { action: 'cost', value: 'foot' },
            ]
        ],
      rules: [
        value => !!value || 'Required.',
        value => (value || '').length <= 20 || 'Max 20 characters',
      ],
    }),
    methods: {
        doSmth () {
            console.log('adwsdasd');
        },
        UserValue({target}){
            console.log(target.value);
        }
    }
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