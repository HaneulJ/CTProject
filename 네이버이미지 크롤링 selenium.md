# 네이버 이미지 크롤링 selenium

Created By: 대영 전
Last Edited By: 하늘 정

```python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time
import urllib.request

driver = webdriver.Chrome('C:/Temp/chromedriver.exe')
driver.get("[https://search.naver.com/search.naver?where=image&sm=tab_jum&query=](https://search.naver.com/search.naver?where=image&sm=tab_jum&query=)")
elem = driver.find_element_by_name("query")
elem.send_keys("뮤직뱅크 출근")
elem.send_keys(Keys.RETURN)

SCROLL_PAUSE_TIME = 1

last_height = driver.execute_script("return document.body.scrollHeight")

while True:
driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")

```python
time.sleep(SCROLL_PAUSE_TIME)

new_height = driver.execute_script("return document.body.scrollHeight")
if new_height == last_height:
    break
last_height = new_height

```

images = driver.find_elements_by_css_selector("._image._listImage")
count = 1
for image in images:
try:
image.click()
time.sleep(2)
imgUrl = driver.find_element_by_xpath('//*[@id="main_pack"]/section/div[2]/div[2]/div/div[1]/div[1]/div[1]/div/div/div[1]/div[1]/img').get_attribute("src")
urllib.request.urlretrieve(imgUrl, str(count) + ".jpg")

```python
    with urlopen(imgUrl) as f:
        with open('./img/' + plusUrl + str(n)+'.jpg','wb') as h: # 이미지 + 사진번호 + 확장자는 jpg
            img = f.read() #이미지 읽기
            h.write(img) # 이미지 저장
    count = count + 1
except:
    pass

```

driver.close()
#사진 하나씩 클릭해서 저장하느라 오래걸림
#단축하고 싶으면 image.click() 지울것
```