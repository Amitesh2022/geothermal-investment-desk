<script setup lang="ts">
import { onMounted } from 'vue'
import { storeToRefs } from 'pinia'
import { RouterLink, RouterView } from 'vue-router'
import { useDeliveryStore } from './store'
const store = useDeliveryStore()
const { approvedShare, offers, urgent } = storeToRefs(store)
onMounted(store.load)
</script>

<template><div class="shell"><aside><div class="brand">GeoInvestEU<span>GEOTHERMAL PROJECTS</span></div><nav><RouterLink to="/">Investment plans</RouterLink><RouterLink to="/insights">Investment guidance</RouterLink></nav><div class="health"><i /> Java geothermal investment service connected</div></aside><main><header><div><span class="eyebrow">Derisk geothermal heat, power and geological exploration</span><h1>Geothermal Investment Desk</h1></div><button @click="store.addOffer">Add investment plan</button></header><section class="summary"><article><small>Plans ready</small><strong>{{ approvedShare }}%</strong><div class="bar"><span :style="{ width: `${approvedShare}%` }" /></div></article><article><small>Plans tracked</small><strong>{{ offers.length }}</strong><p>Shared investment view</p></article><article><small>High-priority gaps</small><strong>{{ urgent }}</strong><p>Needs attention</p></article></section><RouterView /></main></div></template>
