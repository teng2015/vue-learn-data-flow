<template>
    <div>
        <h3>{{ clientid }}</h3>
        <div class="client">
            <ul class="msg-box">
                <li v-for="msg in messages">
                    <label>{{ msg.sender }} : </label>
                    {{ msg.text }}
                </li>
            </ul>
            <div class="input-box">
                <input type="text" v-model="text" @keyup.enter="sendMessage" placeholder="Enter a message, then hit [enter]">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Client',
        data () {
            return {
                text: '',
                messages: store.state.messages
            }
        },
        props: ['clientid'],
        methods: {
            sendMessage () {
                if (!this.text) return false

                store.newMessage({
                    text: this.text,
                    sender: this.clientid
                })

                this.resetInput()
            },
            resetInput () {
                this.text = ''
            }
        }
    }
</script>

<style>
.client {
    position: relative;
    border: 1px solid #ccc;
    background-color: #fff;
}
.client .msg-box {
    height: 300px;
    overflow: auto;
    list-style: none;
    padding: 5px 8px;
}
.client .msg-box li {padding: .2em .5em;text-align: left;}
.client .msg-box label {font-weight: 700;}
.client .input-box {border-top: 1px solid #ccc; padding: 6px 12px;}
.client input {width: 100%; padding: 6px 10px;}
</style>
