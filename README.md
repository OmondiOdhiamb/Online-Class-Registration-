# Online-Class-Registration-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Class Registration</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to Online Class Registration</h1>
        <nav>
            <a href="register.html">Register</a>
            <a href="login.html">Login</a>
        </nav>
    </header>
    <main>
        <h2>Available Courses</h2>
        <ul>
            <li>Course 1: Introduction to Programming</li>
            <li>Course 2: Web Development Basics</li>
            <li>Course 3: Data Science 101</li>
        </ul>
    </main>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Register</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Register for an Account</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="login.html">Login</a>
        </nav>
    </header>
    <main>
        <form id="registerForm">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>

            <button type="submit">Register</button>
        </form>
    </main>

    <script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Login to Your Account</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="register.html">Register</a>
        </nav>
    </header>
    <main>
        <form id="loginForm">
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>

            <button type="submit">Login</button>
        </form>
    </main>

    <script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Dashboard</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="login.html" id="logoutBtn">Logout</a>
        </nav>
    </header>
    <main id="dashboardContent">
        <!-- Content will be loaded by JavaScript based on user role -->
    </main>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: #fff;
    padding: 10px 0;
    text-align: center;
}

header h1 {
    margin: 0;
}

nav a {
    color: #fff;
    margin: 0 10px;
    text-decoration: none;
}

main {
    padding: 20px;
    max-width: 600px;
    margin: 0 auto;
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

form {
    display: flex;
    flex-direction: column;
}

label {
    margin-bottom: 5px;
    font-weight: bold;
}

input {
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px;
    background-color: #333;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #555;
}

h2 {
    margin-top: 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

ul li {
    background-color: #eee;
    margin: 5px 0;
    padding: 10px;
    border-radius: 5px;
}
// Mock database (in real case, you'll use backend APIs)
const users = [
    { email: "admin@example.com", password: "admin123", role: "admin" },
    { email: "student@example.com", password: "student123", role: "student" }
];

const courses = [
    { title: "Introduction to Programming", description: "Learn the basics of programming." },
    { title: "Web Development Basics", description: "Learn the fundamentals of web development." },
    { title: "Data Science 101", description: "An introduction to data science." }
];

// Handle registration form submission
document.getElementById('registerForm')?.addEventListener('submit', function(event) {
    event.preventDefault();
    alert('Registration successful!');
    window.location.href = 'login.html';
});

// Handle login form submission
document.getElementById('loginForm')?.addEventListener('submit', function(event) {
    event.preventDefault();
    const email = event.target.email.value;
    const password = event.target.password.value;

    const user = users.find(user => user.email === email && user.password === password);
    
    if (user) {
        localStorage.setItem('user', JSON.stringify(user));
        window.location.href = 'dashboard.html';
    } else {
        alert('Invalid email or password');
    }
});

// Load dashboard content based on user role
window.addEventListener('load', function() {
    const user = JSON.parse(localStorage.getItem('user'));
    const dashboardContent = document.getElementById('dashboardContent');
    
    if (dashboardContent && user) {
        if (user.role === 'admin') {
            dashboardContent.innerHTML = `
                <h2>Admin Dashboard</h2>
                <h3>Course Registrations</h3>
                <ul>
                    ${courses.map(course => `<li>${course.title}: <button>Approve</button> <button>Reject</button></li>`).join('')}
                </ul>
            `;
        } else if (user.role === 'student') {
            dashboardContent.innerHTML = `
                <h2>Student Dashboard</h2>
                <h3>Your Courses</h3>
                <ul>
                    ${courses.map(course => `<li>${course.title}</li>`).join('')}
                </ul>
            `;
        }
    }
});

// Handle logout
document.getElementById('logoutBtn')?.addEventListener('click', function() {
    localStorage.removeItem('user');
});
