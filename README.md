<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personal Portfolio Website By Sireesha</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://kit.fontawesome.com/c4254e24a8.js" crossorigin="anonymous"></script>
</head>
<body>
<div id="header">
    <div class="container">
        <nav>
            <img src="images/logo.png" class="logo">
            <ul id="sidemenu">
                <li><a href="#header">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#portfolio">Portfolio</a></li>
                <li><a href="#contact">Contact</a></li>
                <i class="fas fa-times" onclick="closemenu()"></i>
            </ul>
            <i class="fas fa-bars" onclick="openmenu()"></i>
        </nav>
        <div class="header-text">
            <p>Software  Developer/ Web Developer</p>

            <h1>Hi, I'm <span>Sireesha</span><br>From Banglore, India</h1>
        </div>
    </div>
</div>
<!-- -----------about---------- -->
<div id="about">
    <div class="container">
        <div class="row">
            <div class="about-col-1">
                <img src="images/user.png">
            </div>
            <div class="about-col-2">
                <h1 class="sub-title">About Me</h1>
                <p>I am Sireesha, a passionate Software Developer with a keen eye for engaging digital experiences. With expertise in web and app design, I transform ideas into visually stunning, user-centric solutions. Driven by creativity and innovation, I thrive on solving complex problems and delivering exceptional results.</p>

                <div class="tab-titles">
                    <p class="tab-links active-link" onclick="opentab('skills')">Skills</p>
                    <p class="tab-links" onclick="opentab('education')">Education</p>
                </div>
                <div class="tab-contents active-tab" id="skills">
                    <ul>
                        <li><span>Backend Developer</span><br>Developing Web/Apps</li>
                        <li><span>Web Development</span><br>Website Development</li>
                    </ul>
                </div>
                <div class="tab-contents" id="education">
                    <ul>
                        <li><span>2024</span><br>B-tech from Gitam University</li>

                        <li><span>2021</span><br>Intermediate from Narayana Jr College.</li>
                        <li><span>2019</span><br>10th Class from Narayana School.</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</div>
<!-- ---------services---------------- -->
<div id="services">
    <div class="container">
        <h1 class="sub-title">My Services</h1>
        <div class="services-list">
            <div>
                <i class="fas fa-code"></i>
                <h2>Web Design</h2>
                <p>Web design is the art of creating visually appealing, user-friendly interfaces that balance aesthetics with functionality to deliver an engaging online experience</p>
                <a href="#">Learn more</a>
            </div>
        </div>
    </div>
</div>
<!-- ----------portfolio------------ -->
<div id="portfolio">
    <div class="container">
        <h1 class="sub-title">My Work</h1>
        <div class="work-list">
            <div class="work">
                <img src="images/work-2.png">
                <div class="layer">
                    <h3>Password Manager Using Python </h3>
                    <p> Developed a system using python libraries where users can store new passwords, retrieve passwords, generate new passwords, and evaluate password strength.</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            <div class="work">
                <img src="images/work-3.png">
                <div class="layer">
                    <h3>Banking System</h3>
                    <p>Created a software application to manage various banking operations, including account management, transaction processing, balance inquiries, fund transfers, and user authentication.</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
        </div>
        <a href="#" class="btn">See more</a>
    </div>
</div>
<!-- ----------contact------------- -->
<div id="contact">
    <div class="container">
        <div class="row">
            <div class="contact-left">
                <h1 class="sub-title">Contact Me</h1>
                <p><i class="fas fa-paper-plane"></i>sireeshapalagiri45@gmail.com</p>
              
                <div class="social-icons">
                    <a href="https://facebook.com/"><i class="fab fa-facebook"></i></a>
                    <a href=""><i class="fab fa-twitter-square"></i></a>
                    <a href=""><i class="fab fa-instagram"></i></a>
                    <a href=""><i class="fab fa-linkedin"></i></a>
                </div>
                <a href="images/my-CV.pdf" download class="btn btn2">Download CV</a>
            </div>
            <div class="contact-right">
                <form name="submit-to-google-sheet">
                    <input type="text" name="Name" placeholder="Your Name" required>
                    <input type="email" name="Email" placeholder="Your Email" required>
                    <textarea name="Message" rows="6" placeholder="Your Message"></textarea>
                    <button type="submit" class="btn btn2">Submit</button>
                </form>
                <span id="msg"></span>
            </div>
        </div>
    </div>
    <div class="copyright">
        <p>Copyright © Sireesha.</p>
    </div>
</div>

<script>

    var tablinks = document.getElementsByClassName("tab-links");
    var tabcontents = document.getElementsByClassName("tab-contents");

    function opentab(tabname){
        for(tablink of tablinks){
            tablink.classList.remove("active-link");
        }
        for(tabcontent of tabcontents){
            tabcontent.classList.remove("active-tab");
        }
        event.currentTarget.classList.add("active-link");
        document.getElementById(tabname).classList.add("active-tab");
    }

</script>

<script>

    var sidemeu = document.getElementById("sidemenu");

    function openmenu(){
        sidemeu.style.right = "0";
    }
    function closemenu(){
        sidemeu.style.right = "-200px";
    }

</script>
<script>
    const scriptURL = '< add your own link here >' // Add your Google Script link
    const form = document.forms['submit-to-google-sheet']
    const msg = document.getElementById("msg")
  
    form.addEventListener('submit', e => {
      e.preventDefault()
      fetch(scriptURL, { method: 'POST', body: new FormData(form)})
        .then(response => {
            msg.innerHTML = "Message sent successfully"
            setTimeout(function(){
                msg.innerHTML = ""
            },5000)
            form.reset()
        })
        .catch(error => console.error('Error!', error.message))
    })
  </script>
</body>
</html>
