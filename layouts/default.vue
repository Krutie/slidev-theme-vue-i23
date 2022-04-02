<template>
    <div class="slidev-layout default" :class="class" :style="style">
        <div class="mx-auto w-full">
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
