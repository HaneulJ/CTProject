# 구글 이미지 크롤링 Selenium

Created By: 대영 전
Last Edited By: 하늘 정
Status: In Progress

```python
first_list = ['마스크', '코로나 예방', '코로나']
second_list = ['얼굴', '회사원', '착용 얼굴', '직장']
browser = webdriver.Chrome('C:/Temp/chromedriver.exe')

for first in first_list:
    for second in second_list:
        new_query = first + " " + second
        url = "https://www.google.com/search?q=" + new_query + "&tbm=isch"
        browser.get(url)
        
        for i in range(200):
            browser.execute_script('window.scrollBy(0,10000)')
    
        for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
            el.screenshot("./img/" + str(idx) + ".png")
            time.sleep(1)

# 이랬더니 str(idx)로 인해 자꾸 사진이 리셋... 
```

```python
# 검색어별로 img폴더 따로 만들어서 추출
search_term = '마스크 얼굴'
url = "https://www.google.com/search?q=" + search_term + "&tbm=isch"

browser = webdriver.Chrome('C:/Temp/chromedriver.exe')
browser.get(url)

for i in range(200):
    browser.execute_script('window.scrollBy(0,10000)')
    
for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
    el.screenshot("./img/" + str(idx) + ".png")
    time.sleep(1)

search_term = '마스크 사람'
url = "https://www.google.com/search?q=" + search_term + "&tbm=isch"

browser = webdriver.Chrome('C:/Temp/chromedriver.exe')
browser.get(url)

for i in range(200):
    browser.execute_script('window.scrollBy(0,10000)')
    
for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
    el.screenshot("./img2/" + str(idx) + ".png")
    time.sleep(1)

search_term = '마스크 회사원'
url = "https://www.google.com/search?q=" + search_term + "&tbm=isch"

browser = webdriver.Chrome('C:/Temp/chromedriver.exe')
browser.get(url)

for i in range(200):
    browser.execute_script('window.scrollBy(0,10000)')
    
for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
    el.screenshot("./img3/" + str(idx) + ".png")
    time.sleep(1)

search_term = '마스크 착용 얼굴'
url = "https://www.google.com/search?q=" + search_term + "&tbm=isch"

browser = webdriver.Chrome('C:/Temp/chromedriver.exe')
browser.get(url)

for i in range(200):
    browser.execute_script('window.scrollBy(0,10000)')
    
for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
    el.screenshot("./img4/" + str(idx) + ".png")
    time.sleep(1)

search_term = '마스크 직장'
url = "https://www.google.com/search?q=" + search_term + "&tbm=isch"

browser = webdriver.Chrome('C:/Temp/chromedriver.exe')
browser.get(url)

for i in range(200):
    browser.execute_script('window.scrollBy(0,10000)')
    
for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
    el.screenshot("./img5/" + str(idx) + ".png")
    time.sleep(1)

search_term = '마스크 연예인'
url = "https://www.google.com/search?q=" + search_term + "&tbm=isch"

browser = webdriver.Chrome('C:/Temp/chromedriver.exe')
browser.get(url)

for i in range(200):
    browser.execute_script('window.scrollBy(0,10000)')
    
for idx, el in enumerate(browser.find_elements_by_class_name("rg_i.Q4LuWd")):
    el.screenshot("./img6/" + str(idx) + ".png")
    time.sleep(1)
```

- 전처리 수행 전, 2000장 정도

[img.zip](%E1%84%80%E1%85%AE%E1%84%80%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5%20%E1%84%8F%E1%85%B3%E1%84%85%E1%85%A9%E1%86%AF%E1%84%85%E1%85%B5%E1%86%BC%20Selenium%209078184bcbad4d4bb93c22d825f4619b/img.zip)