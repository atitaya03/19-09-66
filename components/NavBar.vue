
import { Title } from 'nuxt/dist/head/runtime/components';
<template>
    <nav class="flex px-2">
        <NuxtLink to="/"> Home </NuxtLink>
        <NuxtLink to="/artists"> Artist </NuxtLink>
        <NuxtLink to="/artists/create" title="Add Artist"> Add Artist </NuxtLink>
    </nav>
</template>