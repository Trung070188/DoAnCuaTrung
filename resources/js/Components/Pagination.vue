<template>
    <div class="flex">
        <template v-for="(link, key) in links" :key="key">
            <div
                v-if="link.url === null"
                v-html="link.label"
                class="mb-1 nr-1 px-4 py-3 text-gray-400 text-sm leading-4 border rounded"
            ></div>
            <Link
                v-else
                :href="link.url"
                v-html="link.label"
                class="mb-1 nr-1 px-4 py-3 text-sm leading-4 border rounded focus:text-indigo-500 focus:border-indigo-500 hover:bg-white"
                :class="{ 'bg-indigo-200': link.active }"
            >
            </Link>
        </template>
    </div>
</template>

<script setup>
import { Link } from "@inertiajs/inertia-vue3";
import {defineProps} from "vue";
const props = defineProps({
    links: Array,
});

</script>

<style></style>
