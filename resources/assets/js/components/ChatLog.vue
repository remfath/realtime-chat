<template>
    <div class="chat-log">
        <chat-message v-for="(message, idx) in messages" :message="message" :key="idx"></chat-message>
    </div>
</template>

<script>

    export default {
        data() {
            return {}
        },
        props: ['messages']
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-log .chat-message:nth-child(even) {
        background: #ccc;
    }
</style>