<template>
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
                  <h2>Sign In</h2>
                </div>
                <form role="form" action="/auth/login" method="POST">
                  <div class="form-group mb-3">
                    <div class="input-group input-group-alternative">
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
                      <input
                        class="form-control"
                        placeholder="Password"
                        type="password"
                        v-model="User.password"
                      />
                    </div>
                  </div>
                  <div
                    class="custom-control custom-control-alternative custom-checkbox"
                  >
                    <input
                      class="custom-control-input"
                      id=" customCheckLogin"
                      type="checkbox"
                    />
                    <label class="custom-control-label" for=" customCheckLogin">
                      <span>Remember me</span>
                    </label>
                  </div>
                  <div class="text-center">
                    <button type="submit" class="btn btn-primary my-4" @click="logIn">
                      Sign in
                    </button>
                  </div>
                </form>
              </div>
            </div>
            <div class="row mt-3">
              <div class="col-6">
                <a href="#" class="text-light">
                  <small>Forgot password?</small>
                </a>
              </div>
              <div class="col-6 text-right">
                <router-link to="/register" class="text-light"
                  ><small>Create new account</small>
                </router-link>
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
    name: 'LogIn',
    data() {
        return {
            User: {
                username: '',
                password: ''
            }
        };
    },
    methods: {
        logIn() {
            let newUser = {
                username: this.User.username,
                password: this.User.password
            }
            console.log(newUser);
            axios.post('http://localhost:5000/authlogIn', newUser)
                .then((response) => {
                    console.log("ayat",response)
                try {
                    if (response.status === true){
                        alert("LogIn Succesfully");
                        this.$router.push({name:'home'})
                    }else {
                        alert("LogIn failed");
                    }
                }catch (err){
                        alert("error")
                }
                })

        }
    }
};
</script>