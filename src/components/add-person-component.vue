<template>
    <section id="add-person-section">
        <v-container>
            <div class="add-person-wrapper">
                <v-row>
                    <v-col :md="8">
                        <p class="add-person-text">Is there anyone else you would want us to add?</p>
                    </v-col>
                    <v-col :md="4">
                        <button type="button">Submit a Name</button>
                    </v-col>
                </v-row>
            </div>
        </v-container>
    </section>
</template>

<script>
    export default {
        name: "add-person-component"
    }
</script>

<style lang="scss" scoped>
    #add-person-section{
        padding: 10px 0;
        .add-person-wrapper{
            .row{
                align-items: center;
                .add-person-text{
                    font-size: 26px;
                    line-height: 30px;
                    font-weight: 300;
                }
                button{
                    background-color: transparent;
                    color: #333333;
                    font-weight: 400;
                    border: 2px solid #333;
                    border-radius: 0;
                    box-shadow: none;
                    padding: 10px 30px;
                    font-size: 22px;
                    transition: all .1s;
                    &:hover{
                        background-color: #333333;
                        color: white;
                    }
                }
            }
        }
    }
</style>
