<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../layoutHelper";

/**
 * Resolve urls from frontmatter and append with the base url
 */
function resolveAssetUrl(url: string) {
    if (url.startsWith("/")) return import.meta.env.BASE_URL + url.slice(1);
    return url;
}

const props = defineProps({
    image: {
        type: String,
        default:
            "https://diagram-pins.s3.ap-southeast-2.amazonaws.com/2022-03/bg-01.svg",
    },
    class: {
        type: String,
    },
});

// const style = computed(() => handleBackground(props.image));
const style = computed(() => {
    return {
        backgroundImage: `url("${resolveAssetUrl(props.image)}")`,
        backgroundRepeat: "no-repeat",
        backgroundPosition: "right",
        backgroundSize: "contain",
    };
});
</script>

<template>
    <div class="grid grid-cols-2 w-full h-full">
        <div class="slidev-layout default" :class="props.class">
            <slot />
        </div>
        <div class="w-full w-full" :style="style" />
    </div>
</template>
