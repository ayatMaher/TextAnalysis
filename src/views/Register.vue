<template>
    <header class="header-global">
        <nav id="navbar-main" class="navbar navbar-main navbar-expand-lg navbar-transparent navbar-light">
            <div class="container">
                <div class="navbar-collapse collapse" id="navbar_global">
                    <ul class="navbar-nav align-items-lg-center ml-lg-auto">
                        <li class="nav-item d-none d-lg-block ml-lg-4">
                            <router-link
                                    to="/logIn"
                                    target="_self"
                                    class="btn btn-neutral btn-icon"
                            ><span class="nav-link-inner--text">Sign In</span>
                            </router-link>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
    <main>
        <section class="section section-shaped section-lg my-0">
            <div class="shape shape-style-1 bg-gradient-default">
                <span></span>
                <span></span>
                <span></span>
                <span></span>
                <span></span>
                <span></span>
                <span></span>
                <span></span>
            </div>
            <div class="container pt-lg-md">
                <div class="row justify-content-center">
                    <div class="col-lg-5">
                        <div class="card bg-secondary shadow border-0">
                            <div class="card-body px-lg-5 py-lg-5">
                                <div class="text-center text-muted mb-4">
                                    <h2>Sign Up</h2>
                                </div>
                                <form role="form">
                                    <div class="form-group">
                                        <div class="input-group input-group-alternative mb-3">
                                            <div class="input-group-prepend">
                        <span class="input-group-text"
                        ><i class="ni ni-hat-3"></i
                        ></span>
                                            </div>
                                            <input
                                                    class="form-control"
                                                    placeholder="Name"
                                                    type="text"
                                                    v-model="User.name"
                                            />
                                        </div>
                                    </div>
                                    <div class="form-group">
                                        <div class="input-group input-group-alternative mb-3">
                                            <div class="input-group-prepend">
                        <span class="input-group-text"
                        ><i class="ni ni-email-83"></i
                        ></span>
                                            </div>
                                            <input
                                                    class="form-control"
                                                    placeholder="Email"
                                                    type="email"
                                                    v-model="User.email"
                                            />
                                        </div>
                                    </div>
                                    <div class="form-group">
                                        <div class="input-group input-group-alternative mb-3">
                                            <div class="input-group-prepend">
                        <span class="input-group-text"
                        ><i class="ni ni-hat-3"></i
                        ></span>
                                            </div>
                                            <input
                                                    class="form-control"
                                                    placeholder="User Name"
                                                    type="text"
                                                    v-model="User.username"
                                            />
                                        </div>
                                    </div>
                                    <div class="form-group">
                                        <div class="input-group input-group-alternative">
                                            <div class="input-group-prepend">
                        <span class="input-group-text"
                        ><i class="ni ni-lock-circle-open"></i
                        ></span>
                                            </div>
                                            <input class="form-control" placeholder="Password" type="password"
                                                   v-model="User.password"/>
                                        </div>

                                    </div>

                                    <div class="text-center">
                                        <!--                                        <router-link to="/" class="text-light">-->
                                        <button type="submit" class="btn btn-primary mt-4" @click="signUp">
                                            Create account
                                        </button>
                                        <!--                                        </router-link>-->
                                    </div>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import axios from "axios";

export default {
    name: 'Register',
    data() {
        return {
            User: {
                name: '',
                email: '',
                username: '',
                password: ''
            }
        };
    },
    methods: {
        signUp() {
            let newUser = {
                name: this.User.name,
                email: this.User.email,
                username: this.User.username,
                password: this.User.password
            }
            console.log(newUser);
            axios.post('http://localhost:5000/auth/signUp', newUser)
                .then((response) => {
                    console.log("ayat", response)
                    console.log("ayat", "http://localhost:5000/auth/signUp")
                })
                .catch((error) => {
                    console.log("song", error)
                    this.$router.push({name: 'logIn'})
                })
        }
    }
};
</script>
