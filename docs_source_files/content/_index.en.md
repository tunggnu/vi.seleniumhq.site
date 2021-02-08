---
title: "Dự án Selenium Tự động hóa Trình duyệt"
---

# Dự án Selenium Tự động hóa Trình duyệt

Selenium là một dự án tổng hợp của một loạt các công cụ và thư viện
cho phép và hỗ trợ tự động hóa các trình duyệt web.

Nó cung cấp các tiện ích mở rộng để mô phỏng sự tương tác của
người dùng với các trình duyệt, một máy chủ phân tán để mở rộng
việc phân bổ trình duyệt, và cơ sở hạ tầng để triển khai
[đặc tả W3C WebDriver](//www.w3.org/TR/webdriver/)
cho phép bạn viết mã có thể chạy trên tất cả các trình duyệt web chính.

Dự án này được thực hiện bởi những người đóng góp tình nguyện,
những người đã dành hàng nghìn giờ của mình
để khiến mã nguồn [luôn có sẵn]({{< ref "/front_matter/copyright_and_attributions.en.md#license" >}})
cho mọi người thoải mái sử dụng, tận hưởng và cải tiến.

Selenium tập hợp các nhà cung cấp trình duyệt, kỹ sư và những
người đam mê để xúc tiến một cuộc thảo luận cởi mở về tự động hóa
nền tảng web. Dự án tổ chức [hội nghị thường niên](//seleniumconf.com/)
để giảng dạy và nuôi dưỡng cộng đồng.

Cốt lõi của Selenium là _[WebDriver]({{< ref "/webdriver/_index.md" >}})_,
một *giao diện* để viết các tập chỉ thị có thể chạy trên nhiều trình duyệt.
Đây là một trong những chỉ thị đơn giản nhất mà bạn có thể làm ra:

{{< code-tab >}}
  {{< code-panel language="java" >}}
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.WebDriverWait;
import static org.openqa.selenium.support.ui.ExpectedConditions.presenceOfElementLocated;
import java.time.Duration;

public class HelloSelenium {

    public static void main(String[] args) {
        WebDriver driver = new FirefoxDriver();
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
        try {
            driver.get("https://google.com/ncr");
            driver.findElement(By.name("q")).sendKeys("cheese" + Keys.ENTER);
            WebElement firstResult = wait.until(presenceOfElementLocated(By.cssSelector("h3>div")));
            System.out.println(firstResult.getAttribute("textContent"));
        } finally {
            driver.quit();
        }
    }
}
  {{< / code-panel >}}
  {{< code-panel language="python" >}}
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support.expected_conditions import presence_of_element_located

#Ví dụ này yêu cầu Selenium WebDriver 3.13 hoặc mới hơn
with webdriver.Firefox() as driver:
    wait = WebDriverWait(driver, 10)
    driver.get("https://google.com/ncr")
    driver.find_element(By.NAME, "q").send_keys("cheese" + Keys.RETURN)
    first_result = wait.until(presence_of_element_located((By.CSS_SELECTOR, "h3>div")))
    print(first_result.get_attribute("textContent"))
  {{< / code-panel >}}
  {{< code-panel language="csharp" >}}
using System;
using OpenQA.Selenium;
using OpenQA.Selenium.Firefox;
using OpenQA.Selenium.Support.UI;

class HelloSelenium {
  static void Main() {
    using(IWebDriver driver = new FirefoxDriver()) {
      WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(10));
      driver.Navigate().GoToUrl("https://www.google.com/ncr");
      driver.FindElement(By.Name("q")).SendKeys("cheese" + Keys.Enter);
      wait.Until(webDriver => webDriver.FindElement(By.CssSelector("h3>div")).Displayed);
      IWebElement firstResult = driver.FindElement(By.CssSelector("h3>div"));
      Console.WriteLine(firstResult.GetAttribute("textContent"));
    }
  }
}
  {{< / code-panel >}}
  {{< code-panel language="ruby" >}}
require 'selenium-webdriver'

driver = Selenium::WebDriver.for :firefox
wait = Selenium::WebDriver::Wait.new(timeout: 10)

begin
  driver.get 'https://google.com/ncr'
  driver.find_element(name: 'q').send_keys 'cheese', :return
  first_result = wait.until { driver.find_element(css: 'h3>div') }
  puts first_result.attribute('textContent')
ensure
  driver.quit
end
  {{< / code-panel >}}
  {{< code-panel language="javascript" >}}
const {Builder, By, Key, until} = require('selenium-webdriver');

(async function example() {
    let driver = await new Builder().forBrowser('firefox').build();
    try {
        // Navigate to Url
        await driver.get('https://www.google.com');

        // Enter text "cheese" and perform keyboard action "Enter"
        await driver.findElement(By.name('q')).sendKeys('cheese', Key.ENTER);

        let firstResult = await driver.wait(until.elementLocated(By.css('h3>div')), 10000);

        console.log(await firstResult.getAttribute('textContent'));
    }
    finally{
        driver.quit();
    }
})();
  {{< / code-panel >}}
  {{< code-panel language="kotlin" >}}
import org.openqa.selenium.By
import org.openqa.selenium.Keys
import org.openqa.selenium.firefox.FirefoxDriver
import org.openqa.selenium.support.ui.ExpectedConditions.presenceOfElementLocated
import org.openqa.selenium.support.ui.WebDriverWait
import java.time.Duration

fun main() {
    val driver = FirefoxDriver()
    val wait = WebDriverWait(driver, Duration.ofSeconds(10))
    try {
        driver.get("https://google.com/ncr")
        driver.findElement(By.name("q")).sendKeys("cheese" + Keys.ENTER)
        val firstResult = wait.until(presenceOfElementLocated(By.cssSelector("h3>div")))
        println(firstResult.getAttribute("textContent"))
    } finally {
        driver.quit()
    }
}
  {{< / code-panel >}}
{{< / code-tab >}}


Hãy xem mục _[Tham quan nhanh]({{< ref "/getting_started/quick.en.md" >}})_ để có giải thích đầy đủ
về những gì diễn ra đằng sau khi bạn chạy mã này.
Bạn nên tiếp tục xem [tài liệu giới thiệu]({{< ref "/introduction/_index.md" >}})
để hiểu cách bạn có thể [cài đặt]({{< ref "/selenium_installation/_index.md" >}}) và
sử dụng thành công Selenium như một công cụ tự động hóa việc thử nghiệm,
và mở rộng các thử nghiệm đơn giản như thế này để chạy trong
các môi trường lớn, phân tán trên nhiều trình duyệt,
trên một số hệ điều hành khác nhau.

## Bắt đầu

Nếu bạn chưa quen với Selenium,
chúng tôi có một số tài nguyên có thể giúp bạn
có tất cả thông tin mới nhất ngay lập tức.

* [Tham quan nhanh]({{< ref "/getting_started/quick.en.md" >}})
  * [WebDriver]({{< ref "/getting_started/quick.en.md#webdriver" >}})
  * [IDE]({{< ref "/getting_started/quick.en.md#ide" >}})
  * [Grid]({{< ref "/getting_started/quick.en.md#grid" >}})
