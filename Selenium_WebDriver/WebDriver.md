# Selenium WebDriver

- ### Installing Selenium WebDriver

  - WebDriver is a tool for testing web applications across different browsers using different programming languages.
  - Install WebDriver (Java) and configure with IntelliJ IDEA.
  - Before downloading WebDriver make sure that you have Java JDK installed on your system.
  - We can download and install this WebDriver from [here](https://www.seleniumhq.org/download/).
  - Unzip the ZIP file on your C drive so that you would have the directory "C:\selenium-java-3.141.59".
  - Launch the IntelliJ IDEA, After that
    - File -> New -> Project -> Java -> Project Name.
    - Inside Project, Right click on src -> New -> Package.
    - Right click on package -> New -> Java Class.
    - For adding Libraries, Press Ctrl + Alt + Shift + s. Then project structure window will be opened. 
    - Click on Libraries,
      - click  **+** symbol -> Java -> C:\selenium-java-3.141.59\libs -> OK.
      - click  **+** symbol -> Java -> C:\selenium-java-3.141.59\client-combined-3.141.59-sources.jar -> OK.
      - click Apply -> OK.
  - We can download and install this ChromeDriver from [here](https://chromedriver.storage.googleapis.com/index.html?path=2.4/).
  - Unzip the ZIP file on your C drive so that you would have the directory "C:\chromedriver_win32".
  - Creating the script for Login module in WebDriver.

```
package Satya;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.Test;

public class Krishna {

    public static void main(String [] args) throws InterruptedException{
    
        System.setProperty("webdriver.chrome.driver", "C:\chromedriver_win32");
        ChromeOptions chromeOptions = new ChromeOptions();
        chromeOptions.addArguments("--start-maximized");
        WebDriver driver = new ChromeDriver(chromeOptions);
        WebDriverWait myWait = new WebDriverWait(driver,20);
        driver.get("https://www.facebook.com/");

        myWait.until(ExpectedConditions.visibilityOfElementLocated(By.cssSelector(".login_button")));
        driver.findElement(By.cssSelector(".login_button")).click();
        myWait.until(ExpectedConditions.visibilityOfElementLocated(By.id("user_email")));
        driver.findElement(By.id("user_email")).sendKeys("xyz@gmail.com");

        myWait.until(ExpectedConditions.visibilityOfElementLocated(By.id("user_password")));
        driver.findElement(By.id("user_password")).sendKeys("xyz");

        myWait.until(ExpectedConditions.visibilityOfElementLocated(By.name("commit")));
        driver.findElement(By.name("submmit")).click();

        String tagName = driver.findElement(By.id("searchq")).getTagName();
        System.out.println(tagName);
        driver.close();
}
}
```

- To run program, press Alt + Shift + F10.
