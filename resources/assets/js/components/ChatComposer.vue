<template>
    <div class="chat-composer">
        <input type="text" placeholder="Enter your message" v-model="message" @keyup.enter="sendMessage">
        <button class="btn btn-primary" @click="sendMessage">Send</button>
    </div>
</template>

<script>

    export default {
        data() {
            return {
                message: ''
            }
        },
        methods: {
            sendMessage() {
                this.$emit('sent', {
                    content: this.message,
                    user: 'Jack'
                });
                this.message = '';
            }
        }
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-composer {
        display: flex;
        input {
            flex: 1 auto;
        }
        button {
            border-radius: 0;
        }
    }
</style>