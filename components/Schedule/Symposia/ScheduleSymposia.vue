<template>
  <div class="p-8 pl-0">
    <h1
      class="text-lg font-bold"
      :class="item.highlight && 'text-primary-dark'"
    >
      {{ item.title }}
    </h1>

    <p
      v-if="item.description"
      class="text-sm mb-4"
      v-html="item.description"
    />
    <ul
      v-if="item.speakers"
      class="pb-2"
    >
      <li
        v-for="speaker in item.speakers"
        class="font-medium text-primary-dark py-1.5"
      >
        <ScheduleSpeaker :speaker="speaker" />
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { IScheduleItem } from '~/interfaces'

interface IProps {
  item: IScheduleItem
}

const props = defineProps<IProps>()
</script>
