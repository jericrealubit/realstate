<script setup>
import { Link, usePage } from "@inertiajs/vue3";
import { computed } from "vue";

const flashSuccess = computed(() => usePage().props.flash.success);
</script>

<template>
    <header
        class="border-b border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-900 w-full"
    >
        <div class="container mx-auto">
            <nav class="p-4 flex items-center justify-between">
                <div class="text-lg font-medium">
                    <Link :href="route('listing.index')">Listings</Link>
                </div>
                <div
                    class="text-xl text-indigo-600 dark:text-indigo-300 font-bond text-centered"
                >
                    <Link :href="route('listing.index')">Lara App</Link>
                </div>
                <div>
                    <Link :href="route('listing.create')" class="btn-primary"
                        >+ New Listing</Link
                    >
                </div>
            </nav>
        </div>
    </header>

    <main class="container mx-auto p-4 w-full">
        <div
            v-if="flashSuccess"
            class="mb-4 border rounded-md shadow-sm border-green-200 dark:border-green-800 bg-green-50 dark:bg-green-900 p-2"
        >
            {{ flashSuccess }}
        </div>
        <slot>Default</slot>
    </main>
</template>
