<template>
    <div class="d-flex justify-center pa-4">
        <v-avatar color="primary" size="80">
            <h1>{{ firstCharacter  }}</h1>
        </v-avatar>
    </div>
</template>

<script setup lang="ts">
const firstName = "Matheus Augusto"
const firstCharacter = firstName[0]!.toUpperCase()
</script>