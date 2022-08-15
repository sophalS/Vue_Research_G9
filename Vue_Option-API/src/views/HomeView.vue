<template>
  <div class="take-main">

  <form action="" @submit.prevent="addUser">
      <input type="text" placeholder="Name" v-model="names"><br>
      <input type="text" placeholder="Email" v-model="email"><br>
       <label>
    </label>
      <div class="st-up"><button class="adders" type="submit">Adds</button></div>
  </form>
  </div>

<div class="user-page">All users here</div>
<div class="user-header">
  <div class="card-user" v-for="(items, index) in dataUser" :key="items">
  <div class="user-id">{{index+1}}</div>
    <div class="photo-user">{{items.nameUser}}</div>
    <div class="store-user">
      <div class="user-names">{{items.nameUser}}</div>
      <div class="user-email">{{items.emailUser}}</div>
    </div>
    <div class="btns">
      <button class="adds">Edit</button>
      <button class="deletes" @click="removeUser(index)">Delete</button>
    </div>
  </div>

</div>
</template>
<script>
// @ is an alias to /src


export default {
    data(){
      return{
        dataUser:[],
        names:'',
        email:''
      }
    },
    
    methods:{

      addUser(){
        let newUser={
          nameUser:this.names,
          emailUser:this.email
        }
        this.dataUser.push(newUser);
        this.names='';
        this.email=''
      },

      removeUser(index){

        this.dataUser.splice(index,1)

      }

    },

  mounted(){

    // axios.get("http://127.0.0.1:8000/api/users").then((respons)=>{
    //   this.dataUser=respons.data;
    //   console.log(respons.data)
    // })

  }

  }

</script>
<style scoped>
.take-main{
  display: flex;
  justify-content: center;
  align-items: center;
}
form{
  width: 600px;
  justify-content: center;
  text-align: center;
  align-items: center;
  margin: auto;
  background: blue;
  border-radius: 5px;
  padding: 10px 10px;
}

input[type="text"]{
  width: 480px;
  height: 4vh;
  border: 1px solid;
  margin: 2px 2px;
  border-radius: 5px;
  font-size: 16px;
}
input[type="file"]{
  width: 120px;
  margin: 5px 5px;
  height: 3vh;
  border: 1px solid;
  margin: 5px 5px;
  border-radius: 5px;
  font-size: 20px;
}

label{
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
}

.st-up{
  display: flex;
  justify-content: center;
  text-align: center;
}
.adders{
  width: 110px;
  height: 4vh;
  border: solid 1px;
  margin: 5px 5px;
  border-radius: 5px;
  color: white;
  font-size: 17px;
  background: rgb(37, 168, 37);
}

.user-page{
  display: flex;
  text-align: center;
  justify-content: center;
  align-items: center;
  font-size: 20px;
}
  .user-header{
    text-align: center;
    align-items: center;
    margin: auto;
    justify-content: center;
  }
  .card-user{
    margin: auto;
    width: 600px;
    border-radius: 5px;
    background: rgb(58, 184, 193);
  }
  .user-id{
    display: flex;
    margin: 5px 5px;
    font-size: 20px;
    width: 30px;
    display: flex;
    justify-content: center;
    text-align: center;
    align-items: center;
    border-radius: 20px;
    border: solid 1px red;
  }

.photo-user{
  width: 100px;
  height: 11vh;
  display: flex;
  align-items: center;
  margin: 10px auto 10px;
  border-radius: 100px;
  text-align: center;
  font-size: 17px;
  color: white;
  justify-content: center;
  background: blue;
}
.user-names,.user-email{
  font-size: 20px;
}


.btns{
  width: 500px;
  display: flex;
  align-items: center;
  margin: auto;
  justify-content: space-between;
}
.adds,.deletes{
  height: 4vh;
  width: 100px;
  display: flex;
  font-size: 16px;
  color: white;
  justify-content: center;
  text-align: center;
  align-items: center;
  margin: 10px 10px;
  border-radius: 5px;
  border: 1px solid;
}
.adds{
  background: green;
}

.deletes{
  background: red;
}
  </style>

<!-- <style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style> -->
