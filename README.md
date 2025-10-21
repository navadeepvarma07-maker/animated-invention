# animated-invention
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arnama Connect</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
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
        }
        
        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 0.5rem;
        }
        
        h1 {
            font-size: 2.2rem;
            font-weight: 700;
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
        
        /* Media Upload Styles */
        .media-upload {
            margin-bottom: 1.5rem;
        }
        
        .upload-area {
            border: 2px dashed #ccc;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 15px;
        }
        
        .upload-area:hover {
            border-color: #4e54c8;
            background-color: #f9f9ff;
        }
        
        .upload-icon {
            font-size: 3rem;
            color: #4e54c8;
            margin-bottom: 10px;
        }
        
        .media-preview {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }
        
        .preview-item {
            position: relative;
            width: 100px;
            height: 100px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        .preview-item img, .preview-item video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .remove-media {
            position: absolute;
            top: 5px;
            right: 5px;
            background: rgba(255, 255, 255, 0.8);
            border: none;
            border-radius: 50%;
            width: 24px;
            height: 24px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
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
        
        .post-media {
            margin-bottom: 1rem;
        }
        
        .post-media img, .post-media video {
            width: 100%;
            border-radius: 8px;
            max-height: 300px;
            object-fit: cover;
        }
        
        .post-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: #888;
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
        
        .category-help {
            background-color: #ffebee;
            color: #c62828;
        }
        
        .category-offer {
            background-color: #e8f5e9;
            color: #2e7d32;
        }
        
        .category-event {
            background-color: #e3f2fd;
            color: #1565c0;
        }
        
        .category-sale {
            background-color: #fff8e1;
            color: #f57f17;
        }
        
        /* Dashboard Styles */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }
        
        .dashboard-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
        }
        
        .dashboard-btn {
            background-color: #8a64d0;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 4px;
            cursor: pointer;
            margin-top: 1rem;
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
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }
            
            nav ul {
                flex-direction: column;
                gap: 10px;
            }
            
            .posts-grid {
                grid-template-columns: 1fr;
            }
            
            .dashboard-grid {
                grid-template-columns: 1fr;
            }
            
            .media-preview {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-top">
                <h1><span class="highlight"> ARNAMA </span> Connect</h1>
                <div class="auth-buttons">
                    <button id="login-btn" class="auth-btn">Login</button>
                    <button id="register-btn" class="auth-btn">Register</button>
                    <div id="user-greeting" class="hidden">
                        <span id="username-display"></span>
                        <button id="logout-btn" class="auth-btn">Logout</button>
                    </div>
                </div>
            </div>
            <p>Your local community hub for events, news, and resources</p>
        </div>
    </header>

    <nav>
        <div class="container">
            <ul>
                <li><a href="#bulletin">Community Bulletin</a></li>
                <li id="dashboard-link" class="hidden"><a href="#dashboard">My Dashboard</a></li>
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
                    
                    <!-- Media Upload Section -->
                    <div class="media-upload">
                        <label>Add Photos or Videos</label>
                        <div class="upload-area" id="media-drop-area">
                            <div class="upload-icon">
                                <i class="fas fa-cloud-upload-alt"></i>
                            </div>
                            <p>Drag & drop files here or click to browse</p>
                            <input type="file" id="media-upload" multiple accept="image/*,video/*" style="display: none;">
                        </div>
                        <div class="media-preview" id="media-preview"></div>
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

    <section id="dashboard" class="section hidden">
        <div class="container">
            <h2>My Dashboard</h2>
            <div class="dashboard-grid">
                <div class="dashboard-card">
                    <h3>My Profile</h3>
                    <div id="profile-info">
                        <p><strong>Name:</strong> <span id="profile-name"></span></p>
                        <p><strong>Email:</strong> <span id="profile-email"></span></p>
                        <p><strong>Member since:</strong> <span id="join-date"></span></p>
                    </div>
                    <button id="edit-profile-btn" class="dashboard-btn">Edit Profile</button>
                </div>
                <div class="dashboard-card">
                    <h3>My Posts</h3>
                    <div id="user-posts">
                        <!-- User's posts will be loaded here -->
                    </div>
                </div>
                <div class="dashboard-card">
                    <h3>Saved Posts</h3>
                    <div id="saved-posts">
                        <!-- Saved posts will be loaded here -->
                    </div>
                </div>
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
                    <div class="form-group">
                        <label for="register-address">Street Address (optional)</label>
                        <input type="text" id="register-address">
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
                <h3>Neighborhood Connect</h3>
                <div class="footer-nav">
                    <a href="#bulletin">Community Bulletin</a>
                    <a href="#">About Us</a>
                    <a href="#">Contact</a>
                    <a href="#">Privacy Policy</a>
                </div>
                <p>&copy; 2023 Neighborhood Connect. All rights reserved.</p>
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
        const dashboardSection = document.getElementById('dashboard');
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
        const profileName = document.getElementById('profile-name');
        const profileEmail = document.getElementById('profile-email');
        const joinDate = document.getElementById('join-date');
        const userPostsContainer = document.getElementById('user-posts');
        const savedPostsContainer = document.getElementById('saved-posts');
        const editProfileBtn = document.getElementById('edit-profile-btn');
        
        // Media upload elements
        const mediaDropArea = document.getElementById('media-drop-area');
        const mediaUpload = document.getElementById('media-upload');
        const mediaPreview = document.getElementById('media-preview');

        // Sample posts data with media examples
        const samplePosts = [
            {
                id: 1,
                title: "Community Garden Workday",
                content: "We're having a workday at the community garden this Saturday from 9am-12pm. All are welcome! Bring gloves and water.",
                category: "event",
                author: "Green Thumb Gary",
                date: "2023-10-15",
                media: [
                    {type: 'image', url: 'https://images.unsplash.com/photo-1590602847861-f357a9332bbc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&q=80'}
                ]
            },
            {
                id: 2,
                title: "Moving Boxes Available",
                content: "I have a bunch of moving boxes in good condition. Free to anyone who can pick them up. Various sizes available.",
                category: "offer",
                author: "Moving Mary",
                date: "2023-10-14",
                media: [
                    {type: 'image', url: 'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&q=80'}
                ]
            },
            {
                id: 3,
                title: "Yard Sale This Weekend",
                content: "Big yard sale on Saturday from 8am-2pm at 123 Maple Street. Furniture, kids' clothes, books, and more!",
                category: "sale",
                author: "Sale Sally",
                date: "2023-10-13",
                media: [
                    {type: 'image', url: 'https://images.unsplash.com/photo-1577702312572-5bb9328a7e1c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&q=80'}
                ]
            },
            {
                id: 4,
                title: "Neighborhood Block Party",
                content: "Join us for the annual neighborhood block party this Sunday! Food, music, and games for all ages.",
                category: "event",
                author: "Party Pete",
                date: "2023-10-12",
                media: [
                    {type: 'image', url: 'https://images.unsplash.com/photo-1535016120720-40c646be5580?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=600&q=80'}
                ]
            }
        ];

        // Current user state
        let currentUser = null;
        let mediaFiles = [];

        // Event Listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Check if user is logged in (from localStorage)
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                updateUIForLoggedInUser();
            }
            
            // Load sample posts
            loadPosts();
            
            // Set up event listeners
            setupEventListeners();
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
            
            // Navigation
            dashboardLink.addEventListener('click', showDashboard);
            
            // Media upload
            mediaDropArea.addEventListener('click', () => mediaUpload.click());
            mediaUpload.addEventListener('change', handleMediaUpload);
            mediaDropArea.addEventListener('dragover', (e) => {
                e.preventDefault();
                mediaDropArea.style.borderColor = '#4e54c8';
                mediaDropArea.style.backgroundColor = '#f9f9ff';
            });
            mediaDropArea.addEventListener('dragleave', () => {
                mediaDropArea.style.borderColor = '#ccc';
                mediaDropArea.style.backgroundColor = 'transparent';
            });
            mediaDropArea.addEventListener('drop', handleMediaDrop);
            
            // Close modal when clicking outside
            window.addEventListener('click', function(event) {
                if (event.target === authModal) {
                    closeAuthModal();
                }
            });
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
            document.getElementById('register-address').value = '';
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
            const address = document.getElementById('register-address').value;
            
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
                address,
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
            
            // Show dashboard link
            dashboardLink.classList.remove('hidden');
            
            // Update dashboard if visible
            if (window.location.hash === '#dashboard') {
                showDashboard();
            }
            
            // Load user's posts
            loadUserPosts();
        }

        function updateUIForLoggedOutUser() {
            // Update auth buttons
            loginBtn.classList.remove('hidden');
            registerBtn.classList.remove('hidden');
            userGreeting.classList.add('hidden');
            
            // Hide post form and show login prompt
            postFormContainer.classList.add('hidden');
            loginPrompt.classList.remove('hidden');
            
            // Hide dashboard link
            dashboardLink.classList.add('hidden');
            
            // Hide dashboard if visible
            dashboardSection.classList.add('hidden');
        }

        function handleMediaUpload(e) {
            const files = e.target.files;
            handleFiles(files);
        }

        function handleMediaDrop(e) {
            e.preventDefault();
            mediaDropArea.style.borderColor = '#ccc';
            mediaDropArea.style.backgroundColor = 'transparent';
            
            const files = e.dataTransfer.files;
            handleFiles(files);
        }

        function handleFiles(files) {
            for (let i = 0; i < files.length; i++) {
                const file = files[i];
                const fileType = file.type.split('/')[0];
                
                if (fileType === 'image' || fileType === 'video') {
                    mediaFiles.push(file);
                    
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        const previewItem = document.createElement('div');
                        previewItem.className = 'preview-item';
                        
                        if (fileType === 'image') {
                            previewItem.innerHTML = `
                                <img src="${e.target.result}" alt="Preview">
                                <button class="remove-media" data-index="${mediaFiles.length - 1}">&times;</button>
                            `;
                        } else {
                            previewItem.innerHTML = `
                                <video src="${e.target.result}" controls></video>
                                <button class="remove-media" data-index="${mediaFiles.length - 1}">&times;</button>
                            `;
                        }
                        
                        mediaPreview.appendChild(previewItem);
                        
                        // Add event listener to remove button
                        previewItem.querySelector('.remove-media').addEventListener('click', function() {
                            const index = parseInt(this.getAttribute('data-index'));
                            mediaFiles.splice(index, 1);
                            mediaPreview.removeChild(previewItem);
                            
                            // Update data-index for remaining items
                            const removeButtons = mediaPreview.querySelectorAll('.remove-media');
                            removeButtons.forEach((btn, idx) => {
                                btn.setAttribute('data-index', idx);
                            });
                        });
                    };
                    
                    reader.readAsDataURL(file);
                } else {
                    alert('Please only upload images or videos');
                }
            }
        }

        function loadPosts() {
            // Clear posts container
            postsContainer.innerHTML = '';
            
            // Get posts from localStorage or use sample posts
            const posts = JSON.parse(localStorage.getItem('posts')) || samplePosts;
            
            // Display each post
            posts.forEach(post => {
                const postElement = createPostElement(post);
                postsContainer.appendChild(postElement);
            });
            
            // Save posts to localStorage if using sample posts
            if (!localStorage.getItem('posts')) {
                localStorage.setItem('posts', JSON.stringify(posts));
            }
        }

        function createPostElement(post) {
            const postDiv = document.createElement('div');
            postDiv.className = 'post-card';
            
            const categoryClass = `category-${post.category}`;
            
            let mediaHTML = '';
            if (post.media && post.media.length > 0) {
                mediaHTML = '<div class="post-media">';
                post.media.forEach(media => {
                    if (media.type === 'image') {
                        mediaHTML += `<img src="${media.url}" alt="Post image">`;
                    } else if (media.type === 'video') {
                        mediaHTML += `<video src="${media.url}" controls></video>`;
                    }
                });
                mediaHTML += '</div>';
            }
            
            postDiv.innerHTML = `
                <h3 class="post-title">${post.title}</h3>
                ${mediaHTML}
                <p class="post-content">${post.content}</p>
                <div class="post-meta">
                    <span class="post-author">By ${post.author}</span>
                    <span class="post-date">${post.date}</span>
                </div>
                <span class="post-category ${categoryClass}">${post.category}</span>
            `;
            
            return postDiv;
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
                date: new Date().toLocaleDateString(),
                media: []
            };
            
            // Process media files
            if (mediaFiles.length > 0) {
                // In a real app, you would upload these to a server
                // For this demo, we'll just use placeholder URLs
                mediaFiles.forEach(file => {
                    const fileType = file.type.split('/')[0];
                    newPost.media.push({
                        type: fileType,
                        url: URL.createObjectURL(file)
                    });
                });
            }
            
            // Save post
            const posts = JSON.parse(localStorage.getItem('posts') || '[]');
            posts.unshift(newPost); // Add to beginning of array
            localStorage.setItem('posts', JSON.stringify(posts));
            
            // Reload posts
            loadPosts();
            
            // Clear form and media
            postForm.reset();
            mediaFiles = [];
            mediaPreview.innerHTML = '';
            
            // Add to user's posts
            loadUserPosts();
            
            alert('Your post has been published!');
        }

        function showDashboard() {
            // Show dashboard section
            dashboardSection.classList.remove('hidden');
            
            // Scroll to dashboard
            dashboardSection.scrollIntoView({ behavior: 'smooth' });
            
            // Update profile info
            if (currentUser) {
                profileName.textContent = currentUser.name;
                profileEmail.textContent = currentUser.email;
                joinDate.textContent = currentUser.joinDate;
            }
            
            // Load user's posts
            loadUserPosts();
        }

        function loadUserPosts() {
            if (!currentUser) return;
            
            // Clear user posts container
            userPostsContainer.innerHTML = '';
            
            // Get posts from localStorage
            const posts = JSON.parse(localStorage.getItem('posts') || '[]');
            
            // Filter user's posts
            const userPosts = posts.filter(post => post.author === currentUser.name);
            
            if (userPosts.length === 0) {
                userPostsContainer.innerHTML = '<p>You haven\'t made any posts yet.</p>';
                return;
            }
            
            // Display user's posts
            userPosts.forEach(post => {
                const postElement = createPostElement(post);
                userPostsContainer.appendChild(postElement);
            });
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
