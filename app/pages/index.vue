<template>
  <div class="container mx-auto p-4 space-y-8">
    <h1 class="text-3xl">Event Booking App</h1>
    <h2 class="text-2xl">All Events</h2>
    <div class="grid grid-cols-3 gap-4">
      <EventCard
        v-for="event in fetchEvents()"
        :key="event.id"
        title="event.title"
        description="event.description"
        when="event.date"
        @register="console.log('register')"
      />
    </div>
    <h2 class="text-2xl">Your Bookings</h2>
    <div class="grid gap-4">
      <BookingsCard
        v-for="i in 3"
        :key="i"
        title="Booking Name"
        status="Booked"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
onMounted(() => {
  fetchEvents();
});
const fetchEvents = async () => {
  const response = await fetch("/data/event-data.json");
  const data = await response.json();
};
</script>

<style></style>
