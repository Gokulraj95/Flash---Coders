***********OPENING WEBBROWSER*************
import webbrowser
q = input('Enter the related data search')
url  = 'https://datasetsearch.research.google.com/search?query=' + q
webbrowser.open(url)

**************ACCESS THE WEBPAGE**************
import requests
import bs4
from urllib.request import urlopen as Ureq
from bs4 import BeautifulSoup as soup
res = requests.get(url)
type(res)

***************ACCESSING THE TITLE*********
soup = bs4.BeautifulSoup(res.text, 'html')
type(soup)
titl = soup.select('h1')
print ('select the dataset title')
titl

****************MOVE TO THE DESIRED TAB**********
from selenium import webdriver
import time
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
PATH  = "C:\Program Files (x86)\chromedriver.exe"
driver = webdriver.Chrome(PATH)
driver.get(url)
login_form = driver.find_element_by_xpath("//h1[contains(text(), 'Health Analytics')]")
login_form.click()


