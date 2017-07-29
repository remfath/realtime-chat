<template>
    <div class="chat-log">
        <chat-message v-for="(message, idx) in messages" :message="message" :key="idx"></chat-message>
    </div>
</template>

<script>
    import ChatMessage from './ChatMessage.vue';

    export default {
        data() {
            return {}
        },
        props: ['messages'],
        components: {
            ChatMessage
        }
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-log {
        min-height: 350px;
    }
</style>