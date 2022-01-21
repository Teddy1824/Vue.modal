<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{promotion: theme === 'promotion'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['header', 'text', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close');
        }
    },
}
</script>

<style>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: darkolivegreen;
    border-radius: 10px;
}

.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
}

.modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}

.modal.promotion {
    background: crimson;
    color: white;
}

.modal.promotion h1 {
    color: white;
}

.modal.promotion .actions {
    color: white;
}

.modal.promotion .actions a {
    color:  white;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}

h1 {
    color: black;
    border: none;
    padding: 0;
}

p {
    color: white;
}

</style>