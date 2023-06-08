<template>
<div class="card mx-auto col-lg-4 p-2 mt-4">
  <slot name="special"></slot>
  <h2 class="text-center bg-success text-white rounded-pill">signUp page</h2>
  <div class="form-group form-floating my-2">
    <input type="text" class="form-control" placeholder="Name" name="student_name" v-model="name">
    <label for="">Name</label> 
  </div>
  <div class="form-group form-floating my-2">
    <input type="text" class="form-control" placeholder="email" name="student_name" v-model="email">
    <label for="">Email</label>
  </div>
  <div class="form-group form-floating my-2">
    <input type="text" class="form-control" placeholder="Password" name="student_name" v-model="password">
    <label for="">Password</label>
  </div>
  <div class="form-group form-floating my-2">
    <input type="checkbox" name="" v-model="terms" id="">
    <label for="">Terms and  condition</label>
  </div>
  <div class="form-group my-2">
    <button class="btn btn-outline-primary" @click="signUp">Sign up</button>
  </div>
  <div>
    <p>{{terms}}</p>
  </div>
</div>
<slot></slot>
</template>

<script>
export default {
props:["title", "content"],
data(){
  return{
    name:"",
    email:"",
    password:"",
    terms:false
  }
},
methods:{
  signUp(){
    let userDetails ={
      name:this.name,
      email:this.email,
      password:this.password
    }
    localStorage.setItem("userDetails", JSON.stringify(userDetails))
    console.log(this.name + " "+ this.email+ " "+ this.password);
  }
}
}
</script>

<style>

</style>