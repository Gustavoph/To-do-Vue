<template>
    <div class="new-task">
        <input v-model="name" @keydown.enter="add" type="text"
        class="form-element" placeholder="Nova Tarefa?">
        <button class="form-element" @click="add">+</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: ''
        }
    },
    methods:{
        add(){
            this.$emit('taskAdded', { name: this.name, pending: true})
            this.name = ''
        }
    }
}
</script>

<style>
    .new-task {
        margin: 35px;
    }

    .form-element{
        outline: none;
        font-size: 2rem;
        border: 1px solid #fff;
        padding: 5px 10px 8px;
        color: white;
    }

    input.form-element {
        width: 500px;
        background-color: #fff2;
        border-radius: 8px 0px 0px 8px;
    }

    button.form-element {
        border-left: none;
        background: #2196f3;
        border-radius: 0px 8px 8px 0px;
    }

</style>
