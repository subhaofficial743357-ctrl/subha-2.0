<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Professional CV Maker</title>

<style>
*{
    box-sizing:border-box;
}

body{
    margin:0;
    font-family:Arial, sans-serif;
    background:#eef1f5;
    color:#222;
}

header{
    background:#17202a;
    color:white;
    text-align:center;
    padding:20px;
}

header h1{
    margin:0;
}

header p{
    margin:7px 0 0;
    color:#ddd;
}

.container{
    max-width:1200px;
    margin:20px auto;
    padding:15px;
    display:grid;
    grid-template-columns:360px 1fr;
    gap:20px;
}

.panel{
    background:white;
    padding:20px;
    border-radius:12px;
    box-shadow:0 4px 15px rgba(0,0,0,.12);
}

.panel h2{
    margin-top:0;
}

label{
    display:block;
    font-weight:bold;
    margin-top:13px;
    margin-bottom:5px;
    font-size:14px;
}

input,
textarea{
    width:100%;
    padding:10px;
    border:1px solid #ccc;
    border-radius:7px;
    font-size:14px;
}

textarea{
    min-height:80px;
    resize:vertical;
}

button{
    border:none;
    padding:12px 16px;
    border-radius:7px;
    cursor:pointer;
    font-weight:bold;
    margin-top:15px;
}

.download{
    background:#1769aa;
    color:white;
}

.reset{
    background:#ddd;
}

#resume{
    width:794px;
    min-height:1123px;
    background:white;
    margin:auto;
    display:grid;
    grid-template-columns:1fr 270px;
    box-shadow:0 5px 25px rgba(0,0,0,.15);
}

.left{
    padding:42px 35px;
}

.right{
    background:#f1f3f4;
    padding:42px 25px;
}

.name{
    font-size:30px;
    font-weight:800;
    margin:0;
}

.job{
    margin-top:6px;
    color:#555;
    text-transform:uppercase;
    letter-spacing:1px;
    font-size:13px;
}

.section{
    margin-top:28px;
}

.section h3{
    font-size:14px;
    letter-spacing:1.5px;
    border-bottom:2px solid #222;
    padding-bottom:7px;
}

.text{
    font-size:11px;
    line-height:1.6;
    white-space:pre-line;
}

.photo-wrap{
    text-align:center;
}

.photo{
    width:150px;
    height:180px;
    object-fit:cover;
    background:#ddd;
    border:1px solid #ccc;
}

.contact{
    font-size:11px;
    line-height:1.8;
    margin-top:15px;
}

.skills,
.certs{
    font-size:11px;
    line-height:1.8;
}

.actions{
    display:flex;
    gap:8px;
}

@media(max-width:900px){

    .container{
        grid-template-columns:1fr;
    }

    #resume{
        width:100%;
        min-height:auto;
    }

}

@media print{

    body{
        background:white;
    }

    header,
    .panel:first-child{
        display:none;
    }

    .container{
        display:block;
        margin:0;
        padding:0;
    }

    #resume{
        width:794px;
        min-height:1123px;
        box-shadow:none;
    }

    @page{
        size:A4;
        margin:0;
    }
}
</style>
</head>

<body>

<header>
    <h1>Professional CV Maker</h1>
    <p>Create Your Professional Resume</p>
</header>


<div class="container">


<!-- FORM -->

<div class="panel">

<h2>Enter Your Details</h2>

<label>Full Name</label>
<input id="name"
       value="YOUR NAME"
       oninput="updateCV()">

<label>Job Title</label>
<input id="job"
       value="Electrician / ITI Trainee"
       oninput="updateCV()">

<label>Profile Summary</label>
<textarea id="summary"
oninput="updateCV()">Motivated and hardworking professional with a strong willingness to learn and grow.</textarea>


<label>Phone</label>
<input id="phone"
placeholder="+91 XXXXX XXXXX"
oninput="updateCV()">


<label>Email</label>
<input id="email"
placeholder="your@email.com"
oninput="updateCV()">


<label>Address</label>
<textarea id="address"
placeholder="Village, District, State"
oninput="updateCV()"></textarea>


<label>Education</label>
<textarea id="education"
oninput="updateCV()">ITI - Electrician
12th / Higher Secondary
10th / Secondary</textarea>


<label>Work Experience</label>
<textarea id="experience"
oninput="updateCV()">Fresher / Entry Level
Basic Electrical Work
Wiring and Maintenance</textarea>


<label>Skills</label>
<textarea id="skills"
oninput="updateCV()">Electrical Wiring
Electrical Maintenance
Solar Panel Basics
Inverter & Battery
MS Office
Teamwork
Problem Solving</textarea>


<label>Certifications</label>
<textarea id="certifications"
oninput="updateCV()">ITI Certificate
Basic Computer Knowledge
Electrical Safety Training</textarea>


<label>Career Objective</label>
<textarea id="objective"
oninput="updateCV()">To obtain a suitable position where I can use my skills, learn new technologies and contribute to the growth of the organization.</textarea>


<label>Upload Photo</label>

<input type="file"
       accept="image/*"
       onchange="uploadPhoto(event)">


<div class="actions">

<button class="download"
onclick="window.print()">

📄 Download / Save PDF

</button>

<button class="reset"
onclick="resetCV()">

Reset

</button>

</div>

</div>


<!-- CV PREVIEW -->

<div class="panel">

<h2>Live CV Preview</h2>

<div id="resume">


<div class="left">

<h1 class="name"
id="cvName">
YOUR NAME
</h1>

<div class="job"
id="cvJob">
Electrician / ITI Trainee
</div>


<div class="section">

<h3>
PROFILE SUMMARY
</h3>

<div class="text"
id="cvSummary">
</div>

</div>


<div class="section">

<h3>
WORK EXPERIENCE
</h3>

<div class="text"
id="cvExperience">
</div>

</div>


<div class="section">

<h3>
EDUCATION
</h3>

<div class="text"
id="cvEducation">
</div>

</div>


<div class="section">

<h3>
CAREER OBJECTIVE
</h3>

<div class="text"
id="cvObjective">
</div>

</div>

</div>


<div class="right">


<div class="photo-wrap">

<img id="cvPhoto"
class="photo"
alt="Profile Photo">

</div>


<div class="contact"
id="cvContact">
</div>


<div class="section">

<h3>
KEY SKILLS
</h3>

<div class="skills"
id="cvSkills">
</div>

</div>


<div class="section">

<h3>
CERTIFICATIONS
</h3>

<div class="certs"
id="cvCertifications">
</div>

</div>


</div>

</div>

</div>

</div>


<script>

function getValue(id){

    return document.getElementById(id).value.trim();

}


function makeList(text){

    return text
    .split("\n")
    .filter(item => item.trim() !== "")
    .map(item => "• " + item.replace(/^•\s*/, ""))
    .join("<br>");

}


function updateCV(){

    document.getElementById("cvName").innerText =
        getValue("name") || "YOUR NAME";


    document.getElementById("cvJob").innerText =
        getValue("job") || "PROFESSIONAL";


    document.getElementById("cvSummary").innerText =
        getValue("summary");


    document.getElementById("cvExperience").innerHTML =
        makeList(getValue("experience"));


    document.getElementById("cvEducation").innerHTML =
        makeList(getValue("education"));


    document.getElementById("cvSkills").innerHTML =
        makeList(getValue("skills"));


    document.getElementById("cvCertifications").innerHTML =
        makeList(getValue("certifications"));


    document.getElementById("cvObjective").innerText =
        getValue("objective");


    let contact = "";

    if(getValue("phone")){

        contact += "☎ " +
        getValue("phone") +
        "<br>";

    }


    if(getValue("email")){

        contact += "✉ " +
        getValue("email") +
        "<br>";

    }


    if(getValue("address")){

        contact += "⌖ " +
        getValue("address");

    }


    document.getElementById("cvContact")
    .innerHTML = contact;

}


function uploadPhoto(event){

    let file =
        event.target.files[0];

    if(!file){

        return;

    }


    let reader =
        new FileReader();


    reader.onload =
        function(){

            document.getElementById("cvPhoto")
            .src = reader.result;

        };


    reader.readAsDataURL(file);

}


function resetCV(){

    location.reload();

}


updateCV();

</script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Professional CV Maker</title>

<style>
*{
    box-sizing:border-box;
}

body{
    margin:0;
    font-family:Arial, sans-serif;
    background:#eef1f5;
    color:#222;
}

header{
    background:#17202a;
    color:white;
    text-align:center;
    padding:20px;
}

header h1{
    margin:0;
}

header p{
    margin:7px 0 0;
    color:#ddd;
}

.container{
    max-width:1200px;
    margin:20px auto;
    padding:15px;
    display:grid;
    grid-template-columns:360px 1fr;
    gap:20px;
}

.panel{
    background:white;
    padding:20px;
    border-radius:12px;
    box-shadow:0 4px 15px rgba(0,0,0,.12);
}

.panel h2{
    margin-top:0;
}

label{
    display:block;
    font-weight:bold;
    margin-top:13px;
    margin-bottom:5px;
    font-size:14px;
}

input,
textarea{
    width:100%;
    padding:10px;
    border:1px solid #ccc;
    border-radius:7px;
    font-size:14px;
}

textarea{
    min-height:80px;
    resize:vertical;
}

button{
    border:none;
    padding:12px 16px;
    border-radius:7px;
    cursor:pointer;
    font-weight:bold;
    margin-top:15px;
}

.download{
    background:#1769aa;
    color:white;
}

.reset{
    background:#ddd;
}

#resume{
    width:794px;
    min-height:1123px;
    background:white;
    margin:auto;
    display:grid;
    grid-template-columns:1fr 270px;
    box-shadow:0 5px 25px rgba(0,0,0,.15);
}

.left{
    padding:42px 35px;
}

.right{
    background:#f1f3f4;
    padding:42px 25px;
}

.name{
    font-size:30px;
    font-weight:800;
    margin:0;
}

.job{
    margin-top:6px;
    color:#555;
    text-transform:uppercase;
    letter-spacing:1px;
    font-size:13px;
}

.section{
    margin-top:28px;
}

.section h3{
    font-size:14px;
    letter-spacing:1.5px;
    border-bottom:2px solid #222;
    padding-bottom:7px;
}

.text{
    font-size:11px;
    line-height:1.6;
    white-space:pre-line;
}

.photo-wrap{
    text-align:center;
}

.photo{
    width:150px;
    height:180px;
    object-fit:cover;
    background:#ddd;
    border:1px solid #ccc;
}

.contact{
    font-size:11px;
    line-height:1.8;
    margin-top:15px;
}

.skills,
.certs{
    font-size:11px;
    line-height:1.8;
}

.actions{
    display:flex;
    gap:8px;
}

@media(max-width:900px){

    .container{
        grid-template-columns:1fr;
    }

    #resume{
        width:100%;
        min-height:auto;
    }

}

@media print{

    body{
        background:white;
    }

    header,
    .panel:first-child{
        display:none;
    }

    .container{
        display:block;
        margin:0;
        padding:0;
    }

    #resume{
        width:794px;
        min-height:1123px;
        box-shadow:none;
    }

    @page{
        size:A4;
        margin:0;
    }
}
</style>
</head>

<body>

<header>
    <h1>Professional CV Maker</h1>
    <p>Create Your Professional Resume</p>
</header>


<div class="container">


<!-- FORM -->

<div class="panel">

<h2>Enter Your Details</h2>

<label>Full Name</label>
<input id="name"
       value="YOUR NAME"
       oninput="updateCV()">

<label>Job Title</label>
<input id="job"
       value="Electrician / ITI Trainee"
       oninput="updateCV()">

<label>Profile Summary</label>
<textarea id="summary"
oninput="updateCV()">Motivated and hardworking professional with a strong willingness to learn and grow.</textarea>


<label>Phone</label>
<input id="phone"
placeholder="+91 XXXXX XXXXX"
oninput="updateCV()">


<label>Email</label>
<input id="email"
placeholder="your@email.com"
oninput="updateCV()">


<label>Address</label>
<textarea id="address"
placeholder="Village, District, State"
oninput="updateCV()"></textarea>


<label>Education</label>
<textarea id="education"
oninput="updateCV()">ITI - Electrician
12th / Higher Secondary
10th / Secondary</textarea>


<label>Work Experience</label>
<textarea id="experience"
oninput="updateCV()">Fresher / Entry Level
Basic Electrical Work
Wiring and Maintenance</textarea>


<label>Skills</label>
<textarea id="skills"
oninput="updateCV()">Electrical Wiring
Electrical Maintenance
Solar Panel Basics
Inverter & Battery
MS Office
Teamwork
Problem Solving</textarea>


<label>Certifications</label>
<textarea id="certifications"
oninput="updateCV()">ITI Certificate
Basic Computer Knowledge
Electrical Safety Training</textarea>


<label>Career Objective</label>
<textarea id="objective"
oninput="updateCV()">To obtain a suitable position where I can use my skills, learn new technologies and contribute to the growth of the organization.</textarea>


<label>Upload Photo</label>

<input type="file"
       accept="image/*"
       onchange="uploadPhoto(event)">


<div class="actions">

<button class="download"
onclick="window.print()">

📄 Download / Save PDF

</button>

<button class="reset"
onclick="resetCV()">

Reset

</button>

</div>

</div>


<!-- CV PREVIEW -->

<div class="panel">

<h2>Live CV Preview</h2>

<div id="resume">


<div class="left">

<h1 class="name"
id="cvName">
YOUR NAME
</h1>

<div class="job"
id="cvJob">
Electrician / ITI Trainee
</div>


<div class="section">

<h3>
PROFILE SUMMARY
</h3>

<div class="text"
id="cvSummary">
</div>

</div>


<div class="section">

<h3>
WORK EXPERIENCE
</h3>

<div class="text"
id="cvExperience">
</div>

</div>


<div class="section">

<h3>
EDUCATION
</h3>

<div class="text"
id="cvEducation">
</div>

</div>


<div class="section">

<h3>
CAREER OBJECTIVE
</h3>

<div class="text"
id="cvObjective">
</div>

</div>

</div>


<div class="right">


<div class="photo-wrap">

<img id="cvPhoto"
class="photo"
alt="Profile Photo">

</div>


<div class="contact"
id="cvContact">
</div>


<div class="section">

<h3>
KEY SKILLS
</h3>

<div class="skills"
id="cvSkills">
</div>

</div>


<div class="section">

<h3>
CERTIFICATIONS
</h3>

<div class="certs"
id="cvCertifications">
</div>

</div>


</div>

</div>

</div>

</div>


<script>

function getValue(id){

    return document.getElementById(id).value.trim();

}


function makeList(text){

    return text
    .split("\n")
    .filter(item => item.trim() !== "")
    .map(item => "• " + item.replace(/^•\s*/, ""))
    .join("<br>");

}


function updateCV(){

    document.getElementById("cvName").innerText =
        getValue("name") || "YOUR NAME";


    document.getElementById("cvJob").innerText =
        getValue("job") || "PROFESSIONAL";


    document.getElementById("cvSummary").innerText =
        getValue("summary");


    document.getElementById("cvExperience").innerHTML =
        makeList(getValue("experience"));


    document.getElementById("cvEducation").innerHTML =
        makeList(getValue("education"));


    document.getElementById("cvSkills").innerHTML =
        makeList(getValue("skills"));


    document.getElementById("cvCertifications").innerHTML =
        makeList(getValue("certifications"));


    document.getElementById("cvObjective").innerText =
        getValue("objective");


    let contact = "";

    if(getValue("phone")){

        contact += "☎ " +
        getValue("phone") +
        "<br>";

    }


    if(getValue("email")){

        contact += "✉ " +
        getValue("email") +
        "<br>";

    }


    if(getValue("address")){

        contact += "⌖ " +
        getValue("address");

    }


    document.getElementById("cvContact")
    .innerHTML = contact;

}


function uploadPhoto(event){

    let file =
        event.target.files[0];

    if(!file){

        return;

    }


    let reader =
        new FileReader();


    reader.onload =
        function(){

            document.getElementById("cvPhoto")
            .src = reader.result;

        };


    reader.readAsDataURL(file);

}


function resetCV(){

    location.reload();

}


updateCV();

</script>

</body>
</html>
