<template>
    <div class="chat-app">
        <div class="panel panel-primary">
            <div class="panel-heading">
                <h4>Chat Room</h4>
            </div>
            <div class="panel-body">
                <chat-log :messages="messages"></chat-log>
            </div>
            <chat-composer @sent="addMessage"></chat-composer>
        </div>
    </div>
</template>

<script>
    import ChatLog from './ChatLog.vue';
    import ChatComposer from './ChatComposer.vue';

    export default {
        data() {
            return {
                messages: []
            }
        },
        methods: {
            addMessage(message) {
                this.messages.push(message);
            }
        },
        components: {
            ChatLog,
            ChatComposer
        }
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-app {
        width: 900px;
        margin: 50px auto;
        .panel-body {
            padding: 15px 0;
        }
    }
</style>