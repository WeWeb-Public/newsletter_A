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
                <!-- <h1>
                    <wwObject v-bind:ww-object="section.data.title"></wwObject>
                </h1>
                <h2 class="subtitle">
                    <wwObject v-bind:ww-object="section.data.subtitle"></wwObject>
                </h2> -->
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
        this.init()
    },
    methods: {
        init() {
            this.section.data = this.section.data || {} 
            this.section.data = {"alt":"jolie ville","btn":{"data":{"popup":null},"font":"","link":"section://159","size":"","text":{"fr_FR":"Submit"},"type":"text","zoom":-1,"align":"","class":["ww-class-btn-padding-medium","ww-class-btn-shadow-bottom-small","ww-class-btn-format-round-small","ww-anim-fade"],"image":"/img/no_image_selected.png","ratio":-1,"colors":{"color":"#000000","borderColor":"","backgroundColor":"#FFFFFF"},"hidden":false,"position":{"x":0,"y":0},"uniqueId":0.1307333856855486},"img":{"alt":null,"link":null,"image":"http://static.cotemaison.fr/medias_10824/w_2048,h_1146,c_crop,x_0,y_68/w_15…,g_north/v1456391043/10-astuces-pour-rendre-votre-chat-heureux_5542219.jpg"},"image":{"title":{"data":{"popup":null},"font":"","link":"","size":"text-big","text":{"fr_FR":"This is the Newsletter Section"},"type":"text","zoom":-1,"align":"justify","class":["ww-anim-fade-top-bounce","ww-animspeed-normal"],"image":"/img/no_image_selected.png","ratio":-1,"colors":{"color":"#FFFFFF","borderColor":"","backgroundColor":""},"hidden":false,"position":{"x":0,"y":0},"uniqueId":0.06984277569772246},"subtitle":{"data":{"popup":null},"font":"","link":"","size":"text-small","text":{"fr_FR":"Here you can ask your visitors to provide their e-mail addresses.<br>We'll send you an e-mail each time one does it.<br>You can change your reception e-mail in the configuration panel. "},"type":"text","zoom":-1,"align":"","class":["ww-anim-fade-right-bounce","ww-animspeed-normal"],"image":"/img/no_image_selected.png","ratio":-1,"colors":{"color":"#FFFFFF","borderColor":"","backgroundColor":""},"hidden":false,"position":{"x":0,"y":0},"uniqueId":0.07235985390358435},"titleStyle":{"size":"text-medium","color":"#FFFFFF"},"subtitleStyle":{"color":"#FFFFFF"}},"isNew":false,"title":"Stay in touch","subtitle":"We will send you our awesome Newsletter","okMessage":{"data":{},"link":{"data":{},"type":"none"},"tags":[],"ratio":-1,"hidden":false,"content":{"data":{"alt":{"en_GB":"webeo","fr_FR":"webeo"},"url":"/img/no_image_selected.png","zoom":-1,"hover":{"name":"","options":{}},"ratio":-1,"classes":[],"imgSize":{"h":1000,"w":998},"position":{"x":0,"y":0},"borderColor":"","filterGradient":null},"type":"ww-image"},"children":{},"paddings":{},"uniqueId":1520527563864.009,"wwVersion":3,"altTags":[]},"topWwObjs":[{"data":{"children":{}},"link":{"data":{},"type":"none"},"tags":[],"ratio":66.66666,"hidden":false,"content":{"data":{"size":"big"},"type":"ww-margin"},"children":{},"paddings":{},"uniqueId":1520527567809.576,"wwVersion":3,"altTags":[]},{"data":{"children":{}},"link":{"data":{},"type":"none"},"tags":[],"ratio":66.66666,"hidden":false,"content":{"data":{"tag":"div","font":"","size":2.5,"text":{"en_GB":"New text","fr_FR":"This is the newsletter section"},"align":"center","color":"#FFFFFF","classes":[],"children":[]},"type":"ww-text"},"children":{},"paddings":{},"uniqueId":1520527597351.8606,"wwVersion":3,"altTags":[]},{"data":{"children":{}},"link":{"data":{},"type":"none"},"tags":[],"ratio":66.66666,"hidden":false,"content":{"data":{"tag":"div","font":"","size":1,"text":{"en_GB":"New text","fr_FR":"<div><br></div>Collect your visitors e-mail with this efficient e-mail submission form.<div>Hit the pen and manage details on the top of this section.</div>"},"align":"center","color":"#FFFFFF","classes":[],"children":[]},"type":"ww-text"},"children":{},"paddings":{},"uniqueId":1520527666320.8152,"wwVersion":3,"altTags":[]}],"background":{"data":{"popup":null},"link":{"data":{},"type":"none"},"tags":[],"ratio":100,"hidden":false,"content":{"data":{"alt":{"en_GB":"webeo","fr_FR":"webeo"},"url":"https://wewebprod.s3-eu-west-1.amazonaws.com/public/images/landscape/Mountain1.jpg","zoom":-1,"hover":{"name":"","options":{}},"ratio":-1,"classes":[],"imgSize":{"h":682,"w":1023},"position":{"x":0,"y":0},"borderColor":"","filterGradient":null,"backgroundColor":""},"type":"ww-image"},"children":{},"paddings":{},"uniqueId":0.44186093582906083,"wwVersion":3,"altTags":[]},"nokMessage":{"data":{},"link":{"data":{},"type":"none"},"tags":[],"ratio":-1,"hidden":false,"content":{"data":{"alt":{"en_GB":"webeo","fr_FR":"webeo"},"url":"/img/no_image_selected.png","zoom":-1,"hover":{"name":"","options":{}},"ratio":-1,"classes":[],"imgSize":{"h":1000,"w":998},"position":{"x":0,"y":0},"borderColor":"","filterGradient":null},"type":"ww-image"},"children":{},"paddings":{},"uniqueId":1520527563873.2927,"wwVersion":3,"altTags":[]},"bottomWwObjs":[{"data":{"children":{}},"link":{"data":{},"type":"none"},"tags":[],"ratio":66.66666,"hidden":false,"content":{"data":{"size":"big"},"type":"ww-margin"},"children":{},"paddings":{},"uniqueId":1520527569176.3528,"wwVersion":3,"altTags":[]}],"sectionTitle":"Newsletter","btnSendBgC":"#000000"}

            this.section.data.topWwObjs = this.section.data.topWwObjs || [];
            this.section.data.bottomWwObjs = this.section.data.bottomWwObjs || [];

            if (!this.section.data.background)
                this.section.data.background = wwLib.wwObject.getDefault({ type: 'ww-color' });
            
            // if (!this.section.data.title)
            //     this.section.data.title = wwLib.wwObject.getDefault({ type: 'ww-text' });

            // if (!this.section.data.subtitle)
            //     this.section.data.subtitle = wwLib.wwObject.getDefault({ type: 'ww-text' });

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
        add(array, options) {
            array.splice(options.index, 0, options.wwObject);
            this.sectionCtrl.update(this.section);
        },
        remove(array, options) {
            array.splice(options.index, 1);
            this.sectionCtrl.update(this.section);
        }
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
    padding: 0px !important;
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

.newsletter_A .section-padding {
    padding: 30px 15px
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
    margin: 20px 0;
    margin-left: 8.333333%;
}

.newsletter_A .subtitle {
    margin-top: 10px;
}

@media (min-width: 480px) {}

@media (min-width: 768px) {
    .newsletter_A .section-padding {
        padding: 50px 30px
    }
    .newsletter_A .block {
        -ms-flex: 0 0 66.666666%;
        flex: 0 0 66.666666%;
        max-width: 66.666666%;
        margin-left: 16.666666%;
    }
}

@media (min-width: 992px) {
    .newsletter_A .section-padding {
        padding: 75px 50px
    }
}

@media (min-width: 1024px) {
    .newsletter_A .block {
        -ms-flex: 0 0 50%;
        flex: 0 0 50%;
        max-width: 50%;
        margin-left: 25%;
    }
}
</style>
