<template>
  <section>
    <div class="container mx-auto flex flex-col px-4 md:px-8 py-16 md:py-20">
      <div
        id="Schedule"
        class="pt-8 pb-12 scroll-mt-36 md:scroll-mt-40"
      >
        <h1 class="text-4xl md:text-5xl">Schedule</h1>
        <h2>{{ data.subtitle }}</h2>
      </div>
      <template
        v-for="(day, index) in data.schedule"
        :key="index"
      >
        <ScheduleDay
          class="mb-16 text-hind"
          :day="day"
        />
      </template>
    </div>
  </section>
</template>

<script setup>
const { data } = await useAsyncData('schedule', () =>
  queryContent('/schedule').findOne()
)
</script>
