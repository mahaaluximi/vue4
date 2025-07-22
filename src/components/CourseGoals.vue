<template>
    <ul>
        <li v-for="goal in goals" :key="goal">
            <!-- scoped goal - Passing the loop goal to the invoking components, here "item" is just a name, it can be anything -->
            <!-- <slot v-bind:item="goal"></slot> -->
            <slot :item="goal" addn-Info="...more info"></slot>
            <!-- {{ goal }} -->
        </li>
    </ul>
</template>

<script>
export default {
    data() {
        return {
            goals: ['Finish the course', 'Learn Vue'],
        };
    },
};
</script>   