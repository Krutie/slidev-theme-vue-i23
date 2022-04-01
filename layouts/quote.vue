<template>
    <div class="slidev-layout quote text-center" :class="class" :style="style">
        <div class="mx-auto my-auto w-11/12">
            <slot />
        </div>
    </div>
</template>
<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "@slidev/client/layoutHelper";

const props = defineProps({
    image: {
        type: String,
    },
    class: {
        type: String,
    },
});

const style = computed(() => handleBackground(props.image));
</script>
