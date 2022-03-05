<template>
    <div>
        <ul v-if="taskFilter.length">
            <li v-for="task in taskFilter" :key="task.id">{{ task.title }}</li>
        </ul>
        <p v-else>Não existe tarefas ativas!</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tasks: [
                { id: 1, title: 'Caminhar', status: false },
                { id: 2, title: 'Malhar', status: true },
                { id: 3, title: 'Estudar', status: false },
                { id: 4, title: 'Trabalhar', status: false },
            ],
        };
    },
    computed: {
        taskFilter() {
            return this.tasks.filter((e) => e.status);
        },
    },
};
</script>

<style></style>
