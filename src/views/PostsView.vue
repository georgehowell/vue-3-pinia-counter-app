<template>
    <div class="posts">
        <h1>Posts</h1>

        <ul>
            <li v-for="post in posts" :key="post.id">
                <RouterLink :to="`/postDetail/${post.id}`">{{
                    post.title
                }}</RouterLink>
            </li>
        </ul>

        <textarea v-autofocus />
        <div>
            <button
                @click="counter.increaseCounter(1)"
                class="counter-button"
                :class="{ yellow: counter.oddOrEven === 'odd' }"
            >
                {{ counter.count }}
            </button>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";
import { vAutofocus } from "@/directives/vAutofocus.js";
import { useCounterStore } from "@/stores/counter";

// posts
const posts = ref([
    { id: "id1", title: "Post 1" },
    { id: "id2", title: "Post 2" },
    { id: "id3", title: "Post 3" },
]);

// counter button
// const { counterData, increaseCounter, oddOrEven } = useCounter();
const counter = useCounterStore();
</script>

<style scoped>
ul {
    margin-bottom: 30px;
}

.counter-button {
    font-size: 60px;
    background: pink;
    width: 100%;
}

.counter-button.yellow {
    background: yellow;
}
</style>
