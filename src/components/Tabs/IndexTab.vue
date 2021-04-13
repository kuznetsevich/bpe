<template>
  <VContainer class="flex-column">
    <!-- IF -->
    <VLayout column>
      <VFlex d-flex xs12>
        <VCol class="d-flex" cols="12" sm="6">
          <div class="if-notes">
            <h6 class="title">IF</h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic,
              print, and publishing industries for previewing layouts and visual
              mockups.
            </p>
          </div>
        </VCol>
        <VSpacer />
        <VCol class="d-flex" cols="12" sm="6">
          <VSheet class="content-section" color="white" elevation="1" rounded>
            <VLayout class="flex-column">
              <VSelect
                  v-model="answer.if_first_selector"
                  :items="if_first_selector"
                  label="Select parameter"
                  dense
                  outlined
                  @change="changeIfFirstSelectorValue"
              />
              <VSpacer />
              <VExpandTransition>
                <VSelect
                    v-show="if_second_text_selector_is_show"
                    v-model="answer.if_second_selector"
                    :items="if_second_selector"
                    label="Select parameter"
                    dense
                    outlined
                />
                <VSpacer />
              </VExpandTransition>
              <VExpandTransition>
                <VTextField
                    v-show="if_second_text_selector_is_show"
                    v-model="answer.if_text_selector"
                    input
                    label="Enter the value"
                    outlined
                    dense
                    :rules="rules"
                />
              </VExpandTransition>
              <VExpandTransition>
                <VRow align="center" v-show="if_second_text_selector_is_show">
                  <VCol cols="12" sm="6">
                    <VSubheader v-text="'Additional condition'" />
                  </VCol>
                  <VCol cols="12" sm="6">
                    <VSelect
                        v-model="e6"
                        :items="additional_selector"
                        :menu-props="{ maxHeight: '400' }"
                        label="Select"
                        persistent-hint
                        @select="additional_selector"
                        @change="changeAdditionalSelectorValue"
                    />
                  </VCol>
                </VRow>
              </VExpandTransition>
            </VLayout>
          </VSheet>
        </VCol>
      </VFlex>
    </VLayout>
    <VLayout column>
      <VExpandTransition>
        <VFlex d-flex xs12 v-if="and_or_section_is_view">
          <VCol class="d-flex" cols="12" sm="4">
            <div class="if-notes">
              <h6 class="title">{{ and_or_section_text.title }}</h6>
              <p class="if-description caption">
                {{ and_or_section_text.description }}
              </p>
            </div>
          </VCol>
          <VSpacer />
          <VCol class="d-flex" cols="12" sm="7">
            <VSheet class="content-section" color="white" elevation="1" rounded>
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
                <VTextField label="Enter the value" outlined dense />
              </VLayout>
            </VSheet>
          </VCol>
        </VFlex>
      </VExpandTransition>
    </VLayout>
    <VLayout column>
      <VFlex d-flex xs12>
        <VCol class="d-flex" cols="12" sm="4">
          <div class="if-notes">
            <h6 class="title">THEN</h6>
            <p class="if-description caption">
              Lorem ipsum is placeholder text commonly used in the graphic,
              print, and publishing industries for previewing layouts and visual
              mockups.
            </p>
          </div>
        </VCol>
        <VSpacer />
        <VCol class="d-flex" cols="12" sm="7">
          <VSheet class="content-section" color="white" elevation="1" rounded>
            <VLayout class="flex-column">
              <VRow class="row-style-custom">
                <VCol cols="12" sm="6">
                  <VSubheader v-text="'Select Character Count'" />
                </VCol>
                <VCol cols="12" sm="6">
                  <VSelect
                      :items="[3, 4, 5, 6, 7, 8, 9]"
                      label="Select"
                      dense
                      outlined
                      v-model="answer.then_character_count"
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol cols="12" sm="6">
                  <VSubheader v-text="'Select Seperator Style'" />
                </VCol>
                <VCol cols="12" sm="6">
                  <VSelect
                      :items="['/', '.', ':', ',', '-', 'merged']"
                      label="Select"
                      dense
                      outlined
                      v-model="answer.then_separator_style"
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol cols="12" sm="4">
                  <VSubheader v-text="'Take option 1'" />
                </VCol>
                <VCol cols="12" sm="8">
                  <VSelect :items="items" label="Select size" dense outlined v-model="answer.then_size"/>
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol cols="12" sm="4">
                  <VSubheader v-text="'Take option 2'" />
                </VCol>
                <VCol cols="12" sm="8">
                  <VSelect
                      :items="thenAbbreviatedName"
                      label="Select color"
                      dense
                      outlined
                      v-model="answer.then_color"
                  />
                </VCol>
              </VRow>
              <VRow class="row-style-custom">
                <VCol cols="12" sm="4">
                  <VSubheader v-text="'Take option 3'" />
                </VCol>
                <VCol cols="12" sm="8">
                  <VSelect
                      :items="items"
                      label="Select material"
                      dense
                      outlined
                      v-model="answer.then_material"
                  />
                </VCol>
              </VRow>
            </VLayout>
          </VSheet>
        </VCol>
      </VFlex>
    </VLayout>
    <VLayout column>
      <VFlex d-flex xs12>
        <VCol class="d-flex" cols="12" sm="4" />
        <VSpacer />
        <VCol class="d-flex justify-space-between" cols="12" sm="7">
          <VBtn depressed color="error" @click="clearSelectors"> Clear </VBtn>
          <VBtn depressed color="primary" @click="sendAnswer"> Run </VBtn>
        </VCol>
      </VFlex>
    </VLayout>
  </VContainer>
</template>

<script>
export default {
  name: "IndexTab",
  data: () => ({
    answer: {
      if_first_selector: "",
      if_second_selector: "",
      if_text_selector: "",
      then_character_count: 9,
      then_separator_style: "/",
      then_size: "",
      then_color: "",
      then_material: "",
    },
    if_second_text_selector_is_show: true,
    and_or_section_is_view: false,
    and_or_section_text: {
      title: "And",
      description: "Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.",
    },
    if_first_selector: [
      "All",
      "Vendor",
      "Collection",
      "Product type",
      "Inventory quantity",
      "Price",
      "Compare at price",
      "Cost per item",
    ],
    if_second_selector: [
      "is",
      "is not",
      "contains",
      "does not contain",
      "is empty",
      "is not empty",
      "is greater then",
      "is greater or equal to",
      "is less then",
      "is less or equal to",
    ],
    additional_selector: ["And", "Or", "None"],
    then_selector_colors: [
      "Black",
      "Blue",
      "White",
      "Orange"
    ],
    conditions: [
      [
        { action: "all", value: "foot" },
        { action: "vendor_is", value: "reebok" },
        { action: "collection_is", value: "foot" },
        { action: "product_type_is", value: "reebok" },
        { action: "inventory_quantity", value: "foot" },
        { action: "price", value: "reebok" },
        { action: "compare_at_price", value: "foot" },
        { action: "cost", value: "foot" },
      ],
      [
        { action: "all", value: "foot" },
        { action: "vendor_is", value: "reebok" },
        { action: "collection_is", value: "foot" },
        { action: "product_type_is", value: "reebok" },
        { action: "inventory_quantity", value: "foot" },
        { action: "price", value: "reebok" },
        { action: "compare_at_price", value: "foot" },
        { action: "cost", value: "foot" },
      ],
    ],
    rules: [
      (value) => !!value || "Required.",
      (value) => (value || "").length <= 20 || "Max 20 characters",
    ],
  }),
  methods: {
    // doSmth() {
    //   console.log("adwsdasd");
    // },
    changeIfFirstSelectorValue(value) {
      this.answer.if_first_selector = value;

      if (value !== "All") {
        this.if_second_text_selector_is_show = true;
      } else {
        this.if_second_text_selector_is_show = false;
      }
    },
    sendAnswer() {
      console.log(this.answer);
    },
    changeAdditionalSelectorValue(value) {
      console.log(value);

      if (value === "None") {
        this.and_or_section_is_view = false;
      } else if (value === "Or") {
        this.and_or_section_is_view = true;
        this.and_or_section_text.title = "Or";
        this.and_or_section_text.description = "Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing";
      } else if (value === "And") {
        this.and_or_section_is_view = true;
        this.and_or_section_text.title = "And";
        this.and_or_section_text.description = "Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for previewing layouts and visual mockups.";
      }
    },
    clearSelectors() {
      this.and_or_section_is_view = false;

      this.answer.if_first_selector = "",
          this.answer.if_second_selector = "",
          this.answer.if_text_selector = "",
          this.answer.then_character_count = 9;
      this.answer.then_separator_style = "/";
      this.answer.then_size = "";
      this.answer.then_color = "";
      this.answer.then_material = "";
    }
  },
  computed: {
    thenAbbreviatedName() {
      let arr = [];

      this.then_selector_colors.forEach(item => {
        arr.push(item.slice(0, this.answer.then_character_count));
      });

      return arr;
    }
  }
};
</script>

<style style scoped lang="scss">
.container {
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
.content-section {
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