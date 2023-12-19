<template>
    <div class="modals">
        <h1>Modals</h1>
        <div>
            <label>Show dark modals?</label>
            <input type="checkbox" v-model="showDarkModals" />
        </div>
        <button @click="showModal = true">Show modal</button>
        <component
            v-model="showModal"
            title="My modal title (via prop)"
            :is="showDarkModals ? ModalDark : Modal"
        >
            <!-- <template #title>My new title</template> -->
            <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                Reiciendis exercitationem corporis deleniti a totam, enim
                dignissimos doloribus? Nam modi quo facere consequatur,
                obcaecati recusandae adipisci, quidem distinctio minus, fugit
                reprehenderit?
            </p>
        </component>
    </div>
</template>

<script setup>
import { ref } from "vue";
import Modal from "../components/Modal.vue";
import ModalDark from "../components/ModalDark.vue";

// modal
const showDarkModals = ref(false);
const showModal = ref(false);
</script>
