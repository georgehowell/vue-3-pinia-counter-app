<template>
    <div class="post-detail">
        <h1>This is a post page</h1>
        <p>
            Display the content of post with id of {{ $route.params.id }} here!
        </p>
        <div>
            <button @click="showPostId">Show Post ID</button>
        </div>
        <div>
            <button @click="goHomeIn3Seconds">Go Home in 3 seconds</button>
        </div>
        <div>
            <button @click="goToFirstPost">Go To First Post</button>
        </div>
        <p><router-link to="/posts">&lt; Back</router-link></p>
    </div>
</template>

<script setup>
import { useRoute, useRouter } from "vue-router";

const route = useRoute();
const router = useRouter();

const showPostId = () => {
    alert(`The id of this post is: ${route.params.id}`);
};

const goHomeIn3Seconds = () => {
    setTimeout(() => {
        router.push({ name: "home" });
    }, 3000);
};

const goToFirstPost = () => {
    router.push({
        name: "postDetail",
        params: {
            id: "id1",
        },
    });
};
</script>
