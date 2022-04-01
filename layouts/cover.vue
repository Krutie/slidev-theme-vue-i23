<template>
    <div class="slidev-layout cover" :class="class" :style="style">
        <div class="my-auto w-full">
            <slot />
        </div>
        <div class="abs-tr m-6 flex gap-2">
            <a
                href="https://twitter.com/KrutiePatel"
                target="_blank"
                alt="GitHub"
                class="
                    text-xl
                    icon-btn
                    opacity-50
                    !border-none
                    !hover:text-white
                "
            >
                <carbon-logo-twitter />
            </a>
            <a
                href="https://github.com/Krutie"
                target="_blank"
                alt="GitHub"
                class="
                    text-xl
                    icon-btn
                    opacity-50
                    !border-none
                    !hover:text-white
                "
            >
                <carbon-logo-github />
            </a>
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
