<script lang="ts" setup>
import { Link, usePage } from "@inertiajs/vue3";
import { computed } from "vue";
// import { ref } from "vue";

// const timer = ref(0);
// setInterval(() => timer.value++, 1000);

// page.props.flash.success
//const page = usePage();
const flashSuccess = computed(() => usePage().props.flash.success);
</script>

<template>
    <Link href="/">Main Page</Link>&nbsp;
    <Link href="/hello">Show Page</Link>
    <!-- <div>The page with time {{ timer }}</div> -->

    <div v-if="flashSuccess" class="success">
        {{ flashSuccess }}
    </div>

    <slot>Default</slot>
</template>

<style scoped>
.success {
    background-color: green;
    color: white;
}
</style>

function computed(arg0: () => any) { throw new Error("Function not
implemented."); }
