<script setup lang="ts">
// import { ref } from 'vue'
// import type { Ref } from 'vue'
import { type PassengerItem } from '@/passenger'
import { useRouter } from 'vue-router'
import { useMessageStore } from '@/stores/message'
// import EventService from '@/services/EventService'
// const event = ref<EventItem | null> (null)
// const id: Ref<number> = ref(123)
// EventService.getEventById(id.value)
import type { PropType } from 'vue'
// const props = defineProps({
//     id: String
// })
const props = defineProps({
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
const router = useRouter()
const store = useMessageStore()
function edit(){
    store.updateMessage(props.passenger?.first_name + ' The data has been update')
    setTimeout(() => {
        store.resetMessage()
    },3000)
    router.push({
        name: 'passenger',
        params: {
            id: props.passenger?.id
        }
    })
}
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
  <button @click="edit">Edit</button>
</template>
