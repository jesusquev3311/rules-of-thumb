<template>
    <section class="add-section">
        <v-container>
            <div class="add">
                <v-row>
                    <v-col cols="12" :xs="12" :sm="12" :md="3">
                        <span class="add-top-text">Speak Out. Be Heard.</span>
                        <span class="add-bottom-text">Be Counted</span>
                    </v-col>
                    <v-col cols="12" :xs="12" :sm="12" :md="9">
                        <p class="add-text">
                            Rule of Thumb is a crowd sourced court of public opinion where anyone and everyne can speak freely<br>
                            It's easy. You share your opinion, we analyze and put the data in a public report.
                        </p>
                        <span class="add-close">X</span>
                    </v-col>
                </v-row>
            </div>
        </v-container>
    </section>
</template>

<script>
    export default {
        name: "add-component"
    }
</script>

<style lang="scss" scoped>
    .add-section{
        padding: 25px 0 10px 0;
        .add{
            background-color: #ebebeb;
            padding: 20px 25px;
            position: relative;
            .row{
                align-items: center;
                span{
                    display: block;
                    color: #333333;
                    &.add-top-text{
                        font-size: 18px;
                        line-height: 25px;
                    }
                    &.add-bottom-text{
                        font-weight: 700;
                        font-size: 31px;
                        line-height: 37px;
                    }
                }
                .add-text{
                    font-size: 16px;
                    line-height: 22px;
                    display: inline-flex;
                }
                .add-close{
                    display: inline-flex;
                    justify-content: center;
                    font-size: 30px;
                    font-weight: 400;
                    position: absolute;
                    right: 28px;
                    top: 30%;
                    color:#bdbdbd;
                }
            }
        }
    }
</style>
