<template>
    <section id="main-banner">
        <v-container>
            <v-row>
                <v-col :md="6">
                    <div class="box-wrapper">
                        <div class="box-body">
                            <span>What's your opinion</span>
                            <h1>{{ person[4].name }}?</h1>
                            <p>{{ person[4].description }}</p>
                            <span class="more-info"><v-icon> fab fa-wikipedia-w</v-icon><a href="#">More  information</a></span>
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
                    <span class="closing-left">Closing In <span class="arrow-right-black-alpha"></span></span>
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
        name: "main-banner",
        props:['person']
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
        padding: 150px 0;
        position: relative;
        .box-wrapper{
            max-width: 497px;
            position: relative;
            .box-body{
                padding: 30px;
                color: white;
                position: relative;
                background-color: rgba(255,255,255,0.15);
                z-index: 0;
                &:before{
                    content: '';
                    position: absolute;
                    width: 100%;
                    height: 100%;
                    top: 0;
                    left: 0;
                    /* Add the blur effect */
                    filter: blur(1px);
                    -webkit-filter: blur(1px);
                    background-color: rgba(0,0,0,0.5);
                    z-index: 0;
                }
                h1{position: relative}
                span{
                    color: white;
                    font-size: 13px;
                    line-height: 18px;
                    display: block;
                    position: relative;
                    &.more-info{
                        margin-bottom: 40px;
                        i{
                            color: white;
                            font-size: 13px;
                            margin-right: 5px;
                        }
                        a{
                            color: white;
                        }
                    }
                    &.verdict{
                        font-size: 22px;
                        line-height: 25px;
                        font-weight: 700;
                        margin-bottom: 25px;
                    }
                }
                p{
                    font-size: 19px;
                    line-height: 32px;
                    margin-bottom: 25px;
                    position: relative;
                }
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
                    font-size: 37px;
                    color: #fff;
                }
            }
        }
        .closing-wrapper{
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            .col{
                padding: 0 12px;
                .closing-left{
                    background-color: rgba(0,0,0,0.2);
                    display: flex;
                    justify-content: flex-end;
                    align-items: center;
                    color: white;
                    margin-right: -12px;
                    height: 100%;
                    font-size: 13px;
                    font-weight: 700;
                    padding:  10px;
                    position: relative;
                    .arrow-right-black-alpha{
                        position: absolute;
                        top: 33%;
                        right: -10px;
                    }
                }
                .closing-right{
                    background-color: rgba(255,255,255,0.3);
                    display: flex;
                    align-items: center;
                    padding: 10px 20px;
                    margin-left: -12px;
                    height: 100%;
                    font-size: 22px;
                    color: #333;
                    strong{
                        margin-right: 5px;
                    }
                }
            }
        }
    }
</style>
