<template>
<div>
<h1>Here is the list of VIPs</h1>
<table border="1px">
    <tr>
        <td>account(key)</td>
        <td>Last claim ID</td>
        <td>Stake balance</td>
        <td>tier</td>
        <td>tier history</td>
    </tr>
    <tr v-for="item in list" v-bind:key="item.id">
        <td>{{item.account(key)}}</td>
        <td>{{item.last_claim_id}}</td>
        <td>{{item.stake_balance}}</td>
        <td>{{item.tier}}</td>
        <td>{{item.tier_history}}</td>
    </tr>
</table>
</div>
</template>
<script>
import Vue from 'Vue';
import axios from 'axios';
import VueAxios from 'vue-axios';

Vue.use(VueAxios,axios)
export default {

    name:"vipList",
    data()
    {
        return {list:undefined}
    },
    mounted()
    {
        Vue.axios.get('https://telos.bloks.io/account/stake.start').then((response)=> {
            this.list=response.data.data
            console.warn(response.data.data)
        })
    }
}
</script>