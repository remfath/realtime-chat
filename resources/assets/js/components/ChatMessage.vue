<template>
    <div class="chat-message">
        <p>{{ message.user }}</p>
        <p class="alert alert-success">{{ message.content }}</p>
    </div>
</template>

<script>

    export default {
        data() {
            return {

            }
        },
        props: ['message']
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-message {
        padding: 5px 15px;
    }
</style>