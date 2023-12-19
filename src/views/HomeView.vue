<template>
    <div class="home">
        <h2 ref="appTitleRef">{{ appTitle }}</h2>
        <h3>{{ counter.title }}</h3>
        <div>
            <button @click="counter.decreaseCounter(2)" class="btn">--</button>
            <button @click="counter.decreaseCounter(1)" class="btn">-</button>
            <span class="counter">{{ counter.count }}</span>
            <button @click="counter.increaseCounter(1)" class="btn">+</button>
            <button @click="counter.increaseCounter(2)" class="btn">++</button>
        </div>
        <p>This counter is {{ counter.oddOrEven }}</p>

        <div class="edit">
            <h4>Edit counter title:</h4>
            <input v-model="counter.title" type="text" v-autofocus />
        </div>
    </div>
</template>

<script setup>
/*
  imports
*/

import {
    ref,
    // onBeforeMount,
    onMounted,
    // onBeforeUnmount,
    // onUnmounted,
    // onActivated,
    // onDeactivated,
    // onBeforeUpdate,
    // onUpdated,
} from "vue";
import { useCounterStore } from "@/stores/counter";
import { vAutofocus } from "@/directives/vAutofocus.js";

// const counter = ref(0),
//     counterTitle = ref("My Counter");

/*
  app title
*/

const appTitle = "My Amazing Counter App";

const appTitleRef = ref(null);

onMounted(() => {
    console.log(`The app title is ${appTitleRef.value.offsetWidth}px wide`);
});

/*
  counter
*/
// const { counterData, oddOrEven, increaseCounter, decreaseCounter } =
//     useCounter();
const counter = useCounterStore();

/*
  hooks
*/

// onBeforeMount(() => {
//     console.log("onBeforeMouont");
// });

// onMounted(() => {
//     console.log("onMounted");
// });

// onBeforeUnmount(() => {
//     console.log("onBeforeUnmount");
// });

// onUnmounted(() => {
//     console.log("onUnmounted");
// });

// onActivated(() => {
//     console.log("onActivated");
// });

// onDeactivated(() => {
//     console.log("onDeactivated");
// });

// onBeforeUpdate(() => {
//     console.log("onBeforeUpdate");
// });

// onUpdated(() => {
//     console.log("onUpdated");
// });
</script>

<!--
<script>
import { ref } from "vue";

export default {
    setup() {
        const counter = ref(0);

        const increaseCounter = () => {
            counter.value++;
        };

        const decreaseCounter = () => {
            counter.value--;
        };

        return { counter, increaseCounter, decreaseCounter };
    },
};
</script> -->

<!--
<script>
export default {
    data() {
        return {
            counter: 0,
        };
    },
    methods: {
        increaseCounter() {
            this.counter++;
        },
        decreaseCounter() {
            this.counter--;
        },
    },
    directives: {
        autoFocus: {
            mounted(el) {
                el.focus();
            },
        },
    },
};
</script> -->

<style>
.home {
    text-align: center;
    padding: 20px;
}

.btn,
.counter {
    font-size: 40px;
    margin: 10px;
}

.edit {
    margin-top: 60px;
}
</style>
