<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Artivora - AI Image Prompt Generator</title>

<meta name="description" content="Artivora is a free AI Image Prompt Generator. Create realistic, cinematic, 3D and creative prompts in seconds.">

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:Arial,Helvetica,sans-serif;
    background:#f6f7fb;
    color:#171717;
}

header{
    background:white;
    padding:18px 7%;
    display:flex;
    justify-content:space-between;
    align-items:center;
    border-bottom:1px solid #e5e7eb;
}

.logo{
    font-size:27px;
    font-weight:800;
}

.logo span{
    color:#7c3aed;
}

.header-text{
    color:#666;
    font-size:14px;
}

.hero{
    text-align:center;
    padding:55px 20px 35px;
}

.hero h1{
    font-size:42px;
    margin-bottom:15px;
}

.hero h1 span{
    color:#7c3aed;
}

.hero p{
    max-width:650px;
    margin:auto;
    color:#666;
    font-size:17px;
    line-height:1.6;
}

.container{
    max-width:850px;
    margin:15px auto 60px;
    padding:0 20px;
}

.card{
    background:white;
    padding:28px;
    border-radius:18px;
    box-shadow:0 8px 30px rgba(0,0,0,.07);
}

label{
    display:block;
    margin:17px 0 8px;
    font-weight:bold;
}

input,select{
    width:100%;
    padding:14px;
    border:1px solid #d1d5db;
    border-radius:10px;
    font-size:15px;
    background:white;
}

input:focus,select:focus{
    outline:none;
    border-color:#7c3aed;
}

.generate{
    width:100%;
    margin-top:25px;
    padding:16px;
    border:none;
    border-radius:10px;
    background:#7c3aed;
    color:white;
    font-size:17px;
    font-weight:bold;
    cursor:pointer;
}

.generate:hover{
    opacity:.9;
}

.result{
    display:none;
    margin-top:28px;
}

.result h2{
    margin-bottom:12px;
}

#prompt{
    background:#f3f4f6;
    padding:18px;
    border-radius:12px;
    line-height:1.7;
    font-size:15px;
    word-wrap:break-word;
}

.copy{
    width:100%;
    margin-top:12px;
    padding:14px;
    border:none;
    border-radius:10px;
    background:#171717;
    color:white;
    font-size:16px;
    font-weight:bold;
    cursor:pointer;
}

footer{
    text-align:center;
    padding:25px;
    color:#777;
    font-size:14px;
}

@media(max-width:600px){

    .hero{
        padding-top:40px;
    }

    .hero h1{
        font-size:31px;
    }

    .hero p{
        font-size:15px;
    }

    .card{
        padding:20px;
    }
}
</style>
</head>

<body>

<header>
    <div class="logo">Art<span>ivora</span></div>
    <div class="header-text">AI Creator Tools</div>
</header>

<section class="hero">

    <h1>AI Image <span>Prompt Generator</span></h1>

    <p>
        Create detailed, cinematic and creative AI image prompts
        in seconds. Perfect for creators, designers and AI artists.
    </p>

</section>

<div class="container">

<div class="card">

    <label>What do you want to create?</label>

    <input
        id="subject"
        type="text"
        placeholder="Example: A giant dragon in a green village"
    >

    <label>Image Style</label>

    <select id="style">
        <option>Realistic</option>
        <option>Cinematic</option>
        <option>Photorealistic</option>
        <option>3D Render</option>
        <option>Anime</option>
        <option>Fantasy</option>
    </select>

    <label>Background</label>

    <select id="background">
        <option>Lush green landscape</option>
        <option>Mysterious forest</option>
        <option>Modern city</option>
        <option>Futuristic city</option>
        <option>Mountain landscape</option>
        <option>Studio background</option>
        <option>Desert landscape</option>
    </select>

    <label>Lighting</label>

    <select id="lighting">
        <option>Cinematic lighting</option>
        <option>Golden hour lighting</option>
        <option>Dramatic lighting</option>
        <option>Soft natural lighting</option>
        <option>Neon lighting</option>
        <option>Studio lighting</option>
    </select>

    <label>Aspect Ratio</label>

    <select id="ratio">
        <option>16:9</option>
        <option>9:16</option>
        <option>4:5</option>
        <option>1:1</option>
    </select>

    <button class="generate" onclick="generatePrompt()">
        ✨ Generate Prompt
    </button>

    <div class="result" id="result">

        <h2>Your AI Image Prompt</h2>

        <div id="prompt"></div>

        <button class="copy" onclick="copyPrompt()">
            📋 Copy Prompt
        </button>

    </div>

</div>
</div>

<footer>
    © 2026 Artivora. Free AI Image Prompt Generator.
</footer>

<script>

function generatePrompt(){

    const subject =
        document.getElementById("subject").value.trim();

    const style =
        document.getElementById("style").value;

    const background =
        document.getElementById("background").value;

    const lighting =
        document.getElementById("lighting").value;

    const ratio =
        document.getElementById("ratio").value;

    if(subject === ""){
        alert("Please enter what you want to create.");
        return;
    }

    const finalPrompt =
        subject +
        ", " +
        style +
        " style, highly detailed, ultra realistic details, " +
        background +
        ", " +
        lighting +
        ", professional composition, realistic textures, " +
        "sharp focus, atmospheric depth, cinematic photography, " +
        "high quality, visually stunning, 8K details, " +
        ratio +
        " aspect ratio";

    document.getElementById("prompt").innerText =
        finalPrompt;

    document.getElementById("result").style.display =
        "block";
}

function copyPrompt(){

    const text =
        document.getElementById("prompt").innerText;

    navigator.clipboard.writeText(text)
    .then(function(){

        alert("Prompt copied successfully!");

    })
    .catch(function(){

        alert("Please select and copy the prompt manually.");

    });
}

</script>

</body>
</html>
