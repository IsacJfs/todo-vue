<script setup>
const props = defineProps(['tarefas'])
</script>
<template>
    <ul class="list-group mt-4" v-if="props.tarefas.length > 0">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <div class="row mt-5" v-else>
        <p class="text-center fs-3" >Não existem tarefas a serem exibidas</p>
    </div>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>