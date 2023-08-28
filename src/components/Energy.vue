<template>
    <div class="energy py-5 wrapper">
        <div class="container">
            <div class="energy-main">
                <div class="title-part">
                    <h3 class="text-center mb-3 mt-5">We offer options for greening up energy use and <br>
                    improving your environmental credentials</h3>
                </div>

                <div class="content-part mt-5 pt-4">
                    <div class="row">
                        <div class="col-lg-4 col-md-6 mb-4" v-for="list in lists" :key="list.img">
                            <div class="content-item">
                                <div class="image-part">
                                    <router-link to="/"><img :src="list.img" :alt="list.img"></router-link>
                                </div>
                                <div class="details-part mt-4">
                                    <h6 class="title">{{ list.title }}</h6>
                                    <p class="mb-4 text-dark-gray">{{ list.description }}</p>
                                    <router-link to="/" class="text-decoration-none btn-link">{{ list.button }}</router-link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <hr class="hr">
        </div>
    </div>
</template>

<script>
import service1 from '@/assets/images/renewable-service1.jpg'
import service2 from '@/assets/images/renewable-service2.jpg'
import service3 from '@/assets/images/renewable-service3.jpg'

export default{
    name:'BestPrice',
    data(){
        return{
            lists:[
                {img: service1, title: 'Wind Energy', description: 'We’re an environmentally friendly renewable energy company offering a broad portfolio of technologies, products, and solutions to our clients globally.', button:'Learn More'},
                {img: service2, title: 'Hydro Power', description: 'We’re an environmentally friendly renewable energy company offering a broad portfolio of technologies, products, and solutions to our clients globally.', button:'Learn More'},
                {img: service3, title: 'Solar Power', description: 'We’re an environmentally friendly renewable energy company offering a broad portfolio of technologies, products, and solutions to our clients globally.', button:'Learn More'},
            ]
        }
    }
}
</script>

<style>
</style>