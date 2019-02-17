<template>
    <div class="newsletter_A">
        <!-- wwManager:start -->
        <wwSectionEditMenu v-bind:sectionCtrl="sectionCtrl"></wwSectionEditMenu>
        <!-- wwManager:end -->
        <wwObject class="background" v-bind:ww-object="section.data.background" ww-category="background"></wwObject>
        <div>
            <!--TOP WWOBJS-->
            <div class="top-ww-objs">
                <wwLayoutColumn tag='div' ww-default="ww-row" :ww-list="section.data.topWwObjs" class="wwobjects-wrapper" @ww-add="add(section.data.topWwObjs, $event)" @ww-remove="remove(section.data.topWwObjs, $event)">
                    <div class="top-ww-obj" v-for="topWwObj in section.data.topWwObjs" :key="topWwObj.uniqueId">
                        <wwObject v-bind:ww-object="topWwObj"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
            <div class="container section-padding">
                <!--TITLES-->
                <h1>
                    <wwObject v-bind:ww-object="section.data.title"></wwObject>
                </h1>
                <h2 class="subtitle">
                    <wwObject v-bind:ww-object="section.data.subtitle"></wwObject>
                </h2>
                <!--NEWSLETTER-->
                <div class="row">
                    <div class="block">
                        <wwObject v-bind:ww-object="section.data.newsletter"></wwObject>
                    </div>
                </div>
            </div>
            <!--BOTTOM WWOBJS-->
            <div class="bottom-ww-objs">
                <wwLayoutColumn tag='div' ww-default="ww-row" :ww-list="section.data.bottomWwObjs" class="wwobjects-wrapper" @ww-add="add(section.data.bottomWwObjs, $event)" @ww-remove="remove(section.data.bottomWwObjs, $event)">
                    <div class="top-ww-obj" v-for="bottomWwObj in section.data.bottomWwObjs" :key="bottomWwObj.uniqueId">
                        <wwObject v-bind:ww-object="bottomWwObj"></wwObject>
                    </div>
                </wwLayoutColumn>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "__COMPONENT_NAME__",
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
        this.init()
    },
    methods: {
        init() {
            this.section.data = this.section.data || {} 
            this.section.data.topWwObjs = this.section.data.topWwObjs || [];
            this.section.data.bottomWwObjs = this.section.data.bottomWwObjs || [];

            if (!this.section.data.background) {
                this.section.data.background = wwLib.wwObject.getDefault({ 
                    type: 'ww-image',
                    data: {
                        url: 'http://cdn.wewebapp.io/public/images/weweb-wp.png'
                    }
                });
            }
            if (!this.section.data.title) {
                this.section.data.title = wwLib.wwObject.getDefault({ type: 'ww-text', data: { color: 'white', align: 'center' } });
            }
            if (!this.section.data.subtitle) {
                this.section.data.subtitle = wwLib.wwObject.getDefault({ type: 'ww-text', data: { color: 'white', align: 'center' } });
            }
            if (!this.section.data.newsletter) {
                this.section.data.newsletter = wwLib.wwObject.getDefault({ type: 'ww-newsletter', 
                    data: {
                        emailAddress: this.section.data.emailAddress,
                        btnSendBgC: this.section.data.btnSendBgC,
                        nokMessage: this.section.data.nokMessage
                    }
                });
            }
            this.sectionCtrl.update(this.section);
        },
        // wwManager:start
        add(array, options) {
            array.splice(options.index, 0, options.wwObject);
            this.sectionCtrl.update(this.section);
        },
        remove(array, options) {
            array.splice(options.index, 1);
            this.sectionCtrl.update(this.section);
        }
        // wwManager:end
    }
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

.newsletter_A .container {
    width: 100%;
    height: 100%;
    position: relative;
}

.newsletter_A .bottom-ww-objs {
    position: relative;
}

.newsletter_A .top-ww-objs {
    position: relative;
}

.newsletter_A .top-ww-obj,
.bottom-ww-obj {
    position: relative;
}

.newsletter_A .row {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}

.newsletter_A .block {
    position: relative;
    width: 83.333333%;
    min-height: 1px;
    padding-right: 15px;
    padding-left: 15px;
    -ms-flex: 0 0 83.333333%;
    flex: 0 0 83.333333%;
    max-width: 83.333333%;
    text-align: center;
    margin-top: 20px;
    margin-left: 8.333333%;
}

.newsletter_A .subtitle {
    margin-top: 10px;
}

@media (min-width: 480px) {}

@media (min-width: 768px) {
    .newsletter_A .block {
        -ms-flex: 0 0 66.666666%;
        flex: 0 0 66.666666%;
        max-width: 66.666666%;
        margin-left: 16.666666%;
    }
}

@media (min-width: 992px) {
    .newsletter_A .block {
        -ms-flex: 0 0 50%;
        flex: 0 0 50%;
        max-width: 50%;
        margin-left: 25%;
    }
}
</style>
