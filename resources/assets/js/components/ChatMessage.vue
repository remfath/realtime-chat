<template>
    <div class="chat-message">
        <p>{{ message.content }}</p>
        <small>{{ message.user }}</small>
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

</style>