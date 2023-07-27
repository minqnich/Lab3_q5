<script setup lang="ts">
import { type AirlineItem } from '@/airline'
import type { PropType } from 'vue'

defineProps({
    airline: {
        type: Object as PropType<AirlineItem>,
            require: true
    }
})

</script>
<template>
    <div v-if="airline">
        <p>{{ airline.id }} </p>
        <p>  Name : {{ airline.AirlineName }}</p>
            <p>  Email : {{ airline.email }} </p>
                <p> Address : {{ airline.address }} </p>

    </div>

</template>