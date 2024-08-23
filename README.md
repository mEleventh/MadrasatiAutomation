# madrasati
تجربة الاتمتة في منصة مدرستي باستخدام سيلينيوم و قوقل درايف
التجربة ناجحة واعتقد ان الفائدة من هذه التقنية لا حدود لها 




#### اهم الطلبات 

#### إنشاء متصفح
```
driver = webdriver.Chrome()  # أو أي متصفح آخر
```
#### التنقل
##### فتح صفحة
```
driver.get("https://www.example.com")
```
##### الرجوع للصفحة السابقة
```
driver.back()
```
##### الانتقال للصفحة التالية
```
driver.forward()
```
##### تحديث الصفحة
```
driver.refresh() 
```


#### العثور على العناصر
```
element = driver.find_element(By.ID, "element_id")
```
```
elements = driver.find_elements(By.CLASS_NAME, "class_name")
```

##### طرق أخرى: By.NAME, By.TAG_NAME, By.LINK_TEXT, By.PARTIAL_LINK_TEXT, By.XPATH, By.CSS_SELECTOR

#### التفاعل مع العناصر

##### النقر على العنصر
```
element.click()
```

##### ادخال نص

```
element.send_keys("text")
```
##### مسح النص من الحقل

```
element.clear()
```
##### ارسال نموذج
```
element.submit() 
```

#### الحصول على معلومات

#####  الحصول على النص الظاهر للعنصر
```
element.text
```

#####  الحصول على قيمة سمة معينة

```
element.get_attribute("attribute_name")  
```

#####  الحصول على عنوان الصفحة
```
driver.title  
```
##### الحصول على URL الحالي
```
driver.current_url  
```


#### الانتظار


#####   إنشاء انتظار لمدة 10 ثوانٍ
```
wait = WebDriverWait(driver, 10)
```

##### الانتظار حتى ظهور عنصر
```
element = wait.until(EC.presence_of_element_located((By.ID, "element_id"))) 
```



#### التعامل مع النوافذ والإطارات

##### التبديل إلى النافذة الأخيرة

```
driver.switch_to.window(driver.window_handles[-1]) 
```


#####   التبديل إلى إطار معين
```
driver.switch_to.frame("frame_name") 
```
##### العودة إلى المحتوى الرئيسي
```
driver.switch_to.default_content()  
```


##### JavaScript

```
driver.execute_script("return document.title;")  #   سكربت ل JavaScript
```

#### لقطات الشاشة

##### التقاط لقطة شاشة
```
driver.save_screenshot("screenshot.png") 
```


#### الكوكيز

#####  إضافة كوكي
```
driver.add_cookie({"name": "cookie_name", "value": "cookie_value"})  
```

##### الحصول على جميع الكوكيز
```
driver.get_cookies() 
```


#### التنقل في القوائم المنسدلة
```
from selenium.webdriver.support.ui import Select
select = Select(driver.find_element(By.ID, "dropdown_id"))
```

#####  اختيار بواسطة النص الظاهر

```
select.select_by_visible_text("Option Text")  
```

#####  اختيار بواسطة القيمة
```
select.select_by_value("value") 
```


##### اختيار بواسطة الفهرس
```
select.select_by_index(1)  
```

#### السحب والإفلات
```
from selenium.webdriver.common.action_chains import ActionChains
source = driver.find_element(By.ID, "source")
target = driver.find_element(By.ID, "target")
ActionChains(driver).drag_and_drop(source, target).perform()
```


#### إغلاق المتصفح

######   إغلاق النافذة الحالية
```
driver.close() 
```

##### إغلاق جميع النوافذ وإنهاء عملية WebDriver
```
driver.quit()  
```
