<template>
    <h1>Artist</h1>
    <div v-if="pending">
        Pending...</div>

    <div v-else v-for="artist in artists" :key="artist.id">
        <div class="m-4 text-blue-200">
            <nuxt-link :to="`/artists/${artist.id}`">
                {{artist.name}}
            </nuxt-link>
        </div>
    </div>
</template>

<script setup lang="ts">
//const config = useRuntimeConfig()
const { data: artists, pending } = await useMyFetch<any>("artist",{})

</script>