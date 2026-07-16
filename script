let passwordAttempts = 0;

document.getElementById("appointmentForm").addEventListener("submit", function(event){

    event.preventDefault();

    let valid = true;

    // Clear previous errors
    document.querySelectorAll(".error").forEach(function(item){
        item.innerHTML = "";
    });

    document.getElementById("successMessage").innerHTML = "";

    // Get values
    let fname = document.getElementById("fname").value.trim();
    let lname = document.getElementById("lname").value.trim();
    let email = document.getElementById("email").value.trim();
    let password = document.getElementById("password").value;
    let confirm = document.getElementById("confirmPassword").value;
    let department = document.getElementById("department").value;
    let description = document.getElementById("description").value.trim();

    // Name Validation
    let namePattern = /^[A-Za-z]+$/;

    if(fname==""){
        document.getElementById("fnameError").innerHTML="First Name is required";
        valid=false;
    }
    else if(!namePattern.test(fname)){
        document.getElementById("fnameError").innerHTML="Alphabets only";
        valid=false;
    }

    if(lname==""){
        document.getElementById("lnameError").innerHTML="Last Name is required";
        valid=false;
    }
    else if(!namePattern.test(lname)){
        document.getElementById("lnameError").innerHTML="Alphabets only";
        valid=false;
    }

    // Email Validation
    let emailPattern=/^[^ ]+@[^ ]+\.[a-z]{2,3}$/;

    if(email==""){
        document.getElementById("emailError").innerHTML="Email required";
        valid=false;
    }
    else if(!emailPattern.test(email)){
        document.getElementById("emailError").innerHTML="Invalid Email";
        valid=false;
    }

    // Password Validation
    if(password==""){
        document.getElementById("passwordError").innerHTML="Password required";
        valid=false;
    }

    if(confirm==""){
        document.getElementById("confirmError").innerHTML="Confirm Password";
        valid=false;
    }
    else if(password!==confirm){

        passwordAttempts++;

        document.getElementById("confirmError").innerHTML="Password doesn't match";

        valid=false;

        if(passwordAttempts>=3){
            document.getElementById("password").disabled=true;
            document.getElementById("confirmPassword").disabled=true;
            document.getElementById("confirmError").innerHTML="Maximum 3 attempts reached.";
        }
    }

    // Gender Validation
    let gender=document.querySelector('input[name="gender"]:checked');

    if(!gender){
        document.getElementById("genderError").innerHTML="Select Gender";
        valid=false;
    }

    // Checkbox Validation
    let services=document.querySelectorAll('input[name="service"]:checked');

    if(services.length==0){
        document.getElementById("serviceError").innerHTML="Select at least one service";
        valid=false;
    }

    // Department Validation
    if(department==""){
        document.getElementById("departmentError").innerHTML="Select Department";
        valid=false;
    }

    // Description Validation
    if(description.length<20){
        document.getElementById("descriptionError").innerHTML="Minimum 20 characters required";
        valid=false;
    }

    // Success
    if(valid){
        document.getElementById("successMessage").innerHTML=
        "Appointment Registration Completed Successfully!";
    }

});