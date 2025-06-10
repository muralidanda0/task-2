<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Development Tasks</title>
    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #4895ef;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --warning: #f72585;
            --danger: #f72585;
            --gray: #6c757d;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 2rem;
            color: var(--dark);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            padding: 2rem;
        }
        
        h1 {
            text-align: center;
            color: var(--secondary);
            margin-bottom: 2rem;
            font-size: 2.5rem;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        h2 {
            color: var(--secondary);
            margin: 1.5rem 0 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--accent);
        }
        
        .task-section {
            background-color: white;
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border-left: 4px solid var(--accent);
        }
        
        /* Contact Form Styles */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--secondary);
        }
        
        input, textarea, select {
            width: 100%;
            padding: 0.75rem 1rem;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        input:focus, textarea:focus, select:focus {
            border-color: var(--accent);
            outline: none;
            box-shadow: 0 0 0 3px rgba(72, 149, 239, 0.2);
        }
        
        button {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.3);
        }
        
        .error {
            color: var(--danger);
            font-size: 0.875rem;
            margin-top: 0.25rem;
            display: none;
        }
        
        /* Responsive Layout Styles */
        .responsive-layout {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }
        
        @media (min-width: 768px) {
            .responsive-layout {
                grid-template-columns: 250px 1fr;
            }
        }
        
        .nav {
            background-color: var(--light);
            padding: 1rem;
            border-radius: 8px;
        }
        
        .nav ul {
            list-style: none;
        }
        
        .nav li {
            margin-bottom: 0.5rem;
        }
        
        .nav a {
            display: block;
            padding: 0.5rem 1rem;
            color: var(--dark);
            text-decoration: none;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        
        .nav a:hover {
            background-color: var(--accent);
            color: white;
        }
        
        .content-area {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1rem;
        }
        
        .card {
            background-color: white;
            border-radius: 8px;
            padding: 1rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .card h3 {
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        /* To-Do List Styles */
        .todo-container {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .todo-form {
            display: flex;
            margin-bottom: 1rem;
            gap: 0.5rem;
        }
        
        .todo-form input {
            flex: 1;
        }
        
        .todo-list {
            list-style: none;
        }
        
        .todo-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0.75rem 1rem;
            background-color: white;
            border-radius: 8px;
            margin-bottom: 0.5rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .todo-item:hover {
            transform: translateX(5px);
        }
        
        .todo-item.completed {
            opacity: 0.7;
            text-decoration: line-through;
        }
        
        .todo-actions {
            display: flex;
            gap: 0.5rem;
        }
        
        .todo-actions button {
            padding: 0.25rem 0.5rem;
            font-size: 0.875rem;
        }
        
        .delete-btn {
            background: var(--danger);
        }
        
        /* Image Gallery Styles */
        .gallery-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .gallery-form {
            display: flex;
            margin-bottom: 1rem;
            gap: 0.5rem;
        }
        
        .gallery-form input {
            flex: 1;
        }
        
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1rem;
        }
        
        .gallery-item {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .gallery-item:hover {
            transform: scale(1.05);
        }
        
        .gallery-item img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            display: block;
        }
        
        .gallery-item .remove-btn {
            position: absolute;
            top: 0.5rem;
            right: 0.5rem;
            background-color: var(--danger);
            color: white;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .gallery-item:hover .remove-btn {
            opacity: 1;
        }
        
        .tab-container {
            display: flex;
            margin-bottom: 1rem;
            border-bottom: 1px solid #e9ecef;
        }
        
        .tab {
            padding: 0.5rem 1rem;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
        }
        
        .tab.active {
            border-bottom-color: var(--primary);
            color: var(--primary);
            font-weight: 600;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Web Development Tasks</h1>
        
        <div class="tab-container">
            <div class="tab active" onclick="openTab('contact-form')">Contact Form</div>
            <div class="tab" onclick="openTab('responsive-layout')">Responsive Layout</div>
            <div class="tab" onclick="openTab('todo-list')">To-Do List</div>
            <div class="tab" onclick="openTab('image-gallery')">Image Gallery</div>
        </div>
        
        <!-- Task 1: Contact Form -->
        <div id="contact-form" class="task-section tab-content active">
            <h2>Contact Form with Validation</h2>
            <form class="contact-form" id="contactForm">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" required>
                    <div class="error" id="nameError">Please enter your name</div>
                </div>
                
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                    <div class="error" id="emailError">Please enter a valid email</div>
                </div>
                
                <div class="form-group">
                    <label for="subject">Subject</label>
                    <select id="subject" name="subject">
                        <option value="">Select a subject</option>
                        <option value="general">General Inquiry</option>
                        <option value="support">Technical Support</option>
                        <option value="feedback">Feedback</option>
                    </select>
                    <div class="error" id="subjectError">Please select a subject</div>
                </div>
                
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" rows="5" required></textarea>
                    <div class="error" id="messageError">Please enter your message</div>
                </div>
                
                <button type="submit">Send Message</button>
            </form>
        </div>
        
        <!-- Task 2: Responsive Layout -->
        <div id="responsive-layout" class="task-section tab-content">
            <h2>Responsive Layout with Flexbox and CSS Grid</h2>
            <div class="responsive-layout">
                <nav class="nav">
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">About</a></li>
                        <li><a href="#">Services</a></li>
                        <li><a href="#">Portfolio</a></li>
                        <li><a href="#">Contact</a></li>
                    </ul>
                </nav>
                
                <main class="content-area">
                    <div class="card">
                        <h3>Web Design</h3>
                        <p>Creating beautiful, responsive websites that work across all devices.</p>
                    </div>
                    <div class="card">
                        <h3>Frontend Development</h3>
                        <p>Building interactive user interfaces with modern JavaScript frameworks.</p>
                    </div>
                    <div class="card">
                        <h3>UI/UX Design</h3>
                        <p>Designing intuitive user experiences that delight your customers.</p>
                    </div>
                    <div class="card">
                        <h3>Performance Optimization</h3>
                        <p>Making your website fast and efficient for better user engagement.</p>
                    </div>
                </main>
            </div>
        </div>
        
        <!-- Task 3: To-Do List -->
        <div id="todo-list" class="task-section tab-content">
            <h2>Dynamic To-Do List</h2>
            <div class="todo-container">
                <form class="todo-form" id="todoForm">
                    <input type="text" id="todoInput" placeholder="Add a new task..." required>
                    <button type="submit">Add</button>
                </form>
                
                <ul class="todo-list" id="todoList"></ul>
            </div>
        </div>
        
        <!-- Task 4: Image Gallery -->
        <div id="image-gallery" class="task-section tab-content">
            <h2>Dynamic Image Gallery</h2>
            <div class="gallery-container">
                <form class="gallery-form" id="galleryForm">
                    <input type="url" id="imageUrl" placeholder="Enter image URL..." required>
                    <button type="submit">Add Image</button>
                </form>
                
                <div class="gallery" id="imageGallery"></div>
            </div>
        </div>
    </div>

    <script>
        // Tab functionality
        function openTab(tabId) {
            // Hide all tab contents
            document.querySelectorAll('.tab-content').forEach(content => {
                content.classList.remove('active');
            });
            
            // Remove active class from all tabs
            document.querySelectorAll('.tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Show the selected tab content
            document.getElementById(tabId).classList.add('active');
            
            // Add active class to the clicked tab
            event.currentTarget.classList.add('active');
        }
        
        // Task 1: Contact Form Validation
        const contactForm = document.getElementById('contactForm');
        
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            let isValid = true;
            
            // Validate name
            const name = document.getElementById('name');
            const nameError = document.getElementById('nameError');
            if (name.value.trim() === '') {
                nameError.style.display = 'block';
                name.style.borderColor = 'var(--danger)';
                isValid = false;
            } else {
                nameError.style.display = 'none';
                name.style.borderColor = '#e9ecef';
            }
            
            // Validate email
            const email = document.getElementById('email');
            const emailError = document.getElementById('emailError');
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailRegex.test(email.value)) {
                emailError.style.display = 'block';
                email.style.borderColor = 'var(--danger)';
                isValid = false;
            } else {
                emailError.style.display = 'none';
                email.style.borderColor = '#e9ecef';
            }
            
            // Validate subject
            const subject = document.getElementById('subject');
            const subjectError = document.getElementById('subjectError');
            if (subject.value === '') {
                subjectError.style.display = 'block';
                subject.style.borderColor = 'var(--danger)';
                isValid = false;
            } else {
                subjectError.style.display = 'none';
                subject.style.borderColor = '#e9ecef';
            }
            
            // Validate message
            const message = document.getElementById('message');
            const messageError = document.getElementById('messageError');
            if (message.value.trim() === '') {
                messageError.style.display = 'block';
                message.style.borderColor = 'var(--danger)';
                isValid = false;
            } else {
                messageError.style.display = 'none';
                message.style.borderColor = '#e9ecef';
            }
            
            if (isValid) {
                alert('Form submitted successfully!');
                contactForm.reset();
            }
        });
        
        // Task 3: To-Do List
        const todoForm = document.getElementById('todoForm');
        const todoInput = document.getElementById('todoInput');
        const todoList = document.getElementById('todoList');
        
        // Load todos from localStorage
        let todos = JSON.parse(localStorage.getItem('todos')) || [];
        
        function renderTodos() {
            todoList.innerHTML = '';
            todos.forEach((todo, index) => {
                const li = document.createElement('li');
                li.className = `todo-item ${todo.completed ? 'completed' : ''}`;
                li.innerHTML = `
                    <span>${todo.text}</span>
                    <div class="todo-actions">
                        <button onclick="toggleTodo(${index})">${todo.completed ? 'Undo' : 'Complete'}</button>
                        <button class="delete-btn" onclick="removeTodo(${index})">Delete</button>
                    </div>
                `;
                todoList.appendChild(li);
            });
        }
        
        function addTodo() {
            const text = todoInput.value.trim();
            if (text) {
                todos.push({ text, completed: false });
                localStorage.setItem('todos', JSON.stringify(todos));
                todoInput.value = '';
                renderTodos();
            }
        }
        
        function toggleTodo(index) {
            todos[index].completed = !todos[index].completed;
            localStorage.setItem('todos', JSON.stringify(todos));
            renderTodos();
        }
        
        function removeTodo(index) {
            todos.splice(index, 1);
            localStorage.setItem('todos', JSON.stringify(todos));
            renderTodos();
        }
        
        todoForm.addEventListener('submit', function(e) {
            e.preventDefault();
            addTodo();
        });
        
        // Initial render
        renderTodos();
        
        // Task 4: Image Gallery
        const galleryForm = document.getElementById('galleryForm');
        const imageUrl = document.getElementById('imageUrl');
        const imageGallery = document.getElementById('imageGallery');
        
        // Load images from localStorage
        let images = JSON.parse(localStorage.getItem('galleryImages')) || [];
        
        function renderGallery() {
            imageGallery.innerHTML = '';
            images.forEach((url, index) => {
                const div = document.createElement('div');
                div.className = 'gallery-item';
                div.innerHTML = `
                    <img src="${url}" alt="Gallery image">
                    <button class="remove-btn" onclick="removeImage(${index})">×</button>
                `;
                imageGallery.appendChild(div);
            });
        }
        
        function addImage() {
            const url = imageUrl.value.trim();
            if (url) {
                images.push(url);
                localStorage.setItem('galleryImages', JSON.stringify(images));
                imageUrl.value = '';
                renderGallery();
            }
        }
        
        function removeImage(index) {
            images.splice(index, 1);
            localStorage.setItem('galleryImages', JSON.stringify(images));
            renderGallery();
        }
        
        galleryForm.addEventListener('submit', function(e) {
            e.preventDefault();
            addImage();
        });
        
        // Initial render
        renderGallery();
    </script>
</body>
</html>
