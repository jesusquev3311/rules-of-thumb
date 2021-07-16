<template>
    <article class="person">
        <div class="person-wrapper" :style="{'background-image':'url(' + person.backgroundImg + ')'}">
            <div class="person-body">
                <v-row>
                    <v-col cols="12" :xs="12" :sm="12" :md="1" style="padding-bottom: 0">
                        <span class="votes-icon">
                           <v-icon v-if="person.votes.up > person.votes.down || person.votes.total === 0 || person.votes.up === person.votes.down" class="person-thumb green-bg">fas fa-thumbs-up</v-icon>
                           <v-icon v-else class="person-thumb orange-bg">fas fa-thumbs-down</v-icon>
                        </span>
                    </v-col>
                    <v-col cols="12" :xs="12" :sm="12" :md="11" style="padding-bottom: 0">
                        <h3>{{ person.name }}</h3>
                    </v-col>
                </v-row>
                <v-row>
                    <v-col cols="12" :xs="12" :sm="12" :md="1">

                    </v-col>
                    <v-col cols="12" :xs="12" :sm="12" :md="11">
                        <span class="person-date"><strong>{{ person.date }} month ago</strong> in {{ person.category }}</span>
                        <p class="person-text">{{ person.description }}</p>
                        <div class="person-btns">
                            <span @click="voteSelected('up')"><v-icon :id="'thumb-up-' + person.id" class="person-thumb bg-green" :class="{selected:this.vote === 'up'}" >fas fa-thumbs-up</v-icon></span>
                            <span @click="voteSelected('down')"><v-icon :id="'thumb-down-' + person.id" class="person-thumb bg-orange" :class="{selected:this.vote === 'down'}" >fas fa-thumbs-down</v-icon></span>
                            <v-btn class="btn-vote" @click="submitVote(vote)">Vote</v-btn>
                        </div>
                    </v-col>
                </v-row>
                <div class="person-votes">
                    <div v-if="person.votes.up > 0" class="vote vote-left bg-green" :style="{width: Math.floor((person.votes.up * 100) / person.votes.total ) + '%'}">
                        <v-icon class="person-btn">fas fa-thumbs-up</v-icon>
                        <span>{{ Math.floor((person.votes.up * 100) / person.votes.total )}}%</span>
                    </div>
                    <div v-if="person.votes.down > 0" class="vote vote-right bg-orange" :style="{width: Math.floor((person.votes.down * 100) / person.votes.total ) + '%'}">
                        <v-icon class="person-btn">fas fa-thumbs-down</v-icon>
                        <span>{{ Math.floor((person.votes.down * 100) / person.votes.total) }}%</span>
                    </div>
                </div>
            </div>
        </div>
    </article>
</template>

<script>
    import alertify from '../../node_modules/alertifyjs/build/alertify.js'
    export default {
        name: "person-component",
        props:['person'],
        data(){
            return{
                vote:'',
                item:{
                    index:'',
                    votes:{
                        up:0,
                        down:0,
                        total:0
                    }
                }
            }
        },
        methods:{
            voteSelected(value){
                this.vote = value;//setting local value
            },
            submitVote(vote){
                //adding the vote
                switch (vote) {
                    case 'up':
                        this.person.votes.up = this.person.votes.up + 1;
                        break;
                    case 'down':
                        this.person.votes.down = this.person.votes.down + 1;
                        break
                }
                //setting vote's total
                this.person.votes.total = this.person.votes.up + this.person.votes.down;
                alertify.confirm("Thank you for Voting!!, we appreciate your opinion",
                    ()=>{
                        alertify.success('Vote again');
                        this.vote = '';
                    },
                    ()=>{
                        alertify.error('Cancel');
                    });
            }
        }

    }
</script>

<style lang="scss" scoped>
    @import "../assets/sass/colors";
    .selected{
        border: 2px solid white;
    }
    .person-wrapper{
        background-size: cover;
        min-height: 550px;
        max-width: 550px;
        margin-bottom: 20px;
        position: relative;
        .person-body{
            position: absolute;
            bottom: 0;
            left: 0;
            color: #fff;
            h3{padding-right: 60px;}
            .person-thumb{
                font-size: 17px;
                color: white;
                padding: 10px;
                margin-right: 10px;
                cursor: pointer;
            }
            .votes-icon{
                position: relative;
                display: block;
                height: 100%;
                i{
                    position: absolute;
                    bottom: 5px;
                    left: 0;
                    cursor: default;
                }
            }
            .person-date{
                display: block;
                margin-bottom: 10px;
                font-size: 13px;
                line-height: 15px;
            }
            .person-text{
                font-size: 17px;
                line-height: 24px;
                padding-right: 60px;
                margin-bottom: 20px;
            }
            .person-btns{
                margin-bottom: 20px;
                .btn-vote{
                    background-color: rgba(0,0,0,0.7) !important;
                    color: white;
                    border: 1px solid white;
                    border-radius: 0;
                }
            }
            .person-votes{
                .vote{
                    display: inline-flex;
                    align-items: center;
                    width: 50%;
                    color: white;
                    font-size: 26px;
                    padding: 5px 15px;
                    &.vote-right{
                        justify-content: flex-end;
                    }
                    i{
                        color: white;
                        margin-right: 5px;
                    }
                }
            }
        }
    }
    /* responsive */
    /* mobile devices */
    @media only screen and (max-width: 600px){
        .person-wrapper{
            .person-body{
                .person-votes{
                    .vote{
                        font-size: 16px;
                        i{
                            display: none;
                        }
                    }
                }
            }
        }
    }
    /*small tablets*/
    @media only screen and (min-width: 601px) and (max-width: 787px){
        .person-wrapper{
            margin: 0 auto;
        }
    }
</style>
