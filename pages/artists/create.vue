<template>
    <h1 class="text-3xl"> Add Artits </h1>
    <form @submit.prevent="onSubmit()">
        <div>
            <label for="name"> Artist Name </label>
            <p v-if="errorMessage" class="text-red-500">{{ errorMessage }}</p>
            <input v-model="formData.name" type="text" id="name">
        </div>
        <div>
            <button type="submit">
                Submit
            </button>
        </div>
    </form>
</template>

<script setup lang="ts">
const formData = ref({
    name: ""
})

const errorMessage = ref("")
async function onSubmit() {
    const { name } = formData.value
    //const config = useRuntimeConfig()
    const { data: response, error } = await useMyFetch<any>("artist", { method: "POST", body: { name, image_path:"image url" }})
    if (response.value !== null) {
        errorMessage.value = ""
        await navigateTo(`/artists/${response.value.id}`)
    } else {
        const{ statusMessage, data } = error.value! //obj error might not contains value 
        errorMessage.value = data.message

    }
}


</script>