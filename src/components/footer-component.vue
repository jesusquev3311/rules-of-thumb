<template>
    <footer>
        <v-container>
            <div class="footer-wrapper">
                <v-row>
                    <v-col cols="12" :xs="12" :sm="12" :md="8">
                        <nav class="footer-nav">
                            <ul>
                                <li><a href="#">Terms and Conditions</a></li>
                                <li><a href="#">Privacy Policy</a></li>
                                <li><a href="#">Contact Us</a></li>
                            </ul>
                        </nav>
                    </v-col>
                    <v-col cols="12" :xs="12" :sm="12" :md="4">
                        <ul class="social-links">
                            <li>Follow Us</li>
                            <li><a href="https://facebook.com" target="_blank"><v-icon> fab fa-facebook-square</v-icon></a></li>
                            <li><a href="https://twitter.com" target="_blank"><v-icon> fab fa-twitter</v-icon></a></li>
                        </ul>
                    </v-col>
                </v-row>
            </div>
        </v-container>
    </footer>
</template>

<script>
    export default {
        name: "footer-component"
    }
</script>

<style lang="scss" scoped>
    @import "../assets/sass/colors";
    footer{
        .footer-wrapper{
            padding: 20px 0;
            border-top: 1px dashed;
            ul{
                padding-left: 0;
                list-style: none;
                li{
                    display: inline-block;
                    a{
                        text-decoration: none;
                        color: #333;
                        margin-right: 10px;
                        font-weight: 300;
                        transition: all .1s;
                        font-size: 14px;
                        &:hover{
                            color: $green;
                            i{
                                color: $green;
                            }
                        }
                    }
                }
                &.social-links{
                    display: flex;
                    justify-content: flex-end;
                    align-content: center;
                    align-items: center;
                    li{
                        a{
                            margin-left: 20px;
                        }
                    }
                }
            }
        }
    }
    /*responsive*/
    /* mobile */
    @media only screen and (max-width: 600px){
        footer{
            .footer-wrapper{
                ul{
                    text-align: center;
                    &.social-links{
                        justify-content: center;
                    }
                }
            }
        }
    }
    /* small tablet */
    @media only screen and (min-width: 601px) and (max-width: 920px){
        footer{
            .footer-wrapper{
                ul{
                    text-align: center;
                    &.social-links{
                        justify-content: center;
                    }
                }
            }
        }
    }
</style>
