<template>
    <div class="chat-composer">
        <textarea v-model="message" @keyup.enter="sendMessage" class="composer-input">
    </textarea>
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
                if (this.message) {
                    this.$emit('sent', {
                        content: this.message,
                        user: 'Jack'
                    });
                    this.message = '';
                }
            }
        }
    }
</script>

<style type="text/scss" lang="scss" scoped>
    .chat-composer {
        border-top: 1px solid #d3e0e9;
    }

    .composer-input {
        width: 100%;
        height: 150px;
        padding: 15px;
        border: none;
        resize: none;
        overflow: auto;
        outline: none;
    }
</style>