<template>
    <div class="service-item-content-container border-common">Must Be Implemented</div>
</template>

<script lang="ts">
import { PropType, defineComponent } from 'vue'
import { FeatureStatus } from '../authForms/shared.vue'
import { ServiceItemId } from '../types'
import { ConnectionUpdateArgs } from '../authForms/baseAuth.vue'
import TelemetryClient from '../telemetry.vue'

export default defineComponent({
    name: 'BaseServiceItemContent',
    extends: TelemetryClient,
    emits: ['auth-connection-updated'],
    props: {
        state: {
            type: Object as PropType<FeatureStatus>,
            required: true,
        },
    },
    methods: {
        emitAuthConnectionUpdated(id: ServiceItemId, args: ConnectionUpdateArgs) {
            this.$emit('auth-connection-updated', id, args)
        },
    },
})
</script>
<style>
@import './baseServiceItemContent.css';
@import '../shared.css';
</style>
