# WhatsApp-Message-Automator-using-Selenium
A Mini-Project designed to automate the process of sending messages on WhatsApp using Python. Leveraging libraries like Selenium and PyAutoGUI, this project enables users to send messages to specific contacts with minimal manual intervention. By interacting with the WhatsApp web interface programmatically.

Code-
```
import pyautogui
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.options import Options
options = webdriver.ChromeOptions()
options.add_experimental_option('excludeSwitches', ['enable-logging'])
options.add_argument("--user-data-dir=D:\\webwhatsapp")
a=input("What do u want to send?\n")
b=input("enter contact to search\n")
driver = webdriver.Chrome(options=options)
driver.get('https://web.whatsapp.com/')
print("You are Now Inside",driver.title)
screen_width, screen_height = pyautogui.size()

print("Screen width:", screen_width)
print("Screen height:", screen_height)
time.sleep(7)
search_box = driver.find_element(By.XPATH, '//div[@contenteditable="true"][@data-tab="3"]')
search_box.click()
search_box.send_keys(b)
time.sleep(2)
pyautogui.click(208,519)
message_box = driver.find_element(By.XPATH, '//div[@contenteditable="true"][@data-tab="10"]')
message_box.click()
message_box.send_keys(a)
message_box.send_keys(Keys.RETURN)
time.sleep(7)
driver.quit()
```

Images-

![Screenshot 2024-06-01 205737](https://github.com/SriHarishb/WhatsApp-Message-Automator-using-Selenium/assets/150308442/e839ac96-c238-424c-aa7e-505ef9706a51)


![Screenshot 2024-06-01 205850](https://github.com/SriHarishb/WhatsApp-Message-Automator-using-Selenium/assets/150308442/534162f5-5ca0-455e-a546-1c60b505bc9b)

Conculsion-

By interacting with the WhatsApp web interface programmatically, users can input their message content and select the recipient, allowing for efficient and streamlined communication. With its potential to save time and effort, this project offers a practical solution for those seeking to automate repetitive messaging tasks on Whatsapp.
