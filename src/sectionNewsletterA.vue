<template>
    <div class="newsletter_A">
        <!-- wwManager:start -->
        <wwSectionEditMenu v-bind:sectionCtrl="sectionCtrl"></wwSectionEditMenu>
        <!-- wwManager:end -->

        <wwObject class="background" v-bind:ww-object="section.data.background" ww-category="background"></wwObject>
    </div>
</template>

<script>
export default {
    name: "newsletter_A",
    props: {
        sectionCtrl: Object
    },
    data() {
        return {}
    },
    computed: {
        section() {
            return this.sectionCtrl.get();
        }
    },
    created() {
        this.section.data = this.section.data || {};

        //Initialize image
        if (!this.section.data.background) {
            this.section.data.background = wwLib.wwObject.getDefault({ type: 'ww-image' });
        }

    },
    methods: {}
};
</script>

<style scoped>
.newsletter_A {}

.newsletter_A .background {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
}
</style>
