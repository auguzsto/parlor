<template>
    <div v-for="item in items">
        <v-list-item 
            color="primary"
            nuxt :to="item.link" 
            :title="item.title" 
            :prepend-icon="item.icon">
        </v-list-item>
    </div>
</template>

<script setup lang="ts">
    const items = [
        {title: "Início", icon: "mdi-home", link: "/"},
        {title: "Agenda", icon: "mdi-calendar", link: "/agenda"},
        {title: "Profissionais", icon: "mdi-tools", link: "/profissionais"},
        {title: "Financeiro", icon: "mdi-cash", link: "/financeiro"},
    ];
</script>