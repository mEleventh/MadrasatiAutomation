# madrasati
تجربة الاتمتة في منصة مدرستي باستخدام سيلينيوم و قوقل درايف
التجربة ناجحة واعتقد ان الفائدة من هذه التقنية لا حدود لها 




#### اهم الطلبات 

#### إنشاء متصفح
driver = webdriver.Chrome()  # أو أي متصفح آخر

#### التنقل
driver.get("https://www.example.com")  # فتح صفحة
driver.back()  # الرجوع للصفحة السابقة
driver.forward()  # الانتقال للصفحة التالية
driver.refresh()  # تحديث الصفحة

#### العثور على العناصر
element = driver.find_element(By.ID, "element_id")
elements = driver.find_elements(By.CLASS_NAME, "class_name")
#### طرق أخرى: By.NAME, By.TAG_NAME, By.LINK_TEXT, By.PARTIAL_LINK_TEXT, By.XPATH, By.CSS_SELECTOR

#### التفاعل مع العناصر
element.click()  # النقر على عنصر
element.send_keys("text")  # إدخال نص
element.clear()  # مسح النص من حقل الإدخال
element.submit()  # إرسال نموذج

#### الحصول على معلومات
element.text  # الحصول على النص الظاهر للعنصر
element.get_attribute("attribute_name")  # الحصول على قيمة سمة معينة
driver.title  # الحصول على عنوان الصفحة
driver.current_url  # الحصول على URL الحالي

#### الانتظار
wait = WebDriverWait(driver, 10)  # إنشاء كائن انتظار لمدة 10 ثوانٍ
element = wait.until(EC.presence_of_element_located((By.ID, "element_id")))  # الانتظار حتى ظهور عنصر

#### التعامل مع النوافذ والإطارات
driver.switch_to.window(driver.window_handles[-1])  # التبديل إلى النافذة الأخيرة
driver.switch_to.frame("frame_name")  # التبديل إلى إطار معين
driver.switch_to.default_content()  # العودة إلى المحتوى الرئيسي

# JavaScript
driver.execute_script("return document.title;")  # تنفيذ JavaScript

#### لقطات الشاشة
driver.save_screenshot("screenshot.png")  # التقاط لقطة شاشة

#### الكوكيز
driver.add_cookie({"name": "cookie_name", "value": "cookie_value"})  # إضافة كوكي
driver.get_cookies()  # الحصول على جميع الكوكيز

#### التنقل في القوائم المنسدلة
from selenium.webdriver.support.ui import Select
select = Select(driver.find_element(By.ID, "dropdown_id"))
select.select_by_visible_text("Option Text")  # اختيار بواسطة النص الظاهر
select.select_by_value("value")  # اختيار بواسطة القيمة
select.select_by_index(1)  # اختيار بواسطة الفهرس

#### السحب والإفلات
from selenium.webdriver.common.action_chains import ActionChains
source = driver.find_element(By.ID, "source")
target = driver.find_element(By.ID, "target")
ActionChains(driver).drag_and_drop(source, target).perform()

#### إغلاق المتصفح
driver.close()  # إغلاق النافذة الحالية
driver.quit()  # إغلاق جميع النوافذ وإنهاء عملية WebDriver

