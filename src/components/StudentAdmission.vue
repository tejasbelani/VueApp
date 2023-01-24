<script>



export default {
    name: "StudentAdmissionVue",
    data() {
            return {
                errors: [],
                studnetlist: [],
                student: {
                fdetail: {},
                mdetail: {}
                },
                isvalid: true           
            }
        },
    methods:{
    checkForm()  {
    
      debugger;

      this.errors = [];
      this.isvalid= true;

      if (!this.student.fname) {
        this.errors.fname = 'First name is required.';
        this.isvalid = false;
      }
      if (!this.student.mname) {
        this.errors.mname = 'Middle name is required.';
        this.isvalid = false;
      }
      if (!this.student.lname) {
        this.errors.lname = 'Last name is required.';
        this.isvalid = false;
      }
      if (!this.student.address) {
        this.errors.address = 'Address is required.';
        this.isvalid = false;
      }
      if (!this.student.city) {
        this.errors.city = 'City is required.';
        this.isvalid = false;
      }
      if (!this.student.pin) {
        this.errors.pin = 'Pin is required.';
        this.isvalid = false;
      }
      if (!this.student.dob) {
        this.errors.dob = 'DOB is required.';
        this.isvalid = false;
      }
      if (!this.student.bplace) {
        this.errors.bplace = 'Birth place is required.';
        this.isvalid = false;
      }
      if (!this.student.language) {
        this.errors.language = 'Language is required.';
        this.isvalid = false;
      }
      if (!this.student.state) {
        this.errors.state = 'State is required.';
        this.isvalid = false;
      }
      if (!this.student.country) {        
        this.errors.country = 'Country is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.ffname) {
        this.errors.ffname = 'First name is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.fmname) {
        this.errors.fmname = 'Middle name is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.flname) {
        this.errors.flname = 'Last name is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.femail) {
        this.errors.femail = 'Email is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.fquali) {
        this.errors.fquali = 'Qualification is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.fedu) {
        this.errors.fedu = 'Education is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.fprofession) {
        this.errors.fprofession = 'Proffession is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.fdesign) {
        this.errors.fdesign = 'Designation is required.';
        this.isvalid = false;
      }
      if (!this.student.fdetail.fphone) {                
        this.errors.fphone = 'Phone is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.mfname) {
        this.errors.mfname = 'First name is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.mmname) {
        this.errors.mmname = 'Middle name is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.mlname) {
        this.errors.mlname = 'Last name is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.memail) {
        this.errors.memail = 'Email is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.mquali) {
        this.errors.mquali = 'Qualification is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.medu) {
        this.errors.medu = 'Education is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.mprofession) {
        this.errors.mprofession = 'Proffession is required.';
        this.isvalid = false;
      } 
      if (!this.student.mdetail.mdesign) {
        this.errors.mdesign = 'Designation is required.';
        this.isvalid = false;
      }
      if (!this.student.mdetail.mphone) {        
        this.errors.mphone = 'Phone is required.';
        this.isvalid = false;
      }

      if(this.isvalid) {
        this.studnetlist.push(this.student);
        // this.student.fdetail = {};
        // this.student.mdetail = {};
        // this.student = {};
      }

     if(!this.isvalid) {
        this.errors.push('Data is required.');
     }

    }
  }
}

</script>


<template>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

<table>
  <tr>
    <th>Details</th>
    <th> First Name </th>
    <th> Middle Name </th>
    <th> Last Name </th>
    <th> Addreess </th>
    <th> City </th>
    <th> PIN </th>
    <th> DOB </th>
    <th> Birth Place </th>
    <th> Language </th>
    <th> State</th>
    <th> Country</th>
  </tr>

  <tr v-for="stndt in studnetlist">
    <td> {{ stndt }} </td>
    <td> {{stndt.fname}}</td>
    <td> {{stndt.mname}}</td>
    <td> {{stndt.lname}}</td>
    <td> {{stndt.address}}</td>
    <td> {{stndt.city}}</td>
    <td> {{stndt.pin}}</td>
    <td> {{stndt.bplace}}</td>
    <td> {{stndt.dob}}</td>
    <td> {{stndt.language}}</td>
    <td> {{stndt.state}}</td>
    <td> {{stndt.country}}</td>
  </tr>

</table>



<center> <h2> Student Admission Form </h2> </center>

<div class="bd-example">

<input class="form-control col-md-12" type="text" value="Student Details" aria-label="Disabled input example" disabled="" readonly="">


<div style="text-align: center;color:red;" v-if="errors.length">
    
    <b>Please correct the following error(s):</b> <br/>
    <ul style="display: inline-block;">
      <li v-for="error in errors">{{ error }}</li>
    </ul>

</div>

<form>

<div class="row" style="margin-left:175px;">

        <div style="float:right" class="col-md-6"> 

            <div class="form-outline mb-6">
             <br/> First Name<label style="color:red">*</label><input type="text" maxlength="50" v-model="student.fname" placeholder="First Name" class="form-control  col-md-6" />
             <p v-if="errors.fname" style="color:red;"> First Name is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> Middle Name<label style="color:red">*</label> <input type="text" maxlength="50" v-model="student.mname" placeholder="Middle Name" class="form-control  col-md-6" />
             <p v-if="errors.mname" style="color:red;"> Middle Name is required !</p>
            </div>
            
            <div class="form-outline mb-6">
             <br/> Last Name<label style="color:red">*</label> <input type="text" maxlength="50" v-model="student.lname" placeholder="Last Name" class="form-control  col-md-6" />
             <p v-if="errors.lname" style="color:red;"> Last Name is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> Address<label style="color:red">*</label> <input type="text" maxlength="50" v-model="student.address" placeholder="Address" class="form-control  col-md-6" />
             <p v-if="errors.address" style="color:red;"> Address is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> City<label style="color:red">*</label> <input type="text" maxlength="50" v-model="student.city" placeholder="City" class="form-control  col-md-6" />
             <p v-if="errors.city" style="color:red;"> City Name is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> Pin<label style="color:red">*</label> <input type="number" maxlength="6" v-model="student.pin" placeholder="Pin" class="form-control  col-md-6" />
             <p v-if="errors.pin" style="color:red;"> Pin Name is required !</p>
            </div> <br/>

        </div>

        <div class="col-md-6"> 

            <div class="form-outline mb-6">
             <br/> DOB<label style="color:red">*</label> <input type="text" v-model="student.dob" maxlength="50" placeholder="DOB" class="form-control  col-md-6" />
             <p v-if="errors.dob" style="color:red;"> DOB is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> Birth Place<label style="color:red">*</label> <input type="text" v-model="student.bplace" maxlength="50" placeholder="Birth Place" class="form-control  col-md-6" />
             <p v-if="errors.bplace" style="color:red;"> Birth Place is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> Language<label style="color:red">*</label> <input type="text" v-model="student.language" maxlength="50" placeholder="Language" class="form-control  col-md-6" />
             <p v-if="errors.language" style="color:red;"> Language is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> State<label style="color:red">*</label> <input type="text" v-model="student.state" maxlength="50" placeholder="State" class="form-control  col-md-6" />
             <p v-if="errors.state" style="color:red;"> State is required !</p>
            </div>

            <div class="form-outline mb-6">
             <br/> Country<label style="color:red">*</label> <input type="text" v-model="student.country" maxlength="50" placeholder="Country" class="form-control  col-md-6" />
             <p v-if="errors.country" style="color:red;"> Country is required !</p>
            </div>

        </div>





    </div>

    <input class="form-control col-md-12" type="text" value="Parents Details" aria-label="Disabled input example" disabled="" readonly="">

    <div class="row" style="margin-left: 175px;">

    <div style="float:right;" class="col-md-6"> 

            <div class="form-outline mb-6">
            <br/> Father's First Name <input type="text" v-model="student.fdetail.ffname" placeholder="First Name" class="form-control  col-md-6" />
            <p v-if="errors.ffname" style="color:red;"> First Name is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Middle Name <input type="text" v-model="student.fdetail.fmname" placeholder="Middle Name" class="form-control  col-md-6" />
            <p v-if="errors.fmname" style="color:red;"> Middle Name is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Last Name <input type="text" v-model="student.fdetail.flname" placeholder="Last Name" class="form-control  col-md-6" />
            <p v-if="errors.flname" style="color:red;"> Last Name is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Email <input type="text" v-model="student.fdetail.femail" placeholder="Email" class="form-control  col-md-6" />
            <p v-if="errors.femail" style="color:red;"> Email is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Education <input type="text" v-model="student.fdetail.fedu" placeholder="Education" class="form-control  col-md-6" />
            <p v-if="errors.fedu" style="color:red;"> Education is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Qualification <input type="text" v-model="student.fdetail.fquali" placeholder="Qualification" class="form-control  col-md-6" />
            <p v-if="errors.fquali" style="color:red;"> Qualification is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Profession <input type="text" v-model="student.fdetail.fprofession" placeholder="Profession" class="form-control  col-md-6" />
            <p v-if="errors.fprofession" style="color:red;"> Profession is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Designation <input type="text" v-model="student.fdetail.fdesign" placeholder="Designation" class="form-control  col-md-6" />
            <p v-if="errors.fdesign" style="color:red;"> Designation is required !</p>
            </div>

            <div class="form-outline mb-6">
            <br/> Father's Phone <input type="number" maxlength="10" v-model="student.fdetail.fphone" placeholder="Phone" class="form-control  col-md-6" />
            <p v-if="errors.fphone" style="color:red;"> Phone is required !</p>
            </div>

</div>

<div style="float:right" class="col-md-6"> 

<div class="form-outline mb-6">
<br/> Mother's First Name <input type="text" v-model="student.mdetail.mfname" placeholder="First Name" class="form-control  col-md-6" />
<p v-if="errors.mfname" style="color:red;"> First Name is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Middle Name <input type="text" v-model="student.mdetail.mmname" placeholder="Middle Name" class="form-control  col-md-6" />
<p v-if="errors.mmname" style="color:red;"> Middle Name is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Last Name <input type="text" v-model="student.mdetail.mlname" placeholder="Last Name" class="form-control  col-md-6" />
<p v-if="errors.mlname" style="color:red;"> Last Name is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Email <input type="text" v-model="student.mdetail.memail" placeholder="Email" class="form-control  col-md-6" />
<p v-if="errors.memail" style="color:red;"> Email is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Education <input type="text" v-model="student.mdetail.medu" placeholder="Education" class="form-control  col-md-6" />
<p v-if="errors.medu" style="color:red;"> Education is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Qualification <input type="text" v-model="student.mdetail.mquali" placeholder="Qualification" class="form-control  col-md-6" />
<p v-if="errors.mquali" style="color:red;"> Qualification is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Profession <input type="text" v-model="student.mdetail.mprofession" placeholder="Profession" class="form-control  col-md-6" />
<p v-if="errors.mprofession" style="color:red;"> Profession is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Designation <input type="text" v-model="student.mdetail.mdesign" placeholder="Designation" class="form-control  col-md-6" />
<p v-if="errors.mdesign" style="color:red;"> Designation is required !</p>
</div>

<div class="form-outline mb-6">
<br/> Mother's Phone <input type="number" v-model="student.mdetail.mphone" maxlength="10" placeholder="Phone" class="form-control  col-md-6" />
<p v-if="errors.mphone" style="color:red;"> Phone is required !</p>
</div>




</div>
    </div>


<hr/>

<center> <button type="button"  @click="checkForm" class="btn btn-primary btn-block col-md-4 mb-4"> Submit </button> </center>



</form>

</div>



</template>