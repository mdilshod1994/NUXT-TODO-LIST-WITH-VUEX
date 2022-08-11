<template>
    <div :class="`task ${task.done ? 'is-complete' : ''}`">
        <div class="content">
            {{ task.content }}
        </div>
        <div class="buttons">
            <button @click="toggleTask(task)">
                {{ task.done ? 'Undo' : 'Done' }}
            </button>
            <button class="delete" @click="deleteTask(task)">
                Delete
            </button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['task'],
    methods: {
        toggleTask(task) {
            this.$store.commit('TOGGLE_TASK', task)
        },
        deleteTask(task) {
            this.$store.commit('REMOVE_TASK', task)
        }
    }
}
</script>