<template>
    <div id="game_page">
        <side-nav></side-nav>
        <div id="page_content">
            <top-nav></top-nav>
            <slot name="content"></slot>
        </div>
    </div>
</template>

<script lang="ts">
    import TopNav from '@/components/TopNav.vue';
    import SideNav from '@/components/SideNav.vue';
    import { Component, Vue, Prop } from 'vue-property-decorator';
    @Component({
        name: 'GamePage',
        components: {
            TopNav,
            SideNav,
        },
    })
    export default class GamePage extends Vue {
    }
</script>

<style scoped>
    #game_page {
        display: flex;
        flex-direction: row;
        width: 100%;
    }
    #page_content{
        width: 100%;
    }
</style>