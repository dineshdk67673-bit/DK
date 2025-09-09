<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1.0">
  <title>Student Portfolio & Projects</title>
  <link rel="stylesheet" href="style.css">

  <!-- EmailJS SDK -->
  <script type="text/javascript" src="https://cdn.emailjs.com/dist/email.min.js"></script>
  <script>
    (function(){
      emailjs.init("YOUR_PUBLIC_KEY"); // replace with your EmailJS Public Key
    })();
  </script>

  <style>
    body { font-family: Arial, sans-serif; margin: 0; }
    header, footer { background:#333; color:#fff; padding:1rem; text-align:center; }
    nav { background:#444; display:flex; justify-content:center; flex-wrap:wrap; }
    nav a { color:#fff; padding:1rem; text-decoration:none; }
    nav a:hover { background:#666; }
    section { padding:40px 20px; }
    h2 { margin-bottom:20px; }
    .hero { background:#f4f4f4; padding:60px 20px; text-align:center; }
    .hero h1 span { color:darkred; }
    .projects .project-grid { display:grid; grid-template-columns:repeat(auto-fit, minmax(200px, 1fr)); gap:20px; }
    .project-card { background:#fff; padding:20px; border-radius:10px; box-shadow:0 0 5px rgba(0,0,0,0.2); }
    /* Quiz styles */
    .quiz-container { background:white; padding:20px; border-radius:10px; max-width:500px; margin:auto; box-shadow:0 0 10px rgba(0,0,0,0.2);}
    .quiz-container ul { list-style:none; margin-bottom:20px; }
    .quiz-container li { margin:10px 0; }
    .quiz-container button { background:#333; color:white; padding:10px 15px; border:none; border-radius:5px; cursor:pointer; }
    .quiz-container button:hover { background:#555; }
    /* Blog */
    .post { background:white; padding:15px; margin-bottom:20px; border-radius:8px; box-shadow:0 0 5px rgba(0,0,0,0.1); }
    .post h2 { margin:0 0 10px; }
    .post small { color:gray; font-size:12px; }
    /* Responsive website section */
    .web-container { display:grid; grid-template-columns:3fr 1fr; gap:1rem; }
    .content, .sidebar { padding:1rem; border-radius:8px; }
    .content { background:#f4f4f4; }
    .sidebar { background:#e2e2e2; }
    @media(max-width:768px){ .web-container{ grid-template-columns:1fr; } }
  </style>
</head>
<body>

  <!-- Navbar -->
  <header>
    <h1>MR__ DINESHKUMAR - Portfolio & Projects</h1>
  </header>
  <nav>
    <a href="#portfolio">Portfolio</a>
    <a href="#quiz">Quiz App</a>
    <a href="#blog">Blog</a>
    <a href="#website">Responsive Website</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Portfolio Section -->
  <section id="portfolio" class="hero">
    <div class="hero-content">
      <h1>Hello, I'm <span>MR__ DINESHKUMAR</span></h1>
      <p>I am the student</p>
      <a href="#projects" class="btn">View My Work</a>
    </div>
  </section>

  <section id="about" class="about">
    <h2>About Me</h2>
    <div>
      <img src="IMG_20250301_175116.jpg" alt="Profile Photo" width="150">
      <p>I am a student enthusiastic about technology and design. I love building interactive, user-friendly web applications and exploring new tools in the tech world.</p>
    </div>
  </section>

  <section id="projects" class="projects">
    <h2>My Projects</h2>
    <div class="project-grid">
      <div class="project-card"><h3>Project 1</h3><p>A simple responsive website.</p></div>
      <div class="project-card"><h3>Project 2</h3><p>JavaScript-based quiz app.</p></div>
      <div class="project-card"><h3>Project 3</h3><p>Personal blog with CMS.</p></div>
    </div>
  </section>

  <!-- Quiz App Section -->
  <section id="quiz">
    <h2>Quiz App</h2>
    <div class="quiz-container" id="quiz-box">
      <h2 id="question">Question text</h2>
      <ul>
        <li><label><input type="radio" name="answer" class="answer" id="a"> <span id="a_text">Answer A</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="b"> <span id="b_text">Answer B</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="c"> <span id="c_text">Answer C</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="d"> <span id="d_text">Answer D</span></label></li>
      </ul>
      <button id="submit">Submit</button>
      <div class="result" id="result"></div>
    </div>
  </section>

  <!-- Blog Section -->
  <section id="blog">
    <h2>My Blog</h2>
    <div class="container" id="postsContainer"></div>
  </section>

  <!-- Responsive Website Section -->
  <section id="website">
    <h2>Responsive Website Demo</h2>
    <div class="web-container">
      <div class="content">
        <h3>Main Content</h3>
        <p>This is the main content area. Resize the window to see the responsive effect. On smaller screens, the sidebar will move below the main content.</p>
      </div>
      <div class="sidebar">
        <h3>Sidebar</h3>
        <p>This is a sidebar with some extra information or links.</p>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <form id="contact-form">
      <input type="text" id="name" name="user_name" placeholder="Your Name" required>
      <input type="email" id="email" name="user_email" placeholder="Your Email" required>
      <textarea id="message" name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="form-status"></p>
  </section>

  <footer>
    <p>&copy; 2025 MR__ DINESHKUMAR | All rights reserved</p>
  </footer>

  <!-- JavaScript for Quiz + Blog -->
  <script>
    // Quiz App
    const quizData = [
      {question: "Who discovered HTML?",a: "Charles Babbage",b: "Tim Berners-Lee",c: "Bill Gates",d: "Dennis Ritchie",correct: "b"},
      {question: "Which language is used for styling web pages?",a: "HTML",b: "JQuery",c: "CSS",d: "XML",correct: "c"},
      {question: "Which is not a JavaScript Framework?",a: "React",b: "Angular",c: "Vue",d: "Django",correct: "d"},
      {question: "Which is used for database?",a: "PHP",b: "MySQL",c: "HTML",d: "CSS",correct: "b"}
    ];
    const quiz = document.getElementById("quiz-box");
    const answerEls = document.querySelectorAll(".answer");
    const questionEl = document.getElementById("question");
    const a_text = document.getElementById("a_text");
    const b_text = document.getElementById("b_text");
    const c_text = document.getElementById("c_text");
    const d_text = document.getElementById("d_text");
    const submitBtn = document.getElementById("submit");
    const resultEl = document.getElementById("result");
    let currentQuiz = 0; let score = 0;
    loadQuiz();
    function loadQuiz(){ deselectAnswers(); const currentQuizData = quizData[currentQuiz]; questionEl.innerText = currentQuizData.question; a_text.innerText = currentQuizData.a; b_text.innerText = currentQuizData.b; c_text.innerText = currentQuizData.c; d_text.innerText = currentQuizData.d; }
    function getSelected(){ let answer; answerEls.forEach(el=>{ if(el.checked){ answer=el.id; } }); return answer; }
    function deselectAnswers(){ answerEls.forEach(el=> el.checked=false); }
    submitBtn.addEventListener("click",()=>{ const answer=getSelected(); if(answer){ if(answer===quizData[currentQuiz].correct){ score++; } currentQuiz++; if(currentQuiz<quizData.length){ loadQuiz(); } else { quiz.innerHTML=`<h2>You answered correctly ${score}/${quizData.length} questions.</h2><button onclick="location.reload()">Restart</button>`; } } });

    // Blog
    function loadPosts() {
      const postsContainer = document.getElementById("postsContainer");
      const posts = JSON.parse(localStorage.getItem("blogPosts")) || [];
      postsContainer.innerHTML = "";
      posts.reverse().forEach(post => {
        const postEl = document.createElement("div");
        postEl.classList.add("post");
        postEl.innerHTML = `<h2>${post.title}</h2><small>${new Date(post.date).toLocaleString()}</small><p>${post.content}</p>`;
        postsContainer.appendChild(postEl);
      });
    }
    loadPosts();
  </script>
</body>
</html>
