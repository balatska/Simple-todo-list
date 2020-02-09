<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox" v-on:change="todo.completed = !todo.completed">
            <strong>{{ index + 1 }}</strong>
            {{ todo.title }}
        </span>
        <button class="rm" v-on:click="$emit('remove-todo', todo.id)" >&times;</button>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        },
        index: Number
    }
}
</script>

<style scoped lang="scss">
    li {
        border: 2px solid brown;
        display: flex;
        justify-content: space-between;
        padding: 20px;
        margin: 10px;
        border-radius: 3px;
    }

    .rm {
        background-color: #973131;
        border: none;
        outline: none;
        color: #ffffff;
        border-radius: 3px;
        font-weight: bold;

        &:hover {
            cursor: pointer; 
        }
    }

    .done {
        text-decoration: line-through;
    }
</style>