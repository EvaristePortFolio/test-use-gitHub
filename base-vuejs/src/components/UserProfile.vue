<template>
    <div class="container">
        <div class="user_profile-username">
            The Number of Followers is : {{ followers }} <br>
            {{ fullName }}
            <button @click="followUsers">
                Follow
            </button>
            <div class="user_profile-admin" v-if="user.isAdmin">
                Admin
            </div>
            <div class="user_profile-admin" v-else>
                Not Admin
            </div>
        </div>
        <div class="user_profile-content">
            <ol>
                <twootItem v-for="twott in twotts" :key="twott.id" :username="user.username" :twoot="twott"  @favorite="togglefavor"/>
            </ol>
        </div>
    </div>
</template>

<script>
import twootItem from "./twootItem.vue";

export default {
    name: 'UserProfile',
    components: { twootItem },
    data() {
        return {
            followers: 0,
            user: {
                username: 'evariste',
                firstname: 'tcheuffa',
                lastname: 'nouaga',
                email: 'evaristenouaga@gmail.com',
                isAdmin: false
            },
            twotts: [
                { id: 1, content: "first content is primary full" },
                { id: 2, content: "second content is primary duesty due to lack of amnestty international finish blink blink blink" },

            ]
        }
    },
    computed: {
        fullName() {
            return `${this.user.username} ${this.user.firstname}`
        }
    },
    methods: {
        followUsers() {
            this.followers++
        },
        togglefavor(id){
            console.log('@@@@favourite',id);
        } 
    },
    mounted() {
        this.followUsers()
    }
}
</script>

<style>

.container {
    display: flex;
    flex-direction: inline;
}

.user_profile-username {
    background: greenyellow;
    height: 150px;
    border-radius: 5px;
    margin-top: 10px;
    padding-top: 50px;
    padding-right: 50px;
    padding-left: 50px;
    padding-bottom: 50px;
    width: 150px;

}

.user_profile-admin {
    background: red;
    color: white;
    border-radius: 5px;
    margin-top: 10px;
    margin: auto;
    margin-top: 10px;

}

.user_profile-content {}
</style>