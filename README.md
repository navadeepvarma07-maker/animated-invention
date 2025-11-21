<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arnama Connect - Community Bulletin Board</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .hidden {
            display: none !important;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, #4e54c8, #8a64d0);
            color: white;
            padding: 1.5rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            z-index: 2;
        }
        
        .logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: #ffde59;
        }
        
        .logo-text {
            display: flex;
            flex-direction: column;
        }
        
        h1 {
            font-size: 2.2rem;
            font-weight: 700;
            line-height: 1.1;
        }
        
        .tagline {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-top: 5px;
        }
        
        .highlight {
            color: #ffde59;
        }
        
        .auth-buttons {
            display: flex;
            gap: 10px;
        }
        
        .auth-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .auth-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        #user-greeting {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .notification-bell {
            position: relative;
            cursor: pointer;
            font-size: 1.2rem;
        }
        
        .notification-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Navigation Styles */
        nav {
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            padding: 1rem 0;
        }
        
        nav li {
            margin-right: 1.5rem;
        }
        
        nav a {
            text-decoration: none;
            color: #4e54c8;
            font-weight: 500;
            transition: color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        nav a:hover {
            color: #8a64d0;
        }
        
        /* Section Styles */
        .section {
            padding: 3rem 0;
        }
        
        h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: #4e54c8;
            text-align: center;
        }
        
        h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #6c6c6c;
        }
        
        /* Bulletin Board Styles */
        .bulletin-prompt {
            text-align: center;
            padding: 2rem;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            margin-bottom: 2rem;
        }
        
        .cta-button {
            background-color: #4e54c8;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            margin-top: 1rem;
            transition: background-color 0.3s ease;
        }
        
        .cta-button:hover {
            background-color: #3a3fb3;
        }
        
        /* Form Styles */
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        input, textarea, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            font-family: inherit;
        }
        
        textarea {
            resize: vertical;
            min-height: 120px;
        }
        
        .submit-btn {
            background-color: #4e54c8;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            transition: background-color 0.3s ease;
        }
        
        .submit-btn:hover {
            background-color: #3a3fb3;
        }
        
        /* Posts Grid */
        .posts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 2rem;
        }
        
        .post-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
            transition: transform 0.3s ease;
            position: relative;
        }
        
        .post-card:hover {
            transform: translateY(-5px);
        }
        
        .post-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #4e54c8;
        }
        
        .post-content {
            margin-bottom: 1rem;
            color: #555;
        }
        
        .post-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: #888;
            margin-bottom: 10px;
        }
        
        .post-category {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        .category-general {
            background-color: #e0e0e0;
            color: #424242;
        }
        
        /* Post Actions */
        .post-actions {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid #eee;
        }
        
        .action-btn {
            background: none;
            border: none;
            color: #666;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 0.9rem;
            transition: color 0.3s ease;
        }
        
        .action-btn:hover {
            color: #4e54c8;
        }
        
        .action-btn.liked {
            color: #ff4757;
        }
        
        .action-btn.saved {
            color: #ffa502;
        }
        
        /* Modal Styles */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: #888;
        }
        
        /* Footer Styles */
        footer {
            background-color: #333;
            color: white;
            padding: 2rem 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .footer-nav {
            display: flex;
            gap: 20px;
            margin: 1rem 0;
        }
        
        .footer-nav a {
            color: #ddd;
            text-decoration: none;
        }
        
        .footer-nav a:hover {
            color: white;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo-container">
                    <div class="logo-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="logo-text">
                        <h1>Arnama <span class="highlight">Connect</span></h1>
                        <p class="tagline">Your community hub for sharing and connecting</p>
                    </div>
                </div>
                <div class="auth-buttons">
                    <button id="login-btn" class="auth-btn">Login</button>
                    <button id="register-btn" class="auth-btn">Register</button>
                    <div id="user-greeting" class="hidden">
                        <span>Hello, <span id="username-display"></span></span>
                        <button id="logout-btn" class="auth-btn">Logout</button>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <nav>
        <div class="container">
            <ul>
                <li><a href="#bulletin"><i class="fas fa-bullhorn"></i> Community Bulletin</a></li>
                <li id="dashboard-link" class="hidden"><a href="#dashboard"><i class="fas fa-tachometer-alt"></i> My Dashboard</a></li>
                <li id="messages-link" class="hidden"><a href="#messages"><i class="fas fa-comments"></i> Messages</a></li>
                <li id="users-link" class="hidden"><a href="#users"><i class="fas fa-user-friends"></i> Find Users</a></li>
            </ul>
        </div>
    </nav>

    <section id="bulletin" class="section">
        <div class="container">
            <h2>Community Bulletin</h2>
            <div id="post-form-container" class="hidden">
                <h3>Create a New Post</h3>
                <form id="post-form">
                    <div class="form-group">
                        <label for="post-title">Title</label>
                        <input type="text" id="post-title" required>
                    </div>
                    <div class="form-group">
                        <label for="post-content">Content</label>
                        <textarea id="post-content" rows="5" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="post-category">Category</label>
                        <select id="post-category">
                            <option value="general">General</option>
                            <option value="help">Help Needed</option>
                            <option value="offer">Offering Help</option>
                            <option value="event">Event</option>
                            <option value="sale">For Sale</option>
                        </select>
                    </div>
                    <button type="submit" class="submit-btn">Post to Community</button>
                </form>
            </div>
            <div id="login-prompt" class="bulletin-prompt">
                <p>Want to share something with the community?</p>
                <button id="prompt-login-btn" class="cta-button">Login to Post</button>
            </div>
            <div id="posts-container" class="posts-grid">
                <!-- Posts will be loaded here dynamically -->
            </div>
        </div>
    </section>

    <div id="auth-modal" class="modal hidden">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <div id="login-form">
                <h3>Login</h3>
                <form id="login-form-data">
                    <div class="form-group">
                        <label for="login-email">Email</label>
                        <input type="email" id="login-email" required>
                    </div>
                    <div class="form-group">
                        <label for="login-password">Password</label>
                        <input type="password" id="login-password" required>
                    </div>
                    <button type="submit" class="submit-btn">Login</button>
                </form>
                <p>Don't have an account? <a href="#" id="switch-to-register">Register here</a></p>
            </div>
            <div id="register-form" class="hidden">
                <h3>Register</h3>
                <form id="register-form-data">
                    <div class="form-group">
                        <label for="register-name">Full Name</label>
                        <input type="text" id="register-name" required>
                    </div>
                    <div class="form-group">
                        <label for="register-email">Email</label>
                        <input type="email" id="register-email" required>
                    </div>
                    <div class="form-group">
                        <label for="register-password">Password</label>
                        <input type="password" id="register-password" required>
                    </div>
                    <button type="submit" class="submit-btn">Register</button>
                </form>
                <p>Already have an account? <a href="#" id="switch-to-login">Login here</a></p>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <h3>Arnama Connect</h3>
                <div class="footer-nav">
                    <a href="#bulletin">Community Bulletin</a>
                    <a href="#">About Us</a>
                    <a href="#">Contact</a>
                    <a href="#">Privacy Policy</a>
                </div>
                <p>&copy; 2023 Arnama Connect. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // DOM Elements
        const loginBtn = document.getElementById('login-btn');
        const registerBtn = document.getElementById('register-btn');
        const logoutBtn = document.getElementById('logout-btn');
        const userGreeting = document.getElementById('user-greeting');
        const usernameDisplay = document.getElementById('username-display');
        const dashboardLink = document.getElementById('dashboard-link');
        const messagesLink = document.getElementById('messages-link');
        const usersLink = document.getElementById('users-link');
        const authModal = document.getElementById('auth-modal');
        const closeModalBtn = document.querySelector('.close-modal');
        const switchToRegister = document.getElementById('switch-to-register');
        const switchToLogin = document.getElementById('switch-to-login');
        const loginForm = document.getElementById('login-form');
        const registerForm = document.getElementById('register-form');
        const loginFormData = document.getElementById('login-form-data');
        const registerFormData = document.getElementById('register-form-data');
        const postFormContainer = document.getElementById('post-form-container');
        const loginPrompt = document.getElementById('login-prompt');
        const promptLoginBtn = document.getElementById('prompt-login-btn');
        const postForm = document.getElementById('post-form');
        const postsContainer = document.getElementById('posts-container');

        // Current user state
        let currentUser = null;

        // Event Listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Check if user is logged in (from localStorage)
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                updateUIForLoggedInUser();
            }
            
            // Load posts
            loadPosts();
            
            // Set up event listeners
            setupEventListeners();
            
            // Initialize sample data
            initializeSampleData();
        });

        function setupEventListeners() {
            // Auth buttons
            loginBtn.addEventListener('click', showLoginModal);
            registerBtn.addEventListener('click', showRegisterModal);
            logoutBtn.addEventListener('click', logout);
            promptLoginBtn.addEventListener('click', showLoginModal);
            
            // Modal interactions
            closeModalBtn.addEventListener('click', closeAuthModal);
            switchToRegister.addEventListener('click', switchToRegisterForm);
            switchToLogin.addEventListener('click', switchToLoginForm);
            
            // Form submissions
            loginFormData.addEventListener('submit', handleLogin);
            registerFormData.addEventListener('submit', handleRegister);
            postForm.addEventListener('submit', handlePostSubmit);
            
            // Close modal when clicking outside
            window.addEventListener('click', function(event) {
                if (event.target === authModal) {
                    closeAuthModal();
                }
            });
        }

        function initializeSampleData() {
            // Check if we need to create sample data
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            
            // If no posts exist, create a sample post
            if (posts.length === 0) {
                const samplePost = {
                    id: Date.now(),
                    title: "Welcome to Arnama Connect!",
                    content: "Welcome to our community hub! This is a place where neighbors can connect, share resources, and support each other. Feel free to post about events, items for sale, or ask for help.",
                    category: "general",
                    author: "MNV",
                    authorId: 1,
                    date: new Date().toLocaleDateString(),
                    likes: 0,
                    likedBy: [],
                    comments: [],
                    media: []
                };
                
                posts.push(samplePost);
                localStorage.setItem('posts', JSON.stringify(posts));
            }
            
            // Check if we need to create sample users
            const users = JSON.parse(localStorage.getItem('users')) || [];
            if (users.length === 0) {
                const sampleUser = {
                    id: 1,
                    name: "MNV",
                    email: "mnv@example.com",
                    password: "password",
                    joinDate: new Date().toLocaleDateString()
                };
                
                users.push(sampleUser);
                localStorage.setItem('users', JSON.stringify(users));
            }
        }

        function showLoginModal() {
            authModal.classList.remove('hidden');
            loginForm.classList.remove('hidden');
            registerForm.classList.add('hidden');
        }

        function showRegisterModal() {
            authModal.classList.remove('hidden');
            registerForm.classList.remove('hidden');
            loginForm.classList.add('hidden');
        }

        function closeAuthModal() {
            authModal.classList.add('hidden');
            // Clear form fields
            document.getElementById('login-email').value = '';
            document.getElementById('login-password').value = '';
            document.getElementById('register-name').value = '';
            document.getElementById('register-email').value = '';
            document.getElementById('register-password').value = '';
        }

        function switchToRegisterForm(e) {
            e.preventDefault();
            loginForm.classList.add('hidden');
            registerForm.classList.remove('hidden');
        }

        function switchToLoginForm(e) {
            e.preventDefault();
            registerForm.classList.add('hidden');
            loginForm.classList.remove('hidden');
        }

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            // Simple validation
            if (!email || !password) {
                alert('Please fill in all fields');
                return;
            }
            
            // Check if user exists in localStorage
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            const user = users.find(u => u.email === email && u.password === password);
            
            if (user) {
                // Login successful
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                updateUIForLoggedInUser();
                closeAuthModal();
                alert('Login successful!');
            } else {
                alert('Invalid email or password');
            }
        }

        function handleRegister(e) {
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            
            // Simple validation
            if (!name || !email || !password) {
                alert('Please fill in all required fields');
                return;
            }
            
            // Check if user already exists
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            if (users.some(user => user.email === email)) {
                alert('User with this email already exists');
                return;
            }
            
            // Create new user
            const newUser = {
                id: Date.now(),
                name,
                email,
                password,
                joinDate: new Date().toLocaleDateString()
            };
            
            // Save user
            users.push(newUser);
            localStorage.setItem('users', JSON.stringify(users));
            
            // Auto login
            currentUser = newUser;
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            updateUIForLoggedInUser();
            closeAuthModal();
            alert('Registration successful! You are now logged in.');
        }

        function logout() {
            currentUser = null;
            localStorage.removeItem('currentUser');
            updateUIForLoggedOutUser();
            alert('You have been logged out');
        }

        function updateUIForLoggedInUser() {
            // Update auth buttons
            loginBtn.classList.add('hidden');
            registerBtn.classList.add('hidden');
            userGreeting.classList.remove('hidden');
            usernameDisplay.textContent = currentUser.name;
            
            // Show post form and hide login prompt
            postFormContainer.classList.remove('hidden');
            loginPrompt.classList.add('hidden');
            
            // Show dashboard and messages links
            dashboardLink.classList.remove('hidden');
            messagesLink.classList.remove('hidden');
            usersLink.classList.remove('hidden');
            
            // Reload posts to show action buttons
            loadPosts();
        }

        function updateUIForLoggedOutUser() {
            // Update auth buttons
            loginBtn.classList.remove('hidden');
            registerBtn.classList.remove('hidden');
            userGreeting.classList.add('hidden');
            
            // Hide post form and show login prompt
            postFormContainer.classList.add('hidden');
            loginPrompt.classList.remove('hidden');
            
            // Hide dashboard and messages links
            dashboardLink.classList.add('hidden');
            messagesLink.classList.add('hidden');
            usersLink.classList.add('hidden');
            
            // Reload posts to hide action buttons
            loadPosts();
        }

        function loadPosts() {
            // Clear posts container
            postsContainer.innerHTML = '';
            
            // Get posts from localStorage
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            
            if (posts.length === 0) {
                postsContainer.innerHTML = '<p>No posts yet. Be the first to share something with the community!</p>';
                return;
            }
            
            // Display each post
            posts.forEach(post => {
                const postElement = createPostElement(post);
                postsContainer.appendChild(postElement);
            });
        }

        function createPostElement(post) {
            const postDiv = document.createElement('div');
            postDiv.className = 'post-card';
            
            const categoryClass = `category-${post.category}`;
            
            // Check if current user is the author
            const isCurrentUserAuthor = currentUser && post.authorId === currentUser.id;
            
            // Check if current user has liked the post
            const isLiked = currentUser && post.likedBy && post.likedBy.includes(currentUser.id);
            
            // Check if current user has saved the post
            const savedPosts = JSON.parse(localStorage.getItem(`savedPosts_${currentUser ? currentUser.id : ''}`)) || [];
            const isSaved = savedPosts.includes(post.id);
            
            postDiv.innerHTML = `
                <h3 class="post-title">${post.title}</h3>
                <p class="post-content">${post.content}</p>
                <div class="post-meta">
                    <span class="post-author">By ${post.author}</span>
                    <span class="post-date">${post.date}</span>
                </div>
                <span class="post-category ${categoryClass}">${post.category}</span>
                
                <!-- Post Actions -->
                <div class="post-actions">
                    <button class="action-btn like-btn ${isLiked ? 'liked' : ''}" data-post-id="${post.id}">
                        <i class="fas fa-heart"></i>
                        <span class="like-count">${post.likes || 0}</span>
                    </button>
                    <button class="action-btn comment-btn" data-post-id="${post.id}">
                        <i class="fas fa-comment"></i>
                        <span class="comment-count">${post.comments ? post.comments.length : 0}</span>
                    </button>
                    <button class="action-btn save-btn ${isSaved ? 'saved' : ''}" data-post-id="${post.id}">
                        <i class="fas fa-bookmark"></i>
                        <span>Save</span>
                    </button>
                    <button class="action-btn share-btn" data-post-id="${post.id}">
                        <i class="fas fa-share-alt"></i>
                        <span>Share</span>
                    </button>
                </div>
            `;
            
            // Add event listeners to action buttons
            if (currentUser) {
                // Like button
                const likeBtn = postDiv.querySelector('.like-btn');
                likeBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    toggleLike(postId);
                });
                
                // Save button
                const saveBtn = postDiv.querySelector('.save-btn');
                saveBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    toggleSavePost(postId);
                });
                
                // Share button
                const shareBtn = postDiv.querySelector('.share-btn');
                shareBtn.addEventListener('click', function() {
                    const postId = parseInt(this.getAttribute('data-post-id'));
                    alert('Share functionality would be implemented here for post: ' + postId);
                });
            }
            
            return postDiv;
        }

        function toggleLike(postId) {
            if (!currentUser) return;
            
            const posts = JSON.parse(localStorage.getItem('posts')) || [];
            const postIndex = posts.findIndex(p => p.id === postId);
            
            if (postIndex === -1) return;
            
            const post = posts[postIndex];
            
            // Initialize likes and likedBy if they don't exist
            if (!post.likes) post.likes = 0;
            if (!post.likedBy) post.likedBy = [];
            
            // Check if user already liked the post
            const userIndex = post.likedBy.indexOf(currentUser.id);
            
            if (userIndex === -1) {
                // Like the post
                post.likes++;
                post.likedBy.push(currentUser.id);
            } else {
                // Unlike the post
                post.likes--;
                post.likedBy.splice(userIndex, 1);
            }
            
            // Save updated posts
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Reload posts
            loadPosts();
        }

        function toggleSavePost(postId) {
            if (!currentUser) return;
            
            const savedPosts = JSON.parse(localStorage.getItem(`savedPosts_${currentUser.id}`)) || [];
            const postIndex = savedPosts.indexOf(postId);
            
            if (postIndex === -1) {
                // Save the post
                savedPosts.push(postId);
            } else {
                // Unsave the post
                savedPosts.splice(postIndex, 1);
            }
            
            // Save updated saved posts
            localStorage.setItem(`savedPosts_${currentUser.id}`, JSON.stringify(savedPosts));
            
            // Reload posts
            loadPosts();
        }

        function handlePostSubmit(e) {
            e.preventDefault();
            
            if (!currentUser) {
                alert('Please log in to post');
                return;
            }
            
            const title = document.getElementById('post-title').value;
            const content = document.getElementById('post-content').value;
            const category = document.getElementById('post-category').value;
            
            // Create new post
            const newPost = {
                id: Date.now(),
                title,
                content,
                category,
                author: currentUser.name,
                authorId: currentUser.id,
                date: new Date().toLocaleDateString(),
                likes: 0,
                likedBy: [],
                comments: [],
                media: []
            };
            
            // Save post
            const posts = JSON.parse(localStorage.getItem('posts') || '[]');
            posts.unshift(newPost); // Add to beginning of array
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Reload posts
            loadPosts();
            
            // Clear form
            postForm.reset();
            
            alert('Your post has been published!');
        }

        // Initialize the page
        window.addEventListener('load', function() {
            // Check if user is logged in
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                updateUIForLoggedInUser();
            }
            
            // Load posts
            loadPosts();
        });
    </script>
</body>
</html>
