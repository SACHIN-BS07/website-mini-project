# website-mini-project  : http://127.0.0.1:5500/index.html
mini portfolio website is help to get a pratical knowledge in web development . it make me excite ..
code :
html :
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Portfolio</title>
  <link rel="stylesheet" href="index.css">
  <link rel="stylesheet" href="http://localhost:3000/contact">
</head>
<body>
  <header>
    <h1>SACHIN B S</h1>
    <p>Web Developer | Designer | Engineer</p>
  </header>

  <section id="about">
    <h2>About Me</h2>
    <p>I'm a passionate web developer with a knack for creating stunning websites and applications.</p>
  </section>

  <section id="projects">
    <h2>Projects</h2>
    <div class="project">
      <h3>Portfolio website
      </h3>
      <p>A personal portfolio website showcasing my skills and projects.</p>
      <a href="#">View Project</a>
    </div>
  </section>

  <section id="contact">
  <h2>Contact</h2>
  <form id="contactForm">
    <input type="text" name="name" placeholder="Your Name" required><br>
    <input type="email" name="email" placeholder="Your Email" required><br>
    <textarea name="message" placeholder="Your Message" required></textarea><br>
    <button type="submit" style="background-color: green; border-radius: 5px; color: white;">Send</button>
  </form>
  <p id="formStatus"></p>
</section>
<script>
document.getElementById('contactForm').addEventListener('submit', async function(e) {
  e.preventDefault();
  const form = e.target;
  const data = {
    name: form.name.value,
    email: form.email.value,
    message: form.message.value
  };
  const res = await fetch('http://localhost:3000/contact', {
    method: 'POST',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify(data)
  });
  document.getElementById('formStatus').textContent = res.ok ? 'Message sent!' : 'Error sending message.';
});
</script>

  <section id="details">
    <h2>Contact : 7676091187</h2>
    <p>Email: sachinbs107@gmail.com</p>
    <p>LinkedIn : <a href="#">https://www.linkedin.com/in/sachin-b-s-7a54b8333/</a> | GitHub : <a href="#">https://github.com/SACHIN-BS07</a></p>
  </section>

  <footer>
    <p>© 2025 SACHIN B S</p>
  </footer>

  css: 
  /* Reset some default styles */
body, h1, h2, h3, p, a {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Arial, sans-serif;
  color: #222;
}

body {
  background: #f7f9fb;
  line-height: 1.6;
}

header {
  background: linear-gradient(90deg, #4f8cff 0%, #6ed6ff 100%);
  color: #fff;
  text-align: center;
  padding: 2rem 0 1rem 0;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05);
}

header h1 {
  font-size: 2.5rem;
  letter-spacing: 2px;
  margin-bottom: 0.5rem;
}

header p {
  font-size: 1.2rem;
  font-weight: 300;
}

section {
  max-width: 700px;
  margin: 2rem auto;
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.07);
  padding: 2rem;
}

h2 {
  color: #4f8cff;
  margin-bottom: 1rem;
  font-size: 1.6rem;
  border-bottom: 2px solid #e3eafc;
  padding-bottom: 0.3rem;
}

.project {
  margin-bottom: 1.5rem;
  padding: 1rem;
  border: 1px solid #e3eafc;
  border-radius: 8px;
  background: #f5faff;
}

.project h3 {
  color: #222;
  margin-bottom: 0.5rem;
}

.project a {
  display: inline-block;
  margin-top: 0.5rem;
  color: #4f8cff;
  text-decoration: none;
  font-weight: 500;
  border-bottom: 1px solid #4f8cff;
  transition: color 0.2s;
}

.project a:hover {
  color: #1a5fd6;
  border-bottom: 1px solid #1a5fd6;
}

#contact p, #contact a {
  font-size: 1rem;
  color: #333;
}

#contact a {
  color: #4f8cff;
  text-decoration: none;
  border-bottom: 1px dotted #4f8cff;
  transition: border-bottom 0.2s;
}

#contact a:hover {
  border-bottom: 1px solid #4f8cff;
}

footer {
  text-align: center;
  padding: 1rem 0;
  background: #e3eafc;
  color: #4f8cff;
  font-size: 1rem;
  margin-top: 2rem;
  border-radius: 0 0 12px 12px;
}
javascript:
const express = require('express');
const cors = require('cors');
const app = express();
app.use(cors());
app.use(express.json());

app.post('/contact', (req, res) => {
  const { name, email, message } = req.body;
  // Here, you can save to a database, send an email, etc.
  console.log('Contact form submitted:', name, email, message);
  res.status(200).json({ message: 'Received' });
});

app.listen(3000, () => console.log('Server running on http://localhost:3000'));
  
</body>
</html>
