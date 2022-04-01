<template>
    <div class="slidev-layout content" :class="class" :style="style">
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
        default:
            "https://diagram-pins.s3.ap-southeast-2.amazonaws.com/2022-03/bg-04.svg",
    },
    class: {
        type: String,
    },
});

const style = computed(() => handleBackground(props.image));
</script>
