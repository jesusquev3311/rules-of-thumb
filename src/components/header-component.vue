<template>
    <header>
        <v-container>
            <v-row>
               <v-col :md="6">
                   <div class="logo">
                       <span class="text-logo">Rule of Thumb.</span>
                   </div>
               </v-col>
               <v-col :md="6">
                   <nav>
                       <ul>
                           <li><a href="#">Past Trials</a></li>
                           <li><a href="#">How It Works</a></li>
                           <li class="login-wrapper"><a href="#">Log In</a>/<a href="#">Sign Up</a></li>
                           <li><a href="#"><v-icon>fas fa-search</v-icon></a></li>
                       </ul>
                   </nav>
               </v-col>
            </v-row>
        </v-container>
    </header>
</template>

<script>
    export default {
        name: "header"
    }
</script>

<style lang="scss" scoped>
    header{
        padding: 30px 0;
        background-color: #333;
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
                        padding: 5px 20px;
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
    }
</style>
