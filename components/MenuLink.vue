<template>
    <nav class="flex">
        <NuxtLink class="px-2 py-2 my-2 bg-green-400" :to="to"> <slot/> </NuxtLink>
    </nav>
</template>

<script set up lang = "ts">
    const props = defineProps(['to','title']) //ส่งค่าให้ทำงาน
</script>