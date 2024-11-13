<template>
  <div>
    <UCard>
      <template #header>
        <div class="flex justify-between">
          <div class="flex items-center space-x-2">
            <span>{{ title }} - Status: [{{ status }}] </span>
            <UIcon
              :class="{ 'text-green-600': status === 'Booked' }"
              name="heroicons:check-16-solid"
              class="w-5 h-5"
            />
          </div>

          <UButton class="bg-red-200 text-red-900" size="xs">Cancel</UButton>
        </div>
      </template>
    </UCard>
  </div>
</template>

<script lang="ts" setup>
defineProps({
  title: { type: String, required: true },
  status: String,
});

defineEmits(["booking"]);
</script>

<style></style>
