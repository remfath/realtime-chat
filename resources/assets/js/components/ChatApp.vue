<template>
    <div class="col-md-8 col-md-offset-2">
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
                messages: [],
                userInRooms: []
            }
        },
        methods: {
            addMessage(message) {
                this.messages.push(message);
                axios.post('/messages', message).then(response => {
                    console.log(response.data);
                });
            }
        },
        components: {
            ChatLog,
            ChatComposer
        },
        created() {
            axios.get('/messages').then(response => {
                this.messages = response.data;
            });

            Echo.join('chat-room')
                .here()
                .joining()
                .leaving()
                .listen('MessagePosted', (e) => {
                    console.info(e);
                    this.messages.push({
                        message: e.message.message,
                        user: e.user
                    });
                });
        }
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .panel-body {
        padding: 15px 0;
    }
</style>