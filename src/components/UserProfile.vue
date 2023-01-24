<script>

export default {
      name: "UserProfile",
      data() {
            return {
                user:{},
                userlist:[],
                userDisplaylist:[],
                isInValid: false                
            }
        },
        methods: {
        addusers() {
                if(this.user.uid == undefined || this.user.uname == undefined || this.user.uaddress == undefined)
                {            
                        this.isInValid = true;
                }
                else
                {                   
                    this.userlist.push(this.user);
                    this.user={};
                }
            }
        },
    };
</script>

<template>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">


<div class="row">

    <div class="col-md-6"> 

         <form>

                <div style="text-align:center">
                <h2> User Profile </h2>
                </div>

                <!-- Email input -->
                <div class="form-outline mb-4 col-md-3">
                <input type="text" id="form2Example1" placeholder="ID" v-model="user.uid" class="form-control" />
                </div>

                <!-- Password input -->
                <div class="form-outline mb-4 col-md-3">
                <input type="text" id="form2Example2" placeholder="Name" v-model="user.uname" class="form-control" />
                </div>

                <!-- Password input -->
                <div class="form-outline mb-4 col-md-3">
                <input type="text" id="form2Example2" placeholder="Address" v-model="user.uaddress" class="form-control" />
                </div>

                <!-- 2 column grid layout for inline styling -->


                <!-- Submit button -->
                <button type="button" @click="addusers()" class="btn btn-primary btn-block col-md-3 mb-4">Submit</button>
                
                <p v-if="this.isInValid"> Please enter valid data.  </p> 


        </form>


    </div>

        <div class="col-md-6"  :data="userlist"> 

            <table border="1px">
                <tr>
                    <th>ID</th>
                    <th>Name</th>
                    <th>Address</th> 
                </tr>

                <tr v-if="this.userlist.length <= 0">
                    <td colspan="3">No data available</td>
                </tr>

                <tr v-for="u in userlist">
                <td> {{u.uid}}</td>
                <td>{{u.uname}}</td>
                <td>{{u.uaddress}}</td>
                </tr>

            </table>

        </div>

</div>

</template>