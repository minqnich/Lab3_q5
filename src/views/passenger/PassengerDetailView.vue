<script setup lang="ts">
// import { ref } from 'vue'
// import type { Ref } from 'vue'
import { type PassengerItem } from '@/passenger'
// import EventService from '@/services/EventService'
// const event = ref<EventItem | null> (null)
// const id: Ref<number> = ref(123)
// EventService.getEventById(id.value)
import type { PropType } from 'vue'
// const props = defineProps({
//     id: String
// })
defineProps({
  passenger: {
    type: Object as PropType<PassengerItem>,
    require: true
  }
})

// EventService.getEventById(Number(props.id)).then((response) => {
//     event.value = response.data
// }).catch(error => {
//     console.log(error)
// })
</script>
<template>
  <div v-if="passenger">
    <p>{{ passenger.first_name }}</p>
    <p>{{ passenger.last_name }}</p>
    <p>{{ passenger.email }}</p>
    <p>{{ passenger.gender }}</p>
    <p>{{ passenger.ip_address }}</p>
    <p>{{ passenger.Source }}</p>
    <p>{{ passenger.Destination }}</p>
    <p>{{ passenger.travelDate }}</p>
    <p>{{ passenger.airlineId }}</p>
  </div>

</template>
