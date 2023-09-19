<template>
    <h1>{{ pageTitle }}</h1>
    

    <div class="text-3xl">
        {{ artist.name }}
    </div>

    <div v-for="song in artist.songs" :key="song.id">
        <div class="text-xl mt-6 my-2">
            {{ song.title }}
        </div>
    </div>
</template>
  
<script setup lang="ts">
const route = useRoute();
const pageTitle = `Artsit No. ${route.params.id}`;
const { data: artist } = await useMyFetch<any>(
    `artist/${route.params.id}`,{}
);
</script>