<template>
    <div class="chat-message">
        <p class="message-user">{{ message.user.name }}</p>
        <p class="message-content">{{ message.message }}</p>
    </div>
</template>

<script>

    export default {
        data() {
            return {}
        },
        props: ['message']
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-message {
        padding: 5px 15px;
    }

    .message-user {
        font-size: 90%;
        margin: 5px;
    }

    .message-content {
        padding: 5px 10px;
        background-color: #dff0d8;
        border-color: #d6e9c6;
        color: #3c763d;
        border-radius: 3px;
    }
</style>