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
