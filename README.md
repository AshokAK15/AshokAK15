- 👋 Hi, I’m @AshokAK15
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
AshokAK15/AshokAK15 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
package com.SeleniumPractice;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

/**
 * @author Yadagiri Reddy
 * How to find the elements using selenium webdriver?
 */
public class TestElementFindingStrategies {

	public static void main(String[] args) throws Exception {
		WebDriverManager.chromedriver().setup();
		WebDriver driver = new ChromeDriver();
		driver.get("https://github.com/login");
		Thread.sleep(3000);		
		highlight(driver, driver.findElement(By.id("login_field")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.name("password")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.className("header-logo")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.linkText("Forgot password?")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.partialLinkText("Create an")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.tagName("h1")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.xpath("//label[contains(text(),'Username or email address')]")));
		Thread.sleep(3000);
		highlight(driver, driver.findElement(By.cssSelector("input[name='commit']")));		
	}
	
	public static void highlight(WebDriver driver, WebElement element) {
		JavascriptExecutor jsExecutor = (JavascriptExecutor) driver;
		jsExecutor.executeScript("arguments[0].setAttribute('style', 'border:2px solid red; background:yellow')", element);
	}

}
