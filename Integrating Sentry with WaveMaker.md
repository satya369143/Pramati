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

### <u>**Integartion Process:**</u>

* Go to Sentry Page [click here](https://sentry.io/welcome/).

* Sign up for an account.

* Create a new project by selecting one of the technology. 

* Install your Software development kit (SDK).

* For installing add below line in File Path: Project: Project Name > src/main/webapp/index.html

  * <script src="https://browser.sentry-cdn.com/5.3.0/bundle.min.js" crossorigin="anonymous"></script>

* Configure the Software development kit (SDK).

* For configure add below line in File Path: Project: Project Name > src/main/webapp/app.js

  * ```Sentry.init({ dsn: 'https://<key>@sentry.io/<project>' });```
  * You should `init` the Sentry Browser SDK as soon as possible during your page load.
  * Example: `Sentry.init({dsn: 'https://xxxxxxxxxxxxxxxxxxxxx@sentry.io/xxxxxx'});`
  * In wavemaker, included the above line in **onAppVariablesReady** function and **onPageReady** function.
  * ![1559115722352](/home/satya369/.config/Typora/typora-user-images/1559115722352.png)
  * In your JavaScript file, we need as explicitly as the below line catch block.
  * `Sentry.captureException(err);`
  * ![1559115817585](/home/satya369/.config/Typora/typora-user-images/1559115817585.png) 
  
* Once you run the project, some where project want wrong then error log will appear in sentry dash board. 

* ![1559114597779](/home/satya369/.config/Typora/typora-user-images/1559114597779.png)

* When you click on the issue, a detailed information shown for failure.

* ![1559114297248](/home/satya369/.config/Typora/typora-user-images/1559114297248.png)
