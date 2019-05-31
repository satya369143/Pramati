# Integrating Sentry with WaveMaker

### **<u>Sentry</u>**:

* Sentry is an open source solution that serves as a real-time summary and registration platform for events. It monitors errors and indicates when, where and to whom they occur, without relying solely on user feedback. Supported languages and frameworks include JavaScript, Ruby, Python, Java, and more.

* **Pros:**
  * See the impact of new implementations in real time.
  * Provide support to specific users interrupted by an error.
  * External Integration's – GitHub, HipChat, Heroku, and many more.

* **Cons:**
  * The documentation is quite limited.
  * If you don't use one of the compatible frameworks, the alternative is a manual configuration.

* Before Sentry arrives, if something goes wrong in frontend to identify the error the people will go through code manually.

* After sentry arrives, it is using for both frontend and backend to track the errors in client side.

* With sentry, We easily understand the error because it indicates when, where, to whom they occur and type of error.

* Sentry helps you answer these questions as it integrates with your existing workflow.

* There is an error, Sentry detects it immediately and alerts you via email, Slack, PagerDuty or one of many other additions based on your notification rules

* Simpler products like **Sentry**:

* - Honeybadger
  - TrackJS JavaScript Error Logging
  - Raygun
  - Rollbar
  - LogRocket etc.,

### <u>**Integartion Process:**</u>

* [Go to Sentry](https://sentry.io/)

* Sign up for an account.

* Create a new project by selecting one of the technology.

* Install your Software development kit (SDK).

* For installing add below line in File Path: Project: Project Name > src/main/webapp/index.html

* - <script src="https://browser.sentry-cdn.com/5.3.0/bundle.min.js" crossorigin="anonymous"></script>

* Configure the Software development kit (SDK).

* For configure add below line in File Path: Project: Project Name > src/main/webapp/app.js

* - Sentry.init({ dsn: 'https://<key>@sentry.io/<project>' });

  - You should init the Sentry Browser SDK as soon as possible during your page load.

  - Example: Sentry.init({dsn: 'https://xxxxxxxxxxxxxxxxxxxxx@sentry.io/xxxxxx'});

  - In wavemaker, included the above line in **onAppVariablesReady** function and **onPageReady** function.

    

    ```App.onAppVariablesReady = function() {
    App.onAppVariablesReady = function() {
      Sentry.init({
      dsn: 'https://xxxxxxxxxxxxxxxx@sentry.io/xxxxxx});
    };
    App.onPageReady = function(activePageName, activePageScope, $activePageEl) {
      Sentry.init({
      dsn: 'https://xxxxxxxxxxxxxxxxx@sentry.io/xxxxxx});
    };
    ```

  - In your JavaScript file, we need as explicitly as the below line catch block.

  - ` Sentry.captureException(err);`

    

* - ```Page.text5Blur = function($event, widget) {
        try {
            var a = /^\d{4}\d{4}\d{4}$/;
            var b = Page.Widgets.text5.datavalue;
            if (b.match(a)) {
                return true;
            } else {
                alert('xyz is wrong.');
                return false;
            }
        } catch (err) {
            Sentry.captureException(err);
        }
    };
    ```

  - 

* Once you run the project, some where project want wrong then error log will appear in sentry dash board. 

* ![img](https://lh6.googleusercontent.com/U5aE2bhnPBW_9PQbNbJWhrnjA33WSEusLJRQksVQOZGs1x_lbsJ7J9RObH8rXzfy3TuQKCp5_RL225nMSQg9NKrPsLzJ5CqWkj7_-4ciuHhx9nahYkrYKE8aRZF7zRcLAUraFYiT)

* When you click on the issue, a detailed information shown for failure.

* ![img](https://lh4.googleusercontent.com/kg_6tIMyPG6XrB4ryCE6q16qPf23_gprhDgoNj1UcBCC6SbcvK7_5YQZ5MxQQRbJI2U07CHwP6P5tX_XYr6xswTHydq5l11K0cIgdINetEIg0ATgXkjiVb8azuYLiADv4AkPvY3k)
