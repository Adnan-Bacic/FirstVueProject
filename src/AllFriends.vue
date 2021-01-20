<!--Template-->
<template>
    <div id="all-friends">
        <h2>All Friends</h2>
        <div v-for="(friend, index) in friendsAll" v-bind:key="index">
            <span v-on:click="unfriend(friend.name)">{{ friend.name }}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AllFriends',
    props: ['friendsAll'],
    data(){
        return{
            
        }
    },
    methods: {
        unfriend(name){
            this.$emit('delete', { name : name})
        }
    }
}
</script>

<style scoped>

</style>