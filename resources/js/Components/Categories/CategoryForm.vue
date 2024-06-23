<script setup>

import FormSection from "@/Components/FormSection.vue";
import InputLabel from "@/Components/InputLabel.vue";
import TextInput from "@/Components/TextInput.vue";
import InputError from "@/Components/InputError.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";

const props = defineProps({
    form: {
        type: Object,
        required: true
    },
    updating: {
        type: Boolean,
        required: false,
        default: false,
    }
})

const emit = defineEmits(['submit']);
</script>
<template>
    <FormSection @submitted="$emit('submit')">
        <template #title>
            {{ props.updating ? 'Update Category' : 'Create Category' }}
        </template>
        <template #form>
           <div class="col-span-6 sm:col-span-6">
               <InputLabel for="name" value="name"/>
               <TextInput id="name" v-model="props.form.name" type="text" autocomplete="name" class="mt1 block w-full"/>
               <InputError :message="$page.props.errors.name" class="mt-2" />
           </div>
        </template>
        <template #actions>
            <PrimaryButton>
                {{ props.updating ? 'Update Category' : 'Create Category' }}
            </PrimaryButton>
        </template>
    </FormSection>
</template>
