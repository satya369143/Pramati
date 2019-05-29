# Integrating Sentry with WaveMaker

* Sentry provides error tracking as well as some fantastic insights into what happened. It works for JavaScript as pretty much any other language we can think.

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
  * Example: `Sentry.init({dsn: 'https://4b2153b0a9274ba3afde4a5bc0499910@sentry.io/1469327'});`
  * In wavemaker, included the above line in **onAppVariablesReady** function and **onPageReady** function.
  * In your JavaScript file, we need as explicitly as the below line catch block.
  * `Sentry.captureException(err);` 
  
* Once you run the project, some where project want wrong then error log will appear in sentry dash board. 

  
