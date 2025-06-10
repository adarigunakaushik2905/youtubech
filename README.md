<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="description" content="Syllabus announcement and exam support for 3rd Semester B.Sc AI by Justbrainify YouTube Channel" />
    <meta name="keywords" content="B.Sc AI syllabus, Justbrainify exam support, Machine Learning study resources" />
    <title>Justbrainify - Ignite Your Learning</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Exo+2:wght@400;600&display=swap" rel="stylesheet" />
    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-firestore-compat.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Exo 2', sans-serif;
            background: linear-gradient(135deg, #1a1a3d 0%, #2a2a5e 100%);
            color: #e0e0e0;
            line-height: 1.6;
            scroll-behavior: smooth;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            background: rgba(0, 0, 0, 0.8);
            position: sticky;
            top: 0;
            width: 100%;
            z-index: 1000;
            border-bottom: 2px solid #39FF14;
        }

        .logo {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.5rem;
            color: #39FF14;
            text-transform: uppercase;
        }

        nav a {
            color: #00BFFF;
            text-decoration: none;
            margin: 0 1rem;
            font-weight: 600;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #39FF14;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: url('https://source.unsplash.com/random/1920x1080/?technology,ai') no-repeat center/cover;
            background-attachment: fixed;
            padding: 1rem;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 3rem;
            color: #39FF14;
            text-shadow: 0 0 10px rgba(57, 255, 20, 0.7);
        }

        .hero h2 {
            font-size: 1.75rem;
            margin: 0.5rem 0 1rem;
            color: #00BFFF;
        }

        .subscribe-btn {
            background: #39FF14;
            color: #1a1a3d;
            padding: 0.5rem 1rem;
            text-decoration: none;
            font-weight: 600;
            border-radius: 5px;
            margin: 1rem 0;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .subscribe-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px rgba(57, 255, 20, 0.7);
        }

        .intro-video {
            max-width: 600px;
            width: 100%;
            border: 2px solid #00BFFF;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 191, 255, 0.5);
            transition: transform 0.3s;
        }

        .intro-video:hover {
            transform: scale(1.02);
        }

        .section {
            padding: 3rem 1rem;
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .section h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 2rem;
            color: #00BFFF;
            margin-bottom: 1rem;
        }

        .section ul {
            list-style: none;
            margin: 1rem 0;
        }

        .section ul li {
            font-size: 1.1rem;
            margin: 0.5rem 0;
            padding-left: 1.5rem;
            position: relative;
        }

        .section ul li a {
            color: #00BFFF;
            text-decoration: none;
        }

        .section ul li a:hover {
            color: #39FF14;
        }

        #contact form {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        #contact textarea {
            width: 100%;
            height: 100px;
            padding: 0.5rem;
            background: #2a2a5e;
            border: 2px solid #00BFFF;
            color: #e0e0e0;
            font-family: 'Exo 2', sans-serif;
            resize: none;
        }

        #contact button {
            background: #39FF14;
            color: #1a1a3d;
            padding: 0.5rem;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: transform 0.3s;
        }

        #contact button:hover {
            transform: scale(1.05);
        }

        #comments-list {
            margin-top: 1rem;
        }

        .comment {
            background: #2a2a5e;
            padding: 0.5rem;
            margin: 0.5rem 0;
            border-left: 4px solid #00BFFF;
        }

        .success-message, .error-message {
            display: none;
            margin: 0.5rem 0;
            padding: 0.5rem;
            border-radius: 5px;
            text-align: center;
        }

        .success-message {
            background: #39FF14;
            color: #1a1a3d;
        }

        .error-message {
            background: #ff4d4d;
            color: #e0e0e0;
        }

        footer {
            text-align: center;
            padding: 1rem;
            background: rgba(0, 0, 0, 0.8);
            border-top: 2px solid #39FF14;
        }

        footer p {
            margin: 0.25rem 0;
        }

        footer a {
            color: #00BFFF;
            text-decoration: none;
        }

        footer a:hover {
            color: #39FF14;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }

            .hero h2 {
                font-size: 1.25rem;
            }

            .intro-video {
                max-width: 100%;
                height: 200px;
            }

            header {
                flex-direction: column;
                padding: 0.5rem;
            }

            nav a {
                margin: 0.5rem;
            }

            .section h2 {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="logo">Justbrainify</div>
        <nav>
            <a href="#home">Home</a>
            <a href="#syllabus">Syllabus</a>
            <a href="#resources">Resources</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <h1>🎓 3rd Semester B.Sc AI</h1>
        <h2>📢 Syllabus Announcement + Exam Support by Justbrainify YouTube Channel</h2>
        <a href="http://www.youtube.com/@BRAINIFYSPARK" target="_blank" class="subscribe-btn">🔔 Subscribe & Stay Ahead!</a>
        <iframe class="intro-video" width="600" height="340" src= "Brainify  Empowering Your AI Learning Journey_free.mp4" title="Justbrainify Intro Video - Empowering Your AI Learning Journey" frameborder="0" allowfullscreen loading="lazy"></iframe>
    </section>

    <!-- Syllabus Section -->
    <section id="syllabus" class="section">
        <h2>🧠 Subjects Covered</h2>
        <ul>
            <li>📘 Machine Learning Basics</li>
            <li>📊 Data Warehousing & Business Analytics</li>
            <li>🤖 Knowledge Representation & Reasoning</li>
            <li>🧪 Software Construction & Testing</li>
            <li>🌍 Environmental Science (GE)</li>
            <li>🐍 Python for Data Science Lab</li>
            <li>🧠 Machine Learning Lab</li>
        </ul>
    </section>

    <!-- Resources Section -->
    <section id="resources" class="section">
        <h2>📚 Coming This Semester on Justbrainify</h2>
        <ul>
            <li>✅ Complete Syllabus Overview</li>
            <li>✅ Topic-by-Topic Study Videos</li>
            <li>✅ Important Questions for Exams</li>
            <li>✅ Detailed Notes in PDF Format (<a href="https://via.placeholder.com/3-sem.pdf" download>Download Syllabus</a>)</li>
            <li>✅ All Resources Linked in Video Descriptions</li>
            <li>✅ One-Stop Website Access for All Materials</li>
        </ul>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
        <h2>💬 Have Doubts? Get in Touch!</h2>
        <p>📧 Email: <a href="mailto:justbrainifyofficial@gmail.com">justbrainifyofficial@gmail.com</a></p>
        <p>🌐 Website: (Coming Soon)</p>
        <h3>Ask Your Doubts</h3>
        <form id="comment-form">
            <textarea id="comment-input" placeholder="Type your doubt here..." required></textarea>
            <button type="submit">Submit</button>
        </form>
        <div class="success-message" id="success-message">Comment posted successfully!</div>
        <div class="error-message" id="error-message">Failed to post comment. Please try again.</div>
        <div id="comments-list">
            <h3>Comments</h3>
            <!-- Comments will be dynamically added here -->
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>🔔 Subscribe & Stay Ahead! | 💬 Doubts? Ask in Comments</p>
        <p>🌐 Visit Website: (Coming Soon) | 📧 Email: <a href="mailto:justbrainifyofficial@gmail.com">justbrainifyofficial@gmail.com</a></p>
        <p>© 2025 Justbrainify. Igniting Minds, One Lesson at a Time.</p>
    </footer>

    <script>
        // Initialize Firebase (Replace with your Firebase config)
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_AUTH_DOMAIN",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_STORAGE_BUCKET",
            messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
            appId: "YOUR_APP_ID"
        };

        firebase.initializeApp(firebaseConfig);
        const db = firebase.firestore();

        document.getElementById('comment-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const commentInput = document.getElementById('comment-input');
            const commentText = commentInput.value.trim();
            const successMessage = document.getElementById('success-message');
            const errorMessage = document.getElementById('error-message');

            if (commentText) {
                db.collection('comments').add({
                    text: commentText,
                    date: new Date().toISOString(),
                    timestamp: firebase.firestore.FieldValue.serverTimestamp()
                })
                .then(() => {
                    commentInput.value = '';
                    successMessage.style.display = 'block';
                    errorMessage.style.display = 'none';
                    setTimeout(() => successMessage.style.display = 'none', 3000);
                })
                .catch(error => {
                    console.error('Error adding comment: ', error);
                    errorMessage.style.display = 'block';
                    successMessage.style.display = 'none';
                    setTimeout(() => errorMessage.style.display = 'none', 3000);
                });
            }
        });

        function displayComments(comments) {
            const commentsList = document.getElementById('comments-list');
            commentsList.innerHTML = '<h3>Comments</h3>';
            comments.forEach(comment => {
                const commentData = comment.data();
                const commentDiv = document.createElement('div');
                commentDiv.classList.add('comment');
                const date = new Date(commentData.date).toLocaleString('en-IN', { timeZone: 'Asia/Kolkata' });
                commentDiv.innerHTML = `<p>${commentData.text}</p><small>Posted on: ${date}</small>`;
                commentsList.appendChild(commentDiv);
            });
        }

        db.collection('comments')
            .orderBy('timestamp', 'desc')
            .onSnapshot(snapshot => {
                const comments = [];
                snapshot.forEach(doc => comments.push(doc));
                displayComments(comments);
            }, error => console.error('Error fetching comments: ', error));
    </script>
</body>
</html>
