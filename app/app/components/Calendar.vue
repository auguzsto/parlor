<template>
    <v-sheet class="border rounded-xl h-screen ms-2 elevation-3 pa-6">
        <v-row justify="center" class="">
            <v-btn class="rounded-circle" size="60" color="primary">
                {{ props.dateSelected.getDate() }}
            </v-btn>
        </v-row>
        <v-row class="">
            <v-col v-for="category in props.categories" class="d-flex justify-center">
                {{ category }}
            </v-col>
        </v-row>
        <v-divider></v-divider>
        <div class="overflow-auto mt-5 ms-3" style="height: 90%;">
            <v-row v-for="hour in getHours()" class="border-b">
                <v-col cols="auto" class="border-e" style="height: 96px;">
                    <div class="position-relative mt-7 bg-white" ref="start">
                        {{ hour }}
                    </div>
                </v-col>
                <v-col v-for="(item, index) in props.categories" class="border-e d-flex justify-start">
                    <v-card color="primary" style="height: 28px;">
                        Matheus - {{ hour }}
                    </v-card>
                </v-col>
            </v-row>
        </div>
    </v-sheet>
</template>
<script setup lang="ts">
import type { Calendar } from '~/interfaces/Calendar';

const props = defineProps<Calendar>()

const startHour = 0
const endHour = 24
const startElement = useTemplateRef("start")

const getHours = () => {
    let hours = []
    for (let hour = startHour; hour <= endHour; hour++) {
        let hourFormated = `${hour}h`
        if (hour <= 9) {
            hourFormated = `0${hour}h`
        }
        
        hours.push(hourFormated)
    }
    return hours
}
</script>