<template>
    <div class="add-section">
        <v-container>
            <div class="add">
                <v-row>
                    <v-col :md="3">
                        <span class="add-top-text"></span>
                        <span class="add-bottom-text"></span>
                    </v-col>
                    <v-col :md="9">
                        <p class="add-text">
                            Rule of Thumb is a crowd sourced court of public opinion where anyone and everyne can speak freely<br>
                            It's easy. You share your opinion, we analyze and put the data in a public report.
                        </p>
                        <span class="add-close">X</span>
                    </v-col>
                </v-row>
            </div>
        </v-container>
    </div>
</template>

<script>
    export default {
        name: "add-component"
    }
</script>

<style scoped>

</style>
