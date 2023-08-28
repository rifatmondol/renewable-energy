<template>
    <div class="article wrapper">
        <div class="container">
            <div class="article-main">
                <div class="row">
                    <div class="col-md-9">
                        <div class="article-main-item left">
                            <h4 class="title">Articles contributed by experts in the renewable <br>
                            energy and sustainable industry</h4>
                        </div>
                    </div>
                    <div class="col-md-3">
                        <div class="article-main-item right text-end">
                            <router-link to="/" class="d-inline-block text-decoration-none position-relative">
                                View Insights
                                <span class="ms-1 d-inline-block">
                                    <font-awesome-icon icon="fa-solid fa-angle-right" />
                                </span>
                            </router-link>
                        </div>
                    </div>
                </div>
            </div>
            <div class="article-outer mt-5 pt-3">
                <div class="row">
                    <div class="col-md-4 mb-4" v-for="item in items" :key="item">
                        <div class="article-inner">
                            <router-link to="/" class="text-decoration-none d-inline-block btn-link">
                                <font-awesome-icon icon="fa-solid fa-circle" class="me-1"/>
                                {{ item.type }}
                            </router-link>
                            <router-link to="/" class="text-decoration-none d-block title mt-3">
                                {{ item.title }}
                            </router-link>
                            <router-link to="/" class="read-more text-decoration-none d-inline-block title mt-4 mb-3 bg-light-green position-relative">
                                {{ item.readMore }}
                            </router-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ArticleComponent',
    data(){
        return{
            items:[
                {
                    type:'Solutions',
                    title:'A day in the life of a wind turbine blade assessor',
                    readMore:'Read more'
                },
                {
                    type:'Operations',
                    title:'How cities and counties are getting renewable energy',
                    readMore:'Read more'
                },
                {
                    type:'Managements',
                    title:'Solar prospects rise in MISO utility resource plans',
                    readMore:'Read more'
                },
            ]
        }
    }
}
</script>