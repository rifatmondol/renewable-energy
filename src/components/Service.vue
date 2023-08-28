<template>
    <div class="service wrapper">
        <div class="container">
            <div class="service-section">
                <div class="row">
                    <div class="col-lg-3 col-md-6 mb-4" v-for="item in items" :key="item">
                        <div class="service-item text-center">
                            <div class="service-image mb-4">
                                <img :src="item.src" :alt="item.src">
                            </div>
                            <div class="service-text">
                                <h6 class="mb-4 title">{{item.title}}</h6>
                                <p class="mb-4 text-dark-gray">{{ item.subtitle }}</p>
                                <router-link to="/" class="text-decoration-none d-inline-block btn-link">{{ item.btn }}</router-link>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import icon1 from '@/assets/images/renewable-icon1.png'
import icon2 from '@/assets/images/renewable-icon2.png'
import icon3 from '@/assets/images/renewable-icon3.png'
import icon4 from '@/assets/images/renewable-icon4.png'

export default{
    name:'ServiceComponent',
    data(){
        return{
            items:[
                {
                    src:icon1,
                    title: 'Analysis',
                    subtitle:'The company provides a full suite of renewable products',
                    btn:'Learn More'
                },
                {
                    src:icon2,
                    title: 'Engineering',
                    subtitle:'The company provides a full suite of renewable products',
                    btn:'Learn More'
                },
                {
                    src:icon3,
                    title: 'Operation',
                    subtitle:'The company provides a full suite of renewable products',
                    btn:'Learn More'
                },
                {
                    src:icon4,
                    title: 'Maintenance',
                    subtitle:'The company provides a full suite of renewable products',
                    btn:'Learn More'
                },
            ]
        }
    }
}
</script>