<template>
  <div>
    <UCard>
      <template #header>
        <span>{{ title }}</span>
      </template>

      <div>{{ when }}</div>

      <div>{{ description }}</div>
      <template #footer>
        <section class="flex justify-end">
          <UButton label="Register" @click="$emit('register')" />
        </section>
      </template>
    </UCard>
  </div>
</template>

<script lang="ts" setup>
defineProps({
  title: { type: String, required: true },
  when: String,
  description: String,
});

defineEmits(["register"]);
</script>

<style></style>
