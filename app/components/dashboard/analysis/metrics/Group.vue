<script setup>
defineProps({
  tabs: {
    type: Array,
    required: true,
  },
  rawTabs: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <Tabs
    :default-value="rawTabs[0]"
    class="flex flex-col"
  >
    <TabsList class="w-fit">
      <TabsTrigger
        v-for="(tab, index) in tabs"
        :key="tab"
        :value="rawTabs[index]"
      >
        {{ tab }}
      </TabsTrigger>
    </TabsList>
    <TabsContent
      v-for="(tab, index) in tabs"
      :key="tab"
      :value="rawTabs[index]"
      class="flex-1"
    >
      <DashboardAnalysisMetricsMetric
        :type="rawTabs[index]"
        :name="tab"
        class="h-full"
      />
    </TabsContent>
  </Tabs>
</template>
