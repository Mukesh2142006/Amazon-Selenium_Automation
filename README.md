# Amazon Selenium Automation
# 06/10/2026
# NAME: Mukesh B

An automated Python script built with **Selenium WebDriver** to automate the shopping workflow on Amazon India, including user authentication, product search, cart management, and checkout redirection.

##  Features

- **Automated Login:** Signs into an Amazon India account securely.
- **Product Search:** Searches for a specified item ("OnePlus Nord Buds" by default) using dynamic locators.
- **Cart Integration:** Navigates search results, selects a matching product, and adds it to the shopping cart.
- **Checkout Flow:** Navigates to the cart and triggers the proceed-to-checkout sequence.
-.

---

##  Prerequisites

Make sure you have the following installed on your machine:
- **Python** (v3.8 or higher)
- **Google Chrome** browser
- **ChromeDriver** (automatically managed by Selenium Manager in modern versions)

---

code
```
import time

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys

driver = webdriver.Chrome()

driver.get("https://www.amazon.in/")

time.sleep(10)

search = driver.find_element(By.ID, "twotabsearchtextbox")
search.send_keys("Watch for men")
search.send_keys(Keys.RETURN)

time.sleep(10)

product = driver.find_element(By.CSS_SELECTOR, "[data-component-type='s-search-result'] h2")
product.click()

time.sleep(5)

tabs = driver.window_handles
driver.switch_to.window(tabs[1])

time.sleep(10)

add_cart = driver.find_element(By.ID, "add-to-cart-button")
add_cart.click()

time.sleep(10)

cart = driver.find_element(By.ID, "nav-cart")
cart.click()

time.sleep(10)

items = driver.find_elements(By.CSS_SELECTOR, "div.sc-list-item")

print("Number of items in cart:", len(items))

time.sleep(5)

driver.quit()
```

## output:
   <img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/623e8968-ca48-4430-8152-d26f2afeb95f" />
   <img width="1917" height="1075" alt="image" src="https://github.com/user-attachments/assets/f3cb0a21-0e55-4c1f-8338-9d2b1304f1fe" />
  <img width="1917" height="1065" alt="image" src="https://github.com/user-attachments/assets/7e246f69-6f6e-4400-a69a-9fbb94693401" />
  <img width="1917" height="613" alt="image" src="https://github.com/user-attachments/assets/9d96e0a5-2742-4bc6-9e6a-39f7e2b858f0" />


##  Conclusion

This project demonstrates the practical application of **Selenium WebDriver** for end-to-end browser automation and web scraping. By automating user authentication, dynamic element location, cart management, and checkout navigation, it highlights key test automation principles such as explicit waits and robust error handling. 
