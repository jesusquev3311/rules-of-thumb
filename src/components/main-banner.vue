<template>
    <section id="main-banner">
        <v-container>
            <v-row>
                <v-col :md="6">
                    <div class="box-wrapper">
                        <div class="box-body">
                            <span>What's your opinion</span>
                            <h1>Pope Francis?</h1>
                            <p>He's talking tough on clergy sexual abuse, but is he just another
                                papal pervert protector? (thumbs down) or a true pedophile punishing pontiff? (thumbs up)
                            </p>
                            <span class="more-info"><a href="#">More information</a></span>
                            <span class="verdict">What's Your Verdict?</span>
                        </div>
                        <div class="thumbs-wrapper">
                            <v-row>
                                <v-col :md="6">
                                    <div class="thumb bg-green thumb-left">
                                        <v-icon>fas fa-thumbs-up</v-icon>
                                    </div>
                                </v-col>
                                <v-col :md="6">
                                    <div class="thumb bg-orange thumb-right">
                                        <v-icon>fas fa-thumbs-down</v-icon>
                                    </div>
                                </v-col>
                            </v-row>
                        </div>
                    </div>
                </v-col>
            </v-row>
        </v-container>
        <div class="closing-wrapper">
            <v-row>
                <v-col :md="4">
                    <span class="closing-left">Closing In</span>
                </v-col>
                <v-col :md="8">
                    <span class="closing-right"><strong>22</strong> days</span>
                </v-col>
            </v-row>
        </div>
    </section>
</template>

<script>
    export default {
        name: "main-banner"
    }
</script>

<style lang="scss" scoped>
    #main-banner{
        background-image: url("../assets/img/pope.jpg");
        background-position: center;
        background-size: cover;
        display: block;
        width: 100%;
        min-height: 744px;
        padding-top: 150px;
        position: relative;
        .box-wrapper{
            .box-body{
                background-color: #333;
                padding: 30px;
            }
        }
        .thumbs-wrapper{
            .thumb{
                text-align: center;
                color:#fff;
                padding: 20px;
                cursor: pointer;
                &.thumb-left{
                    margin: -12px -15px 0 0;
                }
                &.thumb-right{
                    margin: -12px 0 0 -15px;
                }
                i{
                    color: #fff;
                }
            }
        }
        .closing-wrapper{
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            .closing-left{
                background-color: rgba(0,0,0,0.3);
                display: block;
                text-align: right;
                color: white;
                padding: 10px 5px;
                margin-right: -12px;
            }
            .closing-right{
                background-color: rgba(255,255,255,0.3);
                display: block;
                padding: 10px 5px;
                margin-left: -12px;
            }
        }
    }
</style>
