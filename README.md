# WhatsApp-Message-Automator-using-Selenium
A Mini-Project designed to automate the process of sending messages on WhatsApp using Python. Leveraging libraries like Selenium and PyAutoGUI, this project enables users to send messages to specific contacts with minimal manual intervention. By interacting with the WhatsApp web interface programmatically.

Code-
'''
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
'''
