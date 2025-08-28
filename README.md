# LaravelTips

### Laravel is useful because it provides a clean, elegant syntax and a robust set of tools for building modern web applications. Key benefits include:
- MVC Architecture: Separates logic, presentation, and data, making code more organized and maintainable.
- Eloquent ORM: Simplifies database interactions with an easy-to-use ActiveRecord implementation.
- Routing: Flexible and expressive routing system for handling web requests.
- Security: Built-in features for authentication, authorization, and protection against common vulnerabilities.
- Blade Templating: Simple yet powerful templating engine for building dynamic views.
- Artisan CLI: Command-line tools for automating repetitive tasks.
- Testing: Integrated support for unit and feature testing.
- Community & Ecosystem: Large community, extensive documentation, and many packages for rapid development.
- Overall, Laravel speeds up development, enforces best practices, and helps create scalable, secure applications.


### Laravel Migration Important Commands:
Migrations are like version control for your database, allowing your team to define and share the applications database schema. 
You can create, modify, and share database tables and columns using migration files and Artisan commands->
- php artisan migrate ->for migration
- php artisan migrate:rollback -> for rollback
- php artisan migrate:refresh -> for rollback all migrations and migrate again
- php artisan migrate:fresh -> drop all tables and migrate
- php artisan migrate:status -> to check the status of migration
- php artisan make:migration tabla_name -> to create a new migration file


### Laravel Service Provider and Service Container:
The Service Container is a powerful tool for managing class dependencies and performing dependency injection. 
It allows you to bind classes and interfaces and resolve them automatically when needed. This makes your code more modular, testable, and maintainable.
Dependency Injection is a technique where one object supplies the dependencies of another object. A service provider 
is responsible for binding things into the service container. In general, we can say that service providers are the 
central place of all Laravel application bootstrapping. Your own application, as well as all of Laravel's core services, are bootstrapped via service providers.
They are stored in the app/Providers directory. The default Laravel installation comes with a few service providers, which are listed in the config/app.php configuration file. 
You can add your own service providers to this array to make them available to your application.
To create a new service provider, you can use the Artisan command:
-php artisan make:provider YourServiceProviderName

This command will create a new service provider file in the app/Providers directory. You can then register your bindings in the register method of the service provider. 
After creating the service provider, you need to register it in the config/app.php file by adding it to the 'providers' array.
and then run the command:
- php artisan config:cache
- php artisan cache:clear
- php artisan route:cache
- php artisan view:clear
- php artisan optimize:clear
- php artisan optimize
- php artisan serve
- php artisan route:clear
- php artisan view:cache    


### Laravel Facades:
Facades provide a "static" interface to classes that are available in the application's service container. 
They serve as "shortcuts" to underlying classes, making it easier to use Laravel's features without needing to resolve objects out of the service container manually.


### Eloquent ORM:
Eloquent is Laravel's built-in ORM (Object-Relational Mapper) that provides a simple ActiveRecord implementation for working with your database. 
Each database table has a corresponding "Model" that is used to interact with that table. Eloquent makes it easy to perform CRUD operations and define relationships between tables.


### Seeding Data in Laravel:
Laravel provides a simple way to seed your database with test data using seed classes.
You can create seed classes using the Artisan command:
- php artisan make:seeder SeederName
  
You can then define the data you want to insert into your database in the run method of the seeder class.
To run the seeders, you can use the Artisan command:
- php artisan db:seed
  
You can also specify a specific seeder to run using the --class option:
- php artisan db:seed --class=SeederName


### Laravel Relationships:
Laravel provides several types of relationships to define how models relate to each other.
- One-to-One: A single record in one table is associated with a single record in another table.
- One-to-Many: A single record in one table can be associated with multiple records in another table.
- Many-to-Many: Multiple records in one table can be associated with multiple records in another table.
- Has Many Through: A relationship that allows you to access records in a distant table through an
intermediate table.
- Polymorphic Relationships: A relationship that allows a model to belong to multiple other models on a single association.
  
You can define these relationships in your Eloquent models using methods like hasOne, hasMany, belongsTo, belongsToMany, hasManyThrough, and morphTo.


###  routing work in Laravel:
Routing in Laravel allows you to define URLs for your application and map them to controllers or closures. 
Routes are defined in the routes/web.php (for web) and routes/api.php (for API) files. Example->
- Route::get('/users', [UserController::class, 'index']);


### Middleware in Laravel:
Middleware provides a convenient mechanism for filtering HTTP requests entering your application. 
For example, Laravel includes a middleware that verifies the user of your application is authenticated. Middleware can be assigned to routes or groups of routes.


### Laravel handle authentication:
Laravel provides a complete authentication system out of the box, including login, registration, password reset, 
and email verification. You can use the built-in Auth facade and middleware to protect routes and manage user sessions.


###  Laravel Events and Listeners :
Events provide a simple observer implementation, allowing you to subscribe and listen for various events 
that occur in your application. Listeners handle the event logic. You can generate events and listeners using Artisan commands and register them in the EventServiceProvider.


### Blade Templating Engine:
Blade is Laravel's powerful, simple templating engine. It allows you to use plain PHP code in your views 
and provides convenient shortcuts for common tasks, such as loops and conditionals. Blade templates are compiled into plain PHP and cached for better performance.


### validate data in Laravel:
Laravel provides several ways to validate incoming data, including the validate method on controllers, 
form request classes, and the Validator facade. Validation rules are defined as arrays, and Laravel automatically redirects back with errors if validation fails.


###  Artisan commands:
Artisan is Laravel's command-line interface. It provides commands for common tasks like migrations, 
database seeding, cache clearing, and more. You can also create your own custom commands using:
php artisan make:command MyCommand


### CSRF protection in Laravel:
Laravel automatically generates a CSRF (Cross-Site Request Forgery) token for each active user session. 
This token is used to verify that the authenticated user is the one actually making the requests to the application. 
You should include @csrf in your forms to protect against CSRF attacks.


### Laravel Queues:
Queues allow you to defer the processing of a time-consuming task, such as sending an email, until a later time.
This can significantly speed up web requests to your application. Laravel provides a unified API for different queue
backends, such as Beanstalkd, Amazon SQS, Redis, or even a relational database.


### Laravel API Development:
Laravel makes it easy to build robust APIs. You can use the built-in routing, middleware, and authentication features to create secure and efficient APIs.


### Laravel Task Scheduling:
Laravel's task scheduling allows you to define scheduled tasks within your application. You can use the 
schedule method in the App\Console\Kernel class to define your scheduled tasks.


### Laravel Socialite:
Laravel Socialite provides an easy way to handle OAuth authentication with various providers like Google, Facebook,
Twitter, and GitHub. You can use Socialite to authenticate users via these providers and retrieve their information.


### Laravel Localization:
Laravel provides built-in support for localization, allowing you to easily translate your application into multiple languages.


### Laravel Telescope:
Laravel Telescope is a powerful debugging assistant for Laravel applications. It provides insights into requests, exceptions,
database queries, queued jobs, mail, notifications, cache operations, and more.


### Laravel Events and Broadcasting:
Laravel's event system allows you to define events and listeners, enabling a decoupled architecture.
You can also broadcast events in real-time using Laravel Echo and WebSockets.
example->
- Event::dispatch(new OrderShipped($order));


### Laravel Mail:
Laravel provides a simple and elegant way to send emails using various drivers like SMTP, Mailgun, Postmark, Amazon SES, and more.
You can use the Mail facade to send emails and create mailable classes for better organization.
example->
- Mail::to($request->user())->send(new OrderShipped($order));


### Laravel File Storage:
Laravel provides a unified API for interacting with different file storage systems, such as local storage, Amazon S3, and others.
You can use the Storage facade to manage files and directories.


### Laravel Traits:
Traits are a mechanism for code reuse in single inheritance languages like PHP. A trait is intended to reduce some limitations of single inheritance by enabling a developer to reuse sets of methods freely in several independent classes living in different class hierarchies.
example->
```
use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\Factories\HasFactory;
class User extends Model
{
    use HasFactory, Notifiable;
}
```

### Laravel Collections:
Laravel Collections provide a fluent, convenient wrapper for working with arrays of data.
They offer a variety of methods for manipulating and transforming data, making it easier to work with arrays
example->
```
$users = User::all();
$filtered = $users->filter(function ($user) {
    return $user->age > 18;
});
```

### Laravel Helpers:
Laravel provides a variety of global helper functions that can be used throughout your application. These helpers cover a wide range of functionalities, such as string manipulation, array handling, and URL generation.
example->
```
$url = url('/home');
$slug = Str::slug('Laravel Tips and Tricks');
```

### Laravel Scout:
Laravel Scout provides a simple, driver-based solution for adding full-text search to your Eloquent models. It supports various search engines like Algolia and MeiliSearch.
example->
```
use Laravel\Scout\Searchable;
class Post extends Model
{
    use Searchable;
}
```

### Laravel Policies:
Policies are classes that organize authorization logic around a particular model or resource. They provide a way to
centralize authorization logic and make it easier to manage.
example->
- php artisan make:policy PostPolicy --model=Post


### Laravel API Resources:
API Resources provide a way to transform your models and collections into JSON responses. They allow you to
control the structure of your JSON output and include related resources.
example->
- php artisan make:resource UserResource


#### Laravel Dusk:
Laravel Dusk provides an expressive, easy-to-use browser automation and testing API. It allows you to write tests that interact with your application in a real browser.
example->
- php artisan dusk:install


### Laravel Horizon:
Laravel Horizon provides a beautiful dashboard and code-driven configuration for your Redis queues. It allows you to monitor key metrics of your queue system, such as job throughput, runtime, and failures.
example->   
- php artisan horizon:install
- php artisan horizon


### Laravel Passport:
Laravel Passport provides a full OAuth2 server implementation for your Laravel application in a matter of minutes.
example->
- php artisan passport:install


### Laravel Jobs:
Jobs are classes that represent a specific task or piece of work that needs to be performed.
You can create jobs using the Artisan command and dispatch them to be processed by a queue worker.
example->
- php artisan make:job SendWelcomeEmail


### Laravel Broadcasting:
Broadcasting allows you to share the same event names between your server-side Laravel application and your client-side JavaScript application. This makes it easy to build real-time applications using WebSockets.
example->   
- php artisan make:event OrderShipped

### Laravel Mix:
Laravel Mix is a wrapper around Webpack that provides a clean, fluent API for defining Webpack build steps for your Laravel application. It simplifies the process of compiling and optimizing your CSS and JavaScript assets.
example->
- npm install
- npm run dev
- npm run prod

### Laravel Tips and Tricks:
Here are some useful tips and tricks for working with Laravel:
1. Use Eloquent Accessors and Mutators to format model attributes when retrieving or setting them.
2. Use route model binding to automatically inject model instances into your routes and controllers.
3. Use the `when` method on Eloquent queries to conditionally add query constraints.
4. Use the `tap` helper function to perform actions on an object and return the object
5. Use the `optional` helper function to safely access properties or methods on potentially null objects.
6. Use the `collect` helper function to create a collection from an array or other iterable.
7. Use the `chunk` method on Eloquent queries to process large datasets in smaller chunks, reducing memory usage.
8. Use the `firstOrCreate` and `updateOrCreate` methods on Eloquent models to simplify finding or creating records.
9. Use the `withCount` method on Eloquent queries to get the count of related models without loading them.
10. Use the `lazy` method on Eloquent queries to process large datasets using a generator, reducing memory usage.
11. Use the `assertDatabaseHas` and `assertDatabaseMissing` methods in your tests to verify the presence or absence of records in the database.
12. Use the `assertSee` and `assertDontSee` methods in your tests to verify the presence or absence of text in the response.
13. Use the `assertJson` and `assertJsonFragment` methods in your tests to verify the structure and content of JSON responses.
14. Use the `assertRedirect` method in your tests to verify that a response redirects to a specific URL.
15. Use the `assertSessionHas` and `assertSessionMissing` methods in your tests to verify the presence or absence of session data.

### Laravel Best Practices:
1. Follow the PSR-12 coding standard for PHP code.
2. Use environment variables to manage configuration settings.
3. Use Eloquent relationships to define associations between models.
4. Use form request classes for validation and authorization logic.
5. Use resource controllers to handle CRUD operations for models.
6. Use API resources to transform models and collections into JSON responses.
7. Use queues for time-consuming tasks to improve application performance.
8. Use caching to improve application performance and reduce database load.
9. Write tests for your application to ensure code quality and prevent regressions.
10. Keep your controllers thin by moving business logic to service classes or model methods.
11. Use Laravel's built-in features and avoid reinventing the wheel.
12. Regularly update Laravel and its dependencies to benefit from security patches and new features.
13. Use version control (e.g., Git) to manage your codebase and collaborate with others.
14. Document your code and use meaningful names for variables, methods, and classes.
15. Follow the principle of least privilege when managing user roles and permissions.

### Laravel Security Best Practices:
1. Always validate and sanitize user input to prevent SQL injection and XSS attacks.
2. Use Laravel's built-in CSRF protection by including the @csrf directive in your forms.
3. Use HTTPS to encrypt data transmitted between the client and server.
4. Store sensitive information, such as API keys and database credentials, in environment variables.
5. Use Laravel's built-in authentication and authorization features to manage user access.
6. Regularly update Laravel and its dependencies to benefit from security patches.
7. Use strong password hashing algorithms (e.g., bcrypt) to store user passwords securely.
8. Limit login attempts to prevent brute-force attacks using Laravel's built-in throttle middleware.
9. Use prepared statements and Eloquent ORM to interact with the database safely.
10. Regularly back up your database and application files to prevent data loss.

### Laravel Console :
Laravel's Artisan command-line interface provides a variety of built-in commands to help you manage your application.
You can also create your own custom commands to automate repetitive tasks.
example->
- php artisan make:command MyCustomCommand

### Laravel Events and Listeners:
Events provide a simple observer implementation, allowing you to subscribe and listen for various events that occur in
your application. Listeners handle the event logic. You can generate events and listeners using Artisan commands and register them in the EventServiceProvider.
example->
- php artisan make:event UserRegistered
- php artisan make:listener SendWelcomeEmail --event=UserRegistered


### Laravel Job Batching:
Job batching allows you to group multiple jobs into a single batch, making it easier to manage and monitor related jobs.
You can create job batches using the Bus facade and monitor their progress using the Horizon dashboard.
example->
```    
use Illuminate\Support\Facades\Bus;
$batch = Bus::batch([
    new ProcessPodcast,
    new ReleasePodcast,
])->dispatch();
```

### Laravel Custom Validation Rules:
You can create custom validation rules by implementing the Rule interface or using the make:rule Artisan command
- php artisan make:rule Uppercase


### Laravel Custom Blade Directives:
You can create custom Blade directives to extend the functionality of the Blade templating engine.
example->
```
use Illuminate\Support\Facades\Blade;
Blade::directive('datetime', function ($expression) {
    return "<?php echo ($expression)->format('m/d/Y H:i'); ?>";
});
```

### Laravel API Rate Limiting:
Laravel provides built-in support for rate limiting API requests using the throttle middleware.
You can configure rate limits in the RouteServiceProvider or directly on your routes.
example->
```
Route::middleware('throttle:60,1')->group(function () {
    Route::get('/user', function () {
        // Your route logic here
    });
});
```

### Laravel Custom Casts:
You can create custom Eloquent attribute casts by implementing the CastsAttributes interface or using the make:cast Artisan command.
- php artisan make:cast Json


### Laravel Model Observers:
Model observers allow you to group event listeners for a model into a single class.
You can create model observers using the make:observer Artisan command and register them in the boot method of a service provider.
example->
- php artisan make:observer UserObserver --model=User


### Laravel API Pagination:
Laravel provides built-in support for paginating API responses using the paginate method on Eloquent queries.
example->
```
$users = User::paginate(15);
```

### Laravel Custom Error Pages:
You can create custom error pages by creating Blade views in the resources/views/errors directory.
For example, create a 404.blade.php file for handling 404 errors.


### Laravel 2025 Notes
1. Latest Version & Updates: Laravel continues to release regular updates; check laravel.com for the latest version and features. Improved performance, security, and developer experience in recent releases.
2. Core Features: MVC Architecture: Clean separation of concerns.
Eloquent ORM: Simplifies database operations.
- Blade Templating: Fast, secure, and easy-to-use view engine.
- Routing: Flexible and expressive route definitions.
- Middleware: Easy request filtering and modification.
- Authentication & Authorization: Built-in scaffolding and policies.
4. Modern Development Tools:
- Artisan CLI: Automate tasks, migrations, and code generation.
- Laravel Mix/Vite: Asset compilation and management.
- Testing: PHPUnit integration for unit and feature tests.
5. Ecosystem: Laravel Breeze, Jetstream, Fortify: Authentication scaffolding.
- Laravel Nova: Admin panel.
- Laravel Horizon: Queue monitoring.
- Laravel Sanctum & Passport: API authentication.
6. Best Practices:Use environment variables for configuration. Follow PSR standards and Laravel conventions. Write tests for critical features. Use queues and jobs for heavy tasks.
7. Deployment: Use tools like Laravel Forge, Envoyer, or Docker for deployment. Optimize with caching, config caching, and route caching.
8. Community & Resources: Extensive documentation and tutorials. Active community on forums, Discord, and GitHub. Increased use of Laravel with modern frontend frameworks (React, Vue, Inertia.js). More focus on API development and microservices. Enhanced support for serverless and cloud-native deployments.

### Artisan Important Commands and description:

| Sr.No. | Command | Description |
| --- | --- | --- |
| 1. | php artisan  clear-compiled |                Remove the compiled class file |
| 2. | php artisan  completion |                    Dump the shell completion script |
| 3. | php artisan  db |  Start a new database CLI session
| 4. | php artisan  down |Put the application into maintenance / demo mode |
| 5. | php artisan  env | Display the current framework environment |
| 6. | php artisan  help |Display help for a command |
| 7. | php artisan  inspire |                       Display an inspiring quote |
| 8. | php artisan  list |List commands |
| 9. | php artisan  migrate |                       Run the database migrations |
| 10. | php artisan  optimize |                      Cache the framework bootstrap files |
| 11. | php artisan  serve |                         Serve the application on the PHP development server |
| 12. | php artisan  socket-connection |             web message socket connection service |
| 13. | php artisan  test |Run the application tests |
| 14. | php artisan  tinker |                        Interact with your application |
| 15. | php artisan  ui |  Swap the front-end scaffolding for the application |
| 16. | php artisan  up |  Bring the application out of maintenance mode |
| 17. | php artisan  Billing:sendBillingEmail |      Send Email to admin for due Invoice |
| 18. | php artisan  Invoice:generateInvoice  |      For generating monthly invoice |
| 19. | php artisan  Registration:sendToCRM   |      Send Regitration to CRM if any failed |
| 20. | php artisan  auth:clear-resets |             Flush expired password reset tokens |
| 21. | php artisan  cache:clear |                   Flush the application cache |
| 22. | php artisan  cache:forget |                  Remove an item from the cache |
| 23. | php artisan  cache:table | Create a migration for the cache database table |
| 24. | php artisan  config:cache |                   Create a cache file for faster configuration loading |
| 25. | php artisan  config:clear |                   Remove the configuration cache file |
| 26. | php artisan  danube:bayz | Bays 101 Inventory Cron |
| 27. | php artisan  db:seed |     Seed the database with records |
| 28. | php artisan  db:wipe |     Drop all tables, views, and types |
| 29. | php artisan  event:cache | Discover and cache the application's events and listeners         |
| 30. | php artisan  event:clear | Clear all cached events and listeners |
| 31. | php artisan  event:generate     |            Generate the missing events and listeners based on registration   |
| 32. | php artisan  event:list |  List the application's events and listeners |
| 33. | php artisan  frontendscript:checkup |        Ensure that the npm listener is running. |
| 34. | php artisan  geoip:clear | Clear GeoIP cached locations. |
| 35. | php artisan  geoip:update |                   Update GeoIP database files to the latest version |
| 36. | php artisan  projectname:status |  projectname Project Status Update after 30 seconds (This is Custom Command) |
| 37. | php artisan  projectname:statusfour |  projectname Project Status Update after 30 seconds (This is Custom Command) |
| 38. | php artisan  projectname:statusthree | projectname Project Status Update after 30 seconds (This is Custom Command) |
| 39. | php artisan  projectname:statustwo   |            projectname Project Status Update after 30 seconds (This is Custom Command) |
| 40. | php artisan  key:generate |                   Set the application key |
| 41. | php artisan  make:cast |   Create a new custom Eloquent cast class |
| 42. | php artisan  make:channel |                   Create a new channel class |
| 43. | php artisan  make:command |                   Create a new Artisan command |
| 44. | php artisan  make:component |                Create a new view component class |
| 45. | php artisan  make:controller |               Create a new controller class |
| 46. | php artisan  make:event |  Create a new event class |
| 47. | php artisan  make:exception |                Create a new custom exception class |
| 48. | php artisan  make:factory |                   Create a new model factory |
| 49. | php artisan  make:job |    Create a new job class |
| 50. | php artisan  make:listener |                 Create a new event listener class |
| 51. | php artisan  make:mail |   Create a new email class |
| 52. | php artisan  make:middleware |                Create a new middleware class |
| 53. | php artisan  make:migration  |               Create a new migration file |
| 54. | php artisan  make:model |  Create a new Eloquent model class |
| 55. | php artisan  make:notification |              Create a new notification class |
| 56. | php artisan  make:observer |                 Create a new observer class |
| 57. | php artisan  make:policy | Create a new policy class |
| 58. | php artisan  make:provider  |                Create a new service provider class |
| 59. | php artisan  make:request |                   Create a new form request class |
| 60. | php artisan  make:resource |                 Create a new resource |
| 61. | php artisan  make:rule |   Create a new validation rule |
| 62. | php artisan  make:seeder | Create a new seeder class |
| 63. | php artisan  make:test |   Create a new test class |
| 64. | php artisan  migrate:fresh  |                Drop all tables and re-run all migrations |
| 65. | php artisan  migrate:install |               Create the migration repository |
| 66. | php artisan  migrate:refresh  |              Reset and re-run all migrations |
| 67. | php artisan  migrate:reset     |             Rollback all database migrations |
| 68. | php artisan  migrate:rollback   |            Rollback the last database migration |
| 69. | php artisan  migrate:status      |           Show the status of each migration |
| 70. | php artisan  model:prune | Prune models that are no longer needed |
| 71. | php artisan  notifications:table |           Create a migration for the notifications table |
| 72. | php artisan  optimize:clear      |           Remove the cached bootstrap files |
| 73. | php artisan  package:discover     |          Rebuild the cached package manifest |
| 74. | php artisan  passport:client       |         Create a client for issuing access tokens |
| 75. | php artisan  passport:hash          |        Hash all of the existing secrets in the clients table |
| 76. | php artisan  passport:install        |       Run the commands necessary to prepare Passport for use |
| 77. | php artisan  passport:keys          |        Create the encryption keys for API authentication |
| 78. | php artisan  passport:purge          |       Purge revoked and / or expired tokens and authentication codes    |
| 79. | php artisan  permission:cache-reset   |      Reset the permission cache |
| 80. | php artisan  permission:create-permission |   Create a permission |
| 81. | php artisan  permission:create-role    |     Create a role |
| 82. | php artisan  permission:show        |        Show a table of roles and permissions per guard |
| 83. | php artisan  queue:batches-table     |       Create a migration for the batches database table |
| 84. | php artisan  queue:checkup   |               Ensure that the queue listener is running. |
| 85. | php artisan  queue:clear | Delete all of the jobs from the specified queue |
| 86. | php artisan  queue:failed |                   List all of the failed queue jobs |
| 87. | php artisan  queue:failed-table       |      Create a migration for the failed queue jobs database table       |
| 88. | php artisan  queue:flush | Flush all of the failed queue jobs |
| 89. | php artisan  queue:forget |                   Delete a failed queue job |
| 90. | php artisan  queue:listen |                   Listen to a given queue |
| 91. | php artisan  queue:monitor  |                Monitor the size of the specified queues |
| 92. | php artisan  queue:prune-batches |            Prune stale entries from the batches database |
| 93. | php artisan  queue:prune-failed   |          Prune stale entries from the failed jobs table |
| 94. | php artisan  queue:restart         |         Restart queue worker daemons after their current job |
| 95. | php artisan  queue:retry | Retry a failed queue job |
| 96. | php artisan  queue:retry-batch     |         Retry the failed jobs for a batch |
| 97. | php artisan  queue:table | Create a migration for the queue jobs database table |
| 98. | php artisan  queue:work |  Start processing jobs on the queue as a daemon |
| 99. | php artisan  route:cache | Create a route cache file for faster route registration |
| 100. | php artisan  route:clear | Remove the route cache file |
| 101. | php artisan  route:list |  List all registered routes |
| 102. | php artisan  sail:install |                   Install Laravel Sail's default Docker Compose file |
| 103. | php artisan  sail:publish |                   Publish the Laravel Sail Docker files |
| 104. | php artisan  sanctum:prune-expired |         Prune tokens expired for more than specified number of hours.     |
| 105. | php artisan  schedule:clear-cache   |        Delete the cached mutex files created by scheduler |
| 106. | php artisan  schedule:list  |                List the scheduled commands |
| 107. | php artisan  schedule:run |                   Run the scheduled commands |
| 108. | php artisan  schedule:test           |       Run a scheduled command |
| 109. | php artisan  schedule:work            |      Start the schedule worker |
| 110. | php artisan  schema:dump | Dump the given database schema |
| 111. | php artisan  session:table |                 Create a migration for the session database table |
| 112. | php artisan  storage:link |                   Create the symbolic links configured for the application |
| 113. | php artisan  stub:publish |                   Publish all stubs that are available for customization |
| 114. | php artisan  ui:auth |     Scaffold basic login and registration views and routes |
| 115. | php artisan  ui:controllers           |      Scaffold the authentication controllers |
| 116. | php artisan  uploads:clear            |      Clears the chunks upload directory. Deletes only .part objects.   |
| 117. | php artisan  vendor:publish           |      Publish any publishable assets from vendor packages |
| 118. | php artisan  view:cache |  Compile all of the application's Blade templates |
| 119. | php artisan  view:clear |                     Clear all compiled view files |
