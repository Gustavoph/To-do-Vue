<template>
    <div class="task-grid">
        <template v-if="tasks.length > 0">
            <Task v-for="(task, i) in tasks" 
            @taskDeleted="$emit('taskDeleted', i)"
            @taskCompleted="$emit('taskCompleted', i)"
            :key="task.name" 
            :task="task"></Task>
        </template>
        <template v-else>
            <div class="no-task">
                <h2>Nenhuma Tarefa cadastrada</h2>
            </div>
        </template>
    </div>
</template>

<script>
import Task from './Task.vue';
export default {
    components: { Task },
    props: {
        tasks:{
            type: Array,
            required: true
        }
    },
    
}
</script>

<style scoped>
    .task-grid {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
    }
    .task-grid .task{
        margin: 10px;
    }
    .no-task{
        color: #aaa;
        font-size: 1.7rem;
    }
</style>