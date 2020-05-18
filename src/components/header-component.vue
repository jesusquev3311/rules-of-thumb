<template>
    <header class="header-component">
        <v-container>
            <v-row>
               <v-col :md="6">
                   <div class="logo">
                       <a href="/">
                        <span class="text-logo">Rule of Thumb.</span>
                       </a>
                   </div>
               </v-col>
               <v-col :md="6" >
                   <nav class="d-none d-md-block">
                       <ul>
                           <li><a href="#">Past Trials</a></li>
                           <li><a href="#">How It Works</a></li>
                           <li class="login-wrapper"><a href="#">Log In</a>/<a href="#">Sign Up</a></li>
                           <li><a href="#"><v-icon>fas fa-search</v-icon></a></li>
                       </ul>
                   </nav>
                   <v-icon id="mobile-menu-icon" class="d-inline-block d-md-none " @click="activateMenu">fas fa-bars</v-icon>
               </v-col>
            </v-row>
        </v-container>
    </header>
</template>

<script>
    export default {
        name: "header",
        data(){
            return{}
        },
        methods:{
            activateMenu(){
                this.$emit('mobile');

            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../assets/sass/colors";
    header{
        padding: 10px 0 0 0;
        background-color: rgba(51,51,51,0.1);
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        z-index: 999;
        nav{
            ul{
                padding: 0;
                margin: 0;
                li{
                    display: inline-block;
                    color: #fff;
                    a{
                        text-decoration: none;
                        color: #fff;
                        font-size: 20px;
                        padding: 0 25px;
                        transition: all .1s;
                        &:hover{
                            color: $green;
                        }
                        i{
                            &:before{
                                font-weight: lighter;
                                color: white;
                            }
                        }
                    }
                    &.login-wrapper{
                        a{
                            padding: 0;
                            margin: 0 5px;
                        }
                    }
                }
            }
        }
        #mobile-menu-icon{
            float: right;
            margin-right: 20px;
            color: #fff;
            cursor: pointer;
        }
    }
</style>
