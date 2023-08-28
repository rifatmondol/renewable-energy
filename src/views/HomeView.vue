<template>
    <Header/>
    <Banner/>
    <Service/>
    <Facility/>
    <Project/>
    <Energy/>
    <Renewable/>
    <Responsibility/>
    <WorldClean/>
    <Global/>
    <ArticleComponent/>
    <FooterPart/>

    <BottomToTop/>
</template>

<script>
import Header from '@/components/Header.vue'
import Banner from '@/components/Banner.vue'
import Service from '@/components/Service.vue'
import Facility from '@/components/Facility.vue'
import Project from '@/components/Project.vue'
import Energy from '@/components/Energy.vue'
import Renewable from '@/components/Renewable.vue'
import Responsibility from '@/components/Responsibility.vue'
import WorldClean from '@/components/WorldClean.vue'
import Global from '@/components/Global.vue'
import ArticleComponent from '@/components/ArticleComponent.vue'
import FooterPart from '@/components/FooterPart.vue'
import BottomToTop from '@/components/BottomToTop.vue'

export default{
    name:"HomeView",
    components:{
        Header,
        Banner,
        Service,
        Facility,
        Project,
        Energy,
        Renewable,
        Responsibility,
        WorldClean,
        Global,
        ArticleComponent,
        FooterPart,
        BottomToTop
    }
}
</script>

<style>

</style>