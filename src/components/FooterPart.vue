<template>
    <footer>
        <div class="container">
            <div class="footer-main">
                <div class="footer-top py-4">
                    <div class="top-menu d-md-flex justify-content-between">
                        <ul class="navbar-nav p-0 flex-md-row flex-grow-1 ">
                            <li class="nav-item" v-for="item in items" :key="item">
                                <router-link :to="item.url" class="text-decoration-none text-dark-gray-2">{{ item.menuName }}</router-link>
                            </li>
                        </ul>
                        <div class="social">
                            <span>
                                <a href="#"><font-awesome-icon icon="fa-brands fa-facebook-f" /></a
                                >
                            </span>
                            <span>
                                <a href="#"><font-awesome-icon icon="fa-brands fa-linkedin-in" /></a>
                            </span>
                            <span>
                                <a href="#"><font-awesome-icon icon="fa-brands fa-twitter" /></a>
                            </span>
                        </div>
                    </div>
                </div>
                <hr class="m-0">
                <div class="footer-middle py-md-5 py-3">
                    <div class="row">
                        <div class="col-lg-3 col-md-6">
                            <div class="middle-item my-4">
                                <h5 class="mb-3">About</h5>
                                <ul class="navbar-nav p-0 flex-grow-1 ">
                                    <li class="nav-item" v-for="item in middleMenu1" :key="item">
                                        <router-link :to="item.url" class="text-decoration-none text-dark-gray-2">{{ item.menuName }}</router-link>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="col-lg-2 col-md-6">
                            <div class="middle-item my-4">
                                <h5 class="mb-3">Products</h5>
                                <ul class="navbar-nav p-0 flex-grow-1 ">
                                    <li class="nav-item" v-for="item in middleMenu2" :key="item">
                                        <router-link :to="item.url" class="text-decoration-none text-dark-gray-2">{{ item.menuName }}</router-link>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="col-lg-2 col-md-6">
                            <div class="middle-item my-4">
                                <h5 class="mb-3">Resources</h5>
                                <ul class="navbar-nav p-0 flex-grow-1 ">
                                    <li class="nav-item" v-for="item in middleMenu3" :key="item">
                                        <router-link :to="item.url" class="text-decoration-none text-dark-gray-2">{{ item.menuName }}</router-link>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="col-lg-3 col-md-6">
                            <div class="middle-item my-4">
                                <h5 class="mb-3">Follow us</h5>
                                <ul class="navbar-nav p-0 flex-grow-1 ">
                                    <li class="nav-item" v-for="item in middleMenu4" :key="item">
                                        <router-link :to="item.url" class="text-decoration-none text-dark-gray-2">{{ item.menuName }}</router-link>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="col-lg-2">
                            <div class="middle-item last my-4">
                                <h5 class="text-lg-end mb-4">Contact</h5>
                                <ul class="navbar-nav p-0 flex-grow-1 ">
                                    <li class="nav-item text-lg-end text-dark-gray-2">New York. 112 W <br> 34th St, Manhattan</li>
                                    <li class="nav-item text-lg-end">
                                        <a href="tel:+1 2124454320" class="text-decoration-none text-dark-gray-2">(1) 212-445-4320</a>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
                <hr class="m-0">
                <div class="footer-bottom py-3">
                    <div class="row">
                        <div class="col-md-6">
                            <div class="bottom-item">
                                <p class="m-0 text-dark-gray-2 fw-medium text-md-start text-center">© 2023 Sway by KeyDesign. All Rights Reserved.</p>
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="bottom-item">
                                <ul class="navbar-nav d-md-flex d-block flex-row justify-content-end p-0 flex-grow-1">
                                    <li class="nav-item text-center">
                                        <router-link to="/" class="text-decoration-none">Terms of Use</router-link>
                                    </li>
                                    <li class="nav-item text-center">
                                        <router-link to="/" class="text-decoration-none">Privacy Policy</router-link>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
export default{
    name:'FooterView',
    data(){
        return{
            items:[
                {
                    menuName:'About',
                    url:'/'
                },
                {
                    menuName:'Services',
                    url:'/'
                },
                {
                    menuName:'Pricing Plans',
                    url:'/'
                },
                {
                    menuName:'Privacy',
                    url:'/'
                },
                {
                    menuName:'Contact Us',
                    url:'/'
                },
            ],
            middleMenu1:[
                {
                    menuName:'About Sway',
                    url:'/'
                },
                {
                    menuName:'Plans & Pricing',
                    url:'/'
                },
                {
                    menuName:'Services',
                    url:'/'
                },
                {
                    menuName:'Blog',
                    url:'/'
                },
            ],
            middleMenu2:[
                {
                    menuName:'Primary Blocks',
                    url:'/'
                },
                {
                    menuName:'Content Blocks',
                    url:'/'
                },
                {
                    menuName:'Infographic Blocks',
                    url:'/'
                },
                {
                    menuName:'Business Blocks',
                    url:'/'
                },
            ],
            middleMenu3:[
                {
                    menuName:'Support center',
                    url:'/'
                },
                {
                    menuName:'Documentation',
                    url:'/'
                },
                {
                    menuName:'Newsletter',
                    url:'/'
                },
                {
                    menuName:'Changelog',
                    url:'/'
                },
            ],
            middleMenu4:[
                {
                    menuName:'Twitter',
                    url:'/'
                },
                {
                    menuName:'Dribbble',
                    url:'/'
                },
                {
                    menuName:'Facebook',
                    url:'/'
                },
                {
                    menuName:'Linkedin',
                    url:'/'
                },
            ],
        }
    }
}

</script>

<style>
</style>