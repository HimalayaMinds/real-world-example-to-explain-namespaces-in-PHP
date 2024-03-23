# real world example to explain namespaces in PHP


Imagine you're developing a web application that includes user authentication functionality. You decide to create a `User` class to handle user-related operations such as login, registration, and profile management. Additionally, you want to use a third-party library called `Mailer` to send email notifications to users.

Here's how you can utilize namespaces to organize your code:

```php
// Define your User class in the 'App' namespace
namespace App;

class User {
    public function login($username, $password) {
        // Login logic here
    }

    public function register($username, $password, $email) {
        // Registration logic here
    }

    public function updateProfile($userId, $newData) {
        // Profile update logic here
    }
}
```

Now, let's say you have a `Mailer` class from a third-party library:

```php
// Define the Mailer class in its own namespace
namespace ThirdParty;

class Mailer {
    public function sendEmail($recipient, $subject, $message) {
        // Email sending logic here
    }
}
```

In your application code, you can use these classes:

```php
// Import the necessary namespaces
use App\User;
use ThirdParty\Mailer;

// Instantiate the User class
$user = new User();

// Use the User class methods
$user->register('john_doe', 'password123', 'john@example.com');

// Instantiate the Mailer class
$mailer = new Mailer();

// Use the Mailer class method
$mailer->sendEmail('john@example.com', 'Welcome!', 'Welcome to our website!');
```

In this example:

- The `User` class is defined within the `App` namespace to encapsulate user-related functionality.
- The `Mailer` class from the third-party library is defined within the `ThirdParty` namespace.
- In the application code, you import these namespaces using the `use` keyword to specify which classes you want to use.
- This allows you to instantiate and use the `User` and `Mailer` classes without any naming conflicts, even if they have methods or properties with the same names.

By using namespaces, you can organize your code logically, prevent naming conflicts, and efficiently manage dependencies in your PHP applications.
