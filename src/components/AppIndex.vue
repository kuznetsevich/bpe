<template>
  <div class="tab_wrapper">
    <VTabs
      v-model="tab"
      :width="width"
      background-color="transparent"
      class="navi-tabs"
    >
      <VTab href="#index_app_tab">
        Generator
      </VTab>
      <VTab href="#task_app_tab">
        Tasks
      </VTab>
      <VTab href="#instruction_app_tab">
        Instruction
      </VTab>
      <VTab href="#add_app_tab">
        Other apps
      </VTab>
    </VTabs>

    <VTabsItems v-model="tab">
      <VTabItem id="index_app_tab">
        <IndexTab />
      </VTabItem>
      <VTabItem id="task_app_tab">
        <TasksTab />
      </VTabItem>
      <VTabItem id="instruction_app_tab">
        <InstructionTab />
      </VTabItem>
      <VTabItem id="add_app_tab">
        <AdsTab />
      </VTabItem>
    </VTabsItems>
  </div>
</template>

<script>
import AdsTab from '@/components/Tabs/AdsTab';
import IndexTab from '@/components/Tabs/IndexTab';
import InstructionTab from '@/components/Tabs/InstructionTab';
import TasksTab from '@/components/Tabs/TasksTab';
export default {
    name: 'AppIndex',
    components: { IndexTab, AdsTab, TasksTab, InstructionTab },
    data: () => ({
        tab: null,
    }),
    computed: {
        // eslint-disable-next-line vue/return-in-computed-property
        width () {
            switch (this.$vuetify.breakpoint.name) {
                case 'xs': return 220;
                case 'sm': return 400;
                case 'md': return 500;
                case 'lg': return 600;
                case 'xl': return 800;
            }
        },
    },
};
</script>

<style scoped lang="scss">
    .navi-tabs {
      margin-bottom: 30px;
      letter-spacing: normal;
    }
    .tab_wrapper {

    }
</style>