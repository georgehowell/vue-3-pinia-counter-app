<template>
    <teleport to=".modals-container">
        <div class="modal" v-if="modelValue">
            <h1>{{ title }}</h1>
            <slot />
            <!-- <pre>{{ $slots.title() }}</pre> -->
            <button @click="$emit('update:modelValue', false)">
                Hide modal
            </button>
            <div>Username is: {{ userData.userName }}</div>
        </div>
    </teleport>
</template>

<script setup>
// import { useSlots } from "vue";
import { inject } from "vue";

// props
const props = defineProps({
    modelValue: {
        type: Boolean,
        default: false,
    },
    title: {
        type: String,
        default: "No title specified",
    },
});
// console.log(props.title);

// emits
const emit = defineEmits(["update:modelValue"]);

// handle button click
// const handleButtonClick = () => {
//     emit("update:modelValue", false);
// };

// const slots = useSlots();

// console.log(slots.title());

// user data
const userData = inject("userData");
</script>

<style scoped>
.modal {
    background: beige;
    padding: 10px;
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
}
</style>
