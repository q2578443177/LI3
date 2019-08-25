<template>
    <div id="warp" v-drag>
        <div id="container">
            <v-header></v-header>
        </div>
    </div>
</template>

<script>
    import vheader from '@/components/header.vue';
    import {
        mapState,
        mapMutations,
        mapActions
    } from 'vuex';
    export default {
        name: 'game',
        components: {
            "v-header": vheader,
        },
        data() {
            return {

            }
        },
        created() {
        },
        mounted() {
        },
        computed: {

        },
        methods: {

        },
        directives: {
            //拖动
            drag: {
                bind: function (el) {
                    let node = el;   //获取当前元素
                    node.onmousedown = (e) => {
                        //算出鼠标相对元素的位置
                        let disX = e.clientX - node.offsetLeft;
                        let disY = e.clientY - node.offsetTop;

                        document.onmousemove = (e) => {
                            //用鼠标的位置减去鼠标相对元素的位置，得到元素的位置
                            let left = e.clientX - disX;
                            let top = e.clientY - disY;

                            //移动当前元素
                            node.style.left = left + 'px';
                            node.style.top = top + 'px';
                        };
                        document.onmouseup = (e) => {
                            document.onmousemove = null;
                            document.onmouseup = null;
                        };
                    };
                }
            }
        }
    }
</script>

<style lang="scss">
    //阿里图标
    @import url("http://at.alicdn.com/t/font_586765_iustpfl9kap.css");
    @import "../public/scss/animation.scss";
    @import "../public/scss/ui.scss";

    #warp {
        position: absolute;
        top: 5%;
        left: calc(50% - 530px);
        width: 1060px;
        height: 700px;
        border-radius: 20px;
        box-shadow: 10px 10px 50px gray;
        transition-duration: all 0.5s;
        cursor: default;
        color: rgba(255, 255, 255, 0.8);
        background: #686669;

        &.full {
            @include fullscreen;
        }

        #container {
            width: 100%;
            height: 100%;
            background: linear-gradient(
                135deg,
                rgba(186, 67, 168, 0.38) 0%,
                rgba(233, 79, 205, 0.17) 61%,
                rgba(234, 79, 206, 0.19) 62%,
                rgba(83, 123, 173, 0.8) 100%
            );
        }
    }
</style>
