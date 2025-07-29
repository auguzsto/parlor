<template>
    <v-row no-gutters>
        <v-col cols="3">
            <v-date-picker
                show-adjacent-months
                title="Selecione uma data"
                v-model="today"
            >
                <template v-slot:actions>
                    <v-btn variant="outlined" @click="today = new Date()">
                        Hoje
                    </v-btn>
                </template>
            </v-date-picker>
        </v-col>
        <v-col cols="9">
            <Calendar 
                :dateSelected="today"
                :categories="categories"
            />
        </v-col>
    </v-row>
</template>

<script setup lang="ts">
import Calendar from '../../components/Calendar.vue'

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

    const today = ref<Date>(new Date())
    const categories: string[] = ["Profissional 1", "Profissional 2"]
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
</script>