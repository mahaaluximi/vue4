<template>
    <h2>Manage Goals</h2>
    <div>
        <input type="text" ref="goalInput">
        <button @click="validateInput">Add Goal</button>
    </div>
    <teleport to="body">
        <error-modal v-if="isInvalid">
            <h2>Invalid Input</h2>
            <p>Please enter at least a few characters.</p>
            <button @click="confirmError">Confirm</button>
        </error-modal>
    </teleport>
</template>

<script>
import ErrorModal from './ErrorModal.vue';
export default {
    components: {
        ErrorModal,
    },
    data() {
        return {
            isInvalid: false,
        };
    },
    methods:{
        validateInput() {
            if (this.$refs.goalInput.value === '') {
                this.isInvalid = true;
            } else {
                this.isInvalid = false;
            }
        },
        confirmError() {
            this.isInvalid = false;
        }
    }
};

</script>