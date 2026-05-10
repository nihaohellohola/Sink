<script setup lang="ts">
defineProps<{
  id: string
  modelValue?: boolean
  label: string
  description?: string
}>()

const emit = defineEmits<{
  'update:modelValue': [value: boolean]
}>()
</script>

<template>
  <Field>
    <div class="flex items-center justify-between">
      <div class="space-y-0.5">
        <FieldLabel :for="id">
          {{ label }}
        </FieldLabel>
        <p v-if="description" class="text-xs text-muted-foreground">
          {{ description }}
        </p>
      </div>
      <Switch
        :id="id"
        :model-value="modelValue"
        @update:model-value="emit('update:modelValue', $event)"
      />
    </div>
  </Field>
</template>
