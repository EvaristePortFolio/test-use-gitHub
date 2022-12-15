<template>
    <div class="user_profile-item" @click="favoriteTwoot(twoot.id)">
       <div class="user_profile-twoot">
        <div class="twoot_user-id">
              @{{username}}
        </div>
        <div class="twoot_user-content">
            {{twoot.content}}
        </div>
       </div>
    </div>

</template>

<script>
export default{
    name:"twootItem",
    props:{
        username: {
            type:String,
            required:true
        },
        twoot:{
            type:Object,
            required:true
        }
    },
    methods: {
        favoriteTwoot(id){
            this.$emit('favorite',id)
        }
    
    }

}
</script>

<style>
 .user_profile-item{
    padding-bottom: 20px;
    background-color: white;
    border-radius: 5px;
    border: 1px solid #DFE3E8;
    box-sizing: border-box;
    cursor: pointer;
    transition: all 0.25s ease;
    width: 200px;
    margin-left: 30px;
    margin-top: 1px;
 }

 .user_profile-item:hover{
    transform: scale(1.1 ,1.1);
 }

</style>