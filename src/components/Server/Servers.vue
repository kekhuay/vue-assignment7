<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li class="list-group-item" v-for="server in servers" :key="server.id" @click="showDetail(server.id)">
                Server #{{ server.id }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                servers: [
                    { id: 1, status: 'Normal' },
                    { id: 2, status: 'Critical' },
                    { id: 3, status: 'Unknown' },
                    { id: 4, status: 'Normal' },
                ]
            };
        },
        methods: {
            showDetail(id) {
                var server = this.servers.filter((s) => s.id === id)[0];
                this.$emit('serverSeleted', server);
            }
        }
    }
</script>

<style>

</style>
