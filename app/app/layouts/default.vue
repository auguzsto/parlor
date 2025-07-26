<template>
    <div>
        <VNavigationDrawer v-model="drawer"></VNavigationDrawer>
        <VAppBar>
            <VAppBarNavIcon @click.stop="drawer = !drawer" ></VAppBarNavIcon>
            <VAppBarTitle>Agenda</VAppBarTitle>
        </VAppBar>
        <VMain>
            <VContainer>
                <slot />
            </VContainer>
        </VMain>
    </div>
</template>
<script setup lang="ts">
    const drawer = ref<boolean>(false)
</script>