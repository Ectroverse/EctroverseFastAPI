<template>
    <GamePage id="head_quarters">
        <div id="hq_content" slot="content">
            <display-box title="Headquarters">
                <div class="text" slot="content">
                    <div id="current_date_next_tick">
                        <div id="current_date">
                            Current date : {{current_date}}
                        </div>
                        <div id="next_tick">
                            Next tick : {{next_tick}}
                        </div>
                    </div>
                    <div id="user_faction">
                        <div id="user_name">
                            User <b>{{userProfile.email}}</b>
                        </div>
                        <div id="faction_name">
                            Faction <b>{{factionname}}</b>
                        </div>
                    </div>
                    <div id="hq_stats">
                        <div id="hq_stats_col_1">
                            <div>Empire: {{empire}}</div>
                            <div>Planets: {{planets}}</div>
                            <div>Population: {{population}}</div>
                            <div>Networth: {{networth}}</div>
                        </div>
                        <div id="hq_stats_col_2">
                            <div>Fleet readiness: {{fr}}%</div>
                            <div>Psychics readiness: {{pr}}%</div>
                            <div>Agents readiness: {{ar}}%</div>
                            <div>Home Planet: {{home_planet}}</div>
                        </div>
                    </div>
                    <div class="genwhite"><i>Message from Administration:</i></div>
                    <div id="admin_msg">
                        {{admin_message}}
                    </div>
                    <b>Message from your Prime Minister</b>
                    <div id="pm_msg">
                        {{prime_minister_message}}
                    </div>
                    <b>No new reports</b>
                    <div id="reports">
                        <router-link to="faction_reports">See all reports</router-link>
                    </div>
                </div>
            </display-box>
        </div>
    </GamePage>

</template>


<script lang="ts">
import DisplayBox from '@/components/DisplayBox.vue';
import GamePage from '@/components/GamePage.vue';
import { readUserProfile } from '@/store/main/getters';
import { Store } from 'vuex';
import { Component, Vue } from 'vue-property-decorator';

@Component({
  name: 'Headquarters',
  components: {
    DisplayBox,
    GamePage,
  },
})
export default class Headquarters extends Vue {
    private userProfile = readUserProfile(this.$store);
}
</script>

<style scoped>
    #head_quarters {
        display: flex;
        flex-direction: row;
        width: 100%;
    }
    #hq_content{
        width: 100%;
        justify-content: center;
        display: flex;
        flex-direction: column;
    }
    #current_date_next_tick{
        padding:10px;
    }
    #user_faction{
        padding:10px;
    }
    #hq_stats{
        width:100%;
        justify-content: center;
        display:flex;
        flex-direction: row;
        padding: 10px;
        margin-bottom: 20px;
    }
    #hq_stats_col_1{
        padding-right:50px;
    }
    #admin_msg{
        white-space: pre-line;
        width: fit-content;
        padding: 12px;
        font-family: Verdana, Arial, Helvetica, sans-serif;
        font-size: 11px;
        color: #8BC7FF;
        line-height: 125%;
        border: 1px solid #DDDDDD;
        margin: 0 auto 20px;
    }
    #pm_msg{
        margin-bottom:20px;
    }
</style>