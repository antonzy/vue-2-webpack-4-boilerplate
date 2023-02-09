<template>
  <StiggProvider v-bind="stiggProvider">
    <Paywall v-bind="paywall" />
  </StiggProvider>
</template>

<script>
import { Paywall, StiggProvider } from '@stigg/vue-2-sdk/dist/stigg.umd.js';

export default {
    components: {
        StiggProvider,
        Paywall
    },
    computed: {
        stiggProvider () {
            return {
                apiKey: '$2b$10$oBzWqcojPmYAfM2C9SeVC.sQIC1713t1fB.HK0i13YzGrJ.rCZYfe:9cfd480c-014b-4dbe-9127-39bf389edf13'
            };
        },
        paywall () {
            return {
                onPlanSelected: ({ plan }) => {
                    console.log(`Selected plan: ${plan.displayName}`);
                }
            };
        }
    }
};
</script>