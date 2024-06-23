<script>
export default {
    name: 'CreateCategory',
}
</script>
<script setup>
import {useForm} from "@inertiajs/vue3";
import AppLayout from "@/Layouts/AppLayout.vue";
import CategoryForm from "@/Components/Categories/CategoryForm.vue"

const form = useForm({
    name: ''
})
</script>
<template>
    <AppLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Add a New Category
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
                <CategoryForm :form="form" @submit="form.post(route('categories.store'))"/>
            </div>
        </div>
    </AppLayout>
</template>
