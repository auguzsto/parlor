<template>
    <div>
        <v-sheet>
            <v-calendar
                ref="calendar"
                v-model="today"
                :events="events"
                color="primary"
                view-mode="week"
                :interval-height="80"
            >
            </v-calendar>
        </v-sheet>
    </div>
</template>

<script setup lang="ts">
import type { VNodeRef } from 'vue'
definePageMeta({
    title: "Agenda"
})

    interface Event {
        title: string,
        start: Date,
        end: Date,
        color?: string,
        allDay?: boolean
    }

    const calendar = ref<VNodeRef>("")
    const events: Array<Event> = [
        {
            title: 'Everto',
            start: new Date('2025-07-27 09:00'),
            end: new Date('2025-07-27 09:59'),
            color: "blue",
        },
         {
            title: 'Augusto',
            start: new Date('2025-07-27 11:00'),
            end: new Date('2025-07-27 11:59'),
            color: "blue",
        },
    ]

  const today = ref<Date[]>([new Date()])
</script>