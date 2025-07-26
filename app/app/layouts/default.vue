<template>
    <div>
        <v-navigation-drawer v-model="drawer">
            <Avatar />
            <v-divider></v-divider>
            <MenuNavigation />
        </v-navigation-drawer>
        <v-app-bar>
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" ></v-app-bar-nav-icon>
            <v-app-bar-title>{{ $route.meta.title ?? "App" }}</v-app-bar-title>
        </v-app-bar>
        <v-main>
            <v-container>
                <slot />
            </v-container>
        </v-main>
    </div>
</template>

<script setup lang="ts">
import Avatar from './components/Avatar.vue';
import MenuNavigation from './components/MenuNavigation.vue';

const drawer = ref<boolean>(false)
const route = useRoute()
useSeoMeta({
    title: "Parlor - Plataforma para gerenciar seu salão de beleza",
})
</script>