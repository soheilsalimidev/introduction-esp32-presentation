---
theme: penguin
class: text-center
colorSchema: 'auto'
highlighter: prism
lineNumbers: false
info: Esp32 and why is it important in IoT, with code
drawings:
  persist: false
transition: slide-left
title: Esp32
layout: intro
mdc: true
dir: rtl
fonts:
  sans: 'iranyekanwebregular'
  local: 'iranyekanwebregular'
htmlAttrs:
  dir: 'rtl'
  lang: 'fa'
---

# Esp32 and why is it important in IoT, with code

**professor Jamshidi**

---
---

# فهرست مطالب

مباحثی که می خوایم در موردشون حرف بزنیم

- 🖥 **ESP32** - مقدمه ای بر برد esp 32  بررسی انواع مختلف ورژنها و قابلیت های esp32
- 📤 **ESP32 در IoT** - بررسی روند کارکردی esp32  و بررسی esp32در IoT
- 📍 **ESP32 Pins** - معرفی انواع و کاربرد های پین ها  در Esp32
- 🛠 **ESP32 example project** - ساخت یک RGB Stripe


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  font-family: iranyekanwebregular
}
</style>

---
layout: full
---
<Intro />

---
layout: new-section
---

# مقدمه ایی بر esp32

![esp32](/Adafruit-AirLift-Featherwing.gif)

---
---
# ESP 32  چیست؟

ESP32 یک سری از میکروکنترلرهای کم هزینه و کم مصرف با قابلیت اتصال به Wi-Fi و بلوتوث دو حالته است. این میکروکنترلرها توسط شرکت Espressif Systems در شانگهای چین طراحی و توسط TSMC با فرآیند 40 نانومتری تولید می شوند1 ESP32 دارای پردازنده های Xtensa LX6 یا LX7 دو هسته ای یا تک هسته ای 32 بیتی، حافظه RAM و ROM، مدیریت توان، مدارات امنیتی، مبدل های آنالوگ به دیجیتال و دیجیتال به آنالوگ، رابط های SPI، I2C، UART، SDIO، CAN و Ethernet و سنسورهای لمسی است12 ESP32 می تواند به عنوان یک سیستم مستقل یا به عنوان یک دستگاه برده به یک میکروکنترلر میزبان عمل کند و از طریق رابط های SPI / SDIO یا I2C / UART با سیستم های دیگر ارتباط برقرار کند2 ESP32 خانواده ای از میکروکنترلرها را تشکیل می دهد که دارای ویژگی ها و قابلیت های مختلفی هستند1

---
---
# کاربرد های ESP 32
ESP32 یک میکروکنترلر کم هزینه و کم مصرف با قابلیت اتصال به Wi-Fi و بلوتوث دو حالته است که برای پروژه های اینترنت اشیا (IoT) مناسب است. ESP32 می تواند در بسیاری از دستگاه های هوشمند کاربرد داشته باشد. برخی از کاربردهای رایج ESP32 عبارتند از:

- دستگاه های صنعتی هوشمند، از جمله کنترل کننده های منطقی برنامه پذیر (PLC)
- دستگاه های پزشکی هوشمند، از جمله مانیتورهای سلامت قابل پوشیدن
- دستگاه های انرژی هوشمند، از جمله HVAC و ترموستات
- دستگاه های امنیتی هوشمند، از جمله دوربین های نظارتی و قفل های هوشمند

---
layout: new-section
---
# نسخه های ESP 32
![esp32](/ESP32-Board-Espressif-Example-1.jpg.webp)

---
layout:  text-image
media: '/ESP32-Board.jpg'
---
# versions of esp32 

ز زمان عرضه ESP32 اصلی، تعدادی از انواع آن معرفی و اعلام شده است. آنها خانواده میکروکنترلرهای ESP32 را تشکیل می دهند. این تراشه‌ها پردازنده‌ها و قابلیت‌های متفاوتی دارند، اما همگی SDK یکسانی دارند و تا حد زیادی با کد سازگار هستند. علاوه بر این، ESP32 اصلی تجدید نظر شد (به عنوان مثال ESP32 ECO V3 را ببینید

---
---
# ESP32

<div class="flex">
<p>
ESP32
<ul>
<li>Xtensa single-/dual-core 32-bit LX6 microprocessor(s)</li>
<li>Wi-Fi: 802.11 b/g/n</li>
<li>Bluetooth: v4.2 BR/EDR and BLE (shares the radio with Wi-Fi)</li>
<li>34 × programmable GPIOs</li>
<li>12-bit SAR ADC up to 18 channels</li>
<li>2 x 8-bit DAC</li>
</ul>
</p>

<p>
ESP32-S3
<ul>
<li>Dual-core Xtensa LX7 CPU, up to 240 MHz,[10]</li>
<li>Added instructions to accelerate machine learning applications</li>
<li>512 KiB SRAM, 384 KiB ROM, and 16 KiB RTC SRAM</li>
<li>Ultra-low power RISC-V coprocessor clocked at 17.5 MHz</li>
<li>Ultra-low power FSM coprocessor similar to previous ESP32 and ESP32-S2</li>
<li>Wi-Fi 2.4 GHz (IEEE 802.11 b/g/n)</li>
<li>Bluetooth 5 (LE)</li>
<li>44 programmable GPIOs</li>
<li>USB OTG</li>
</ul>
</p>
</div>

---
---
# MCU چیست؟
 مخفف "واحد میکروکنترلر" است. این یک کامپیوتر کوچک روی یک مدار مجتمع است که شامل هسته پردازنده، حافظه و تجهیزات جانبی ورودی/خروجی قابل برنامه ریزی است. MCU ها در طیف گسترده ای از کاربردها از جمله لوازم الکترونیکی مصرفی، سیستم های خودرو، دستگاه های پزشکی و اتوماسیون صنعتی استفاده می شوند. آنها به گونه ای طراحی شده اند که توان کم، کم هزینه و بسیار قابل اعتماد باشند. برخی از برندهای معروف MCU عبارتند از Atmel، Freescale، Microchip و Texas Instruments

---
---
# ESP 32 in IoT

اهمیت ESP32 در اینترنت اشیا این است که یک میکروکنترلر کم هزینه، کم مصرف و همه کاره است که می تواند از اتصال Wi-Fi و بلوتوث و همچنین طیف وسیعی از تجهیزات جانبی و سنسورها پشتیبانی کند. ESP32 را می توان برای کاربردهای مختلف اینترنت اشیا مانند اتوماسیون خانگی، دستگاه های پوشیدنی، انرژی هوشمند، سیستم های امنیتی و غیره استفاده کرد. ESP32 همچنین با Arduino IDE و دیگر پلتفرم‌های توسعه سازگار است و ایجاد پروژه‌های IoT را برای علاقه‌مندان و توسعه‌دهندگان آسان می‌کند. برخی از مزایای ESP32 برای اینترنت اشیا عبارتند از:

- دارای یک پردازنده دو هسته ای است که می تواند تا 240 مگاهرتز کار کند و عملکرد بالا و قابلیت های چند وظیفه ای را ارائه می دهد.
- دارای ماژول های Wi-Fi و بلوتوث است که می تواند در حالت دوگانه کار کند و امکان ارتباط همزمان با دستگاه ها و شبکه های دیگر را فراهم می کند.
- دارای حالت مصرف کم انرژی است که می تواند عمر باتری دستگاه های IoT را افزایش دهد و همچنین حالت خواب عمیق دارد که می تواند در رویدادهای خارجی یا تایمرها بیدار شود.
- دارای ویژگی های شتاب سخت افزاری است که می تواند امنیت و رمزگذاری داده های اینترنت اشیا مانند RSA، SHA، RNG و AES1 را افزایش دهد.

---
---
# چند نمونه کاربرد IoT در زندگی روزمره انسان ها 

Esp32 برای انجام پروژه های اینترنت اشیا (IoT)، سیستم های هوشمند، ردیابی و کنترل دستگاه ها و بازی های الکترونیکی استفاده می شود. همچنین این میکروکنترلر برای اتصال دستگاه ها به اینترنت، انتقال داده ها، کنترل دستگاه ها از راه دور و ایجاد ارتباط بین دستگاه ها استفاده می شود. به علاوه، Esp32 دارای ورودی و خروجی های متنوعی است که امکان اتصال به سنسورها، موتورها، نمایشگرها و دیگر قطعات الکترونیکی را فراهم می کند.

- سیستم هوشمند خانه: Esp32 می‌تواند به عنوان مرکز کنترلی برای یک سیستم هوشمند خانه مورد استفاده قرار گیرد. با اتصال Esp32 به دستگاه‌های خانه هوشمند مانند چراغ‌ها، ترموستات، درب‌ها و پنجره‌ها، می‌توانید این دستگاه‌ها را از راه دور کنترل کرده و داده‌های مربوط به استفاده آن‌ها را جمع‌آوری کنید.

- ردیابی و مکان‌یابی: با استفاده از Esp32 و یک ماژول GPS، می‌توانید یک سیستم ردیابی و مکان‌یابی برای اشیای مختلف ایجاد کنید. این کاربرد می‌تواند برای ردیابی و مکان‌یابی خودروها، وسایل نقلیه، حیوانات خانگی یا حتی افراد مورد استفاده قرار گیرد.

- کشاورزی هوشمند: Esp32 می‌تواند در سیستم‌های کشاورزی هوشمند مورد استفاده قرار گیرد، از جمله کنترل آبیاری، مانیتورینگ شرایط محیطی برای کشت و زراعت، و یا اتصال به سیستم‌های خودروی کشاورزی برای کنترل و مانیتورینگ.

---
---
# کنترل گل خانه با ESP32

1. اتصال سنسورها به ESP32:
 هر گلخانه می‌تواند یک یا چند برد ESP32 داشته باشد که به سنسورهای رطوبت و دما متصل می‌شوند. برای اندازه‌گیری رطوبت و دما، می‌توانید از سنسورهای مانند DHT11 یا DHT22 برای اندازه‌گیری دما و رطوبت استفاده کنید.
این سنسورها دارای یک پروتکل ارتباطی است که به نام نوعی از دیجیتال سریال با نام One-Wire یا Single-Bus معروف است. این پروتکل این امکان را فراهم می‌کند که اطلاعات از سنسور به میکروکنترلر (مانند ESP32) ارسال شود.
این سنسورها دارای چهار پایه هستند: یک پایه یکسان (Ground)، یک پایه تغذیه (VCC)، یک پایه داده (Data) و یک پایه خروجی (Output). برای اتصال سنسور به برد ESP32، شما باید پایه‌های Ground و VCC را به منبع تغذیه و زمین بردهای ESP32 متصل کنید و پایه داده را به یک پایه ورودی/خروجی دیجیتال برد ESP32 وصل کنید.

برای برنامه‌نویسی و تنظیم سنسور DHT11 یا DHT22 روی برد ESP32، شما می‌توانید از کتابخانه‌های آماده برای ESP32 استفاده کنید. برای مثال، شما می‌توانید از کتابخانه DHT sensor library استفاده کنید که برای این منظور مناسب است. این کتابخانه از خواندن داده‌های ارسالی از سنسور به ESP32 و تفسیر آن‌ها به عنوان دما و رطوبت کمک می‌گیرد.

---
---
2. اتصال ESP32 به شبکه اینترنت:
   - ESP32 باید به شبکه اینترنت متصل شود تا بتواند داده‌های اندازه‌گیری شده را به سرور ابری ارسال کند. برای این کار، ESP32 می‌تواند از Wi-Fi یا سایر اتصالات اینترنتی مانند Ethernet یا LoRa استفاده کند.

3. ارسال داده‌ها به سرور ابری:
   - ESP32 باید داده‌های اندازه‌گیری شده را به سرور ابری ارسال کند. برای این کار، ESP32 می‌تواند از پروتکل‌های ارتباطی مانند HTTP یا MQTT استفاده کند تا داده‌ها را به سرور ابری ارسال کند.
پس از خواندن داده‌های از سنسور، شما می‌توانید این داده‌ها را به شبکه اینترنتی ارسال کنید تا به سرور ابری یا دیگر دستگاه‌ها ارسال شود. برای این کار، شما می‌توانید از پروتکل‌های مختلف ارتباطی مانند HTTP و Restful Api برای ارتباط با سرور ابری استفاده کنید.


4. ذخیره و پردازش داده‌ها در سرور ابری:
   - سرور ابری باید داده‌های دریافتی را ذخیره کرده و از آن‌ها برای مانیتورینگ و کنترل گلخانه‌ها استفاده کند. برای این کار، می‌توانید از پایگاه داده‌های ابری مانند Firebase استفاده کنید. با استفاده از زبان ها برنامه نویسی مختلف و فریم ورک های منساب مانند PHP  و Asp.net  یک Gateaway  برای گرفتن اطلاعات قرار میدهیم و با استفاده از دیتابیس هایی مانند SQL  اطلاعات را ذخیره و پردازش میکنیم .

---
---
5. کنترل گلخانه‌ها:
   - بر اساس داده‌های دریافتی از گلخانه‌ها، سرور ابری می‌تواند تصمیم بگیرد که چه اقداماتی باید انجام شود. به عنوان مثال، در صورتی که رطوبت به حداقل یا حداکثر مجاز برسد، می‌تواند دستوراتی برای روشن یا خاموش کردن سیستم‌های آبیاری ارسال کند.

با این روش، می‌توانید چند گلخانه را از راه دور مانیتور کرده و کنترل کنید و از طریق سرور ابری داده‌های مربوط به هر گلخانه را مدیریت کنید.

---
layout: new-section
---
# ESP 32 Pins
![esp32](/ESP32-Pinout.webp)

---
---
# Power Pins
دو پایه پاور وجود دارد: پایه VIN و پایه 3V3. اگر منبع تغذیه 5 ولتی تنظیم شده دارید، می توان از پین VIN برای تغذیه مستقیم ESP32 و لوازم جانبی آن استفاده کرد. پایه 3V3 خروجی از تنظیم کننده ولتاژ روی برد است. می توانید تا 600 میلی آمپر از آن دریافت کنید. GND پین زمین است.

<img  src="/powerPins.webp"/>

---
---
# GPIO Pins
بردESP32  دارای 25 پین  (Genral purpose input/output)GPIOاست که با برنامه نویسی مناسب می توان عملکردهای مختلفی را به آنها اختصاص داد. پین‌های GPIO دیجیتال هستند، به این معنی که فقط سطوح بالا/پایین یا روشن/خاموش را پشتیبانی می‌کنند. آنها معمولا از ورودی یا خروجی آنالوگ با سطوح ولتاژ مجزا پشتیبانی نمی کنند.

<img  src="/ESP32-GPIO-Pins.webp"/>

---
---
در حالی که اکثر پین ها دارای هدف اختصاصی هستند، مانند ارسال سیگنال به یک قطعه خاص، عملکرد یک پین GPIO قابل تنظیم است و می تواند توسط نرم افزار کنترل شود.
رایج ترین عملکردهای پین های GPIO عبارتند از:

- قابلیت تنظیم در نرم افزار برای ورودی یا خروجی بودن
- فعال یا غیرفعال شدن
- تنظیم مقدار یک خروجی دیجیتال
- خواندن مقدار یک خروجی دیجیتال
- ایجاد وقفه در هنگام تغییر مقدار ورودی


---
---
# Enable Pin
پین EN پین فعال برای ESP32 است که به طور پیش فرض بالا کشیده شده است. هنگامی که بالا کشیده می شود، تراشه فعال می شود. وقتی LOW کشیده می شود، تراشه غیرفعال می شود.
پین EN نیز به یک سوئیچ دکمه ای متصل است که می تواند پین را پایین بکشد و باعث ریست شود.

<img  src="/ESP32-Enable-Pin.webp"/>

---
---
# Strapping Pins
از این پین ها برای قرار دادن ESP32  در حالت BOOT برای اجرای برنامه ذخیره شده در فلش مموری) یا حالت FLASH برای آپلود برنامه در حافظه فلش استفاده می شود. بسته به وضعیت این پین ها، ESP32  در حالت روشن وارد حالت BOOT  یا حالت FLASH  می شود. 

<img  src="/ESP32-Strapping-Pins.webp"/>


---
---
# Touch Pins
ESP32  دارای ۹ تاچ خازنی است. هنگامی که یک بار خازنی (مانند انگشت انسان) در مجاورت GPIO  باشد، ESP32  تغییر در ظرفیت بار خازن را تشخیص می دهد. می توانید با چسباندن هر جسم رسانا به این پین ها مانند فویل آلومینیومی، پارچه رسانا، رنگ رسانا و … یک پد لمسی بسازید. به دلیل طراحی کم نویز و حساسیت بالای مدارمی توان حتی پدهای نسبتاً کوچکی ساخت.

<img  src="/ESP32-Touch-Pins.webp"/>


---
---
# DAC Pins
ESP32 شامل دو کانال DAC 8 بیتی برای تبدیل سیگنال های دیجیتال به ولتاژ آنالوگ واقعی است. می توان از آن به عنوان "پتانسیومتر دیجیتال" برای کنترل دستگاه های آنالوگ استفاده کرد.

<img  src="/ESP32-DAC-Pins.webp"/>

---
---
# ADC Pins

واحد آنالوگ به دیجیتالESP32  یک ADC  با دقت 12 بیتی است، به این معنی که می تواند تا 4096 (2 ^ 12) سطح آنالوگ گسسته را تشخیص دهد. به عبارت دیگر، ولتاژ ورودی از 0 تا 3.3 ولت (ولتاژ عملیاتی) را به مقدار صحیح از 0 تا 4095 تبدیل می کند. این مسئله منجر به وضوح 0.0008 ولت (0.8 میلی ولت) در هر واحد می شود.

وقتی Wi-Fi فعال است نمی توان از پین های ADC2  استفاده کرد. اگر پروژه شما بهWi-Fi  نیاز دارد، به جای آن از پین های ADC1  استفاده کنید


<img  src="/ESP32-ADC-Pins.webp"/>

---
---
# حالت Sleep Mode
حالتDeep Sleep  یک حالت پایه است که به کمک آن می‌توانید مصرف انرژی را به حداقل برسانید. در این حالت، برد به یک حالت خواب عمیق وارد می‌شود که می‌تواند تا ۵۰ روز به طول بیانجامد. در این حالت، تمامی پردازش‌ها متوقف شده و تنها مقدار کمی از انرژی برای ادامه‌ی عملکرد سیستم حفظ می‌شود. این حالت برای کاربرد‌هایی که نیاز به مصرف انرژی کمتر دارند، مثل سیستم‌های IoT، بسیار مناسب است.

# پلتفرم‌های برنامه‌نویسی ESP32
- چندین پلتفرم توسعه برای برنامه نویسی ESP32 وجود دارد.

- این بورد را می‌توان با زبان Node js و Micro Python که همان زبان پایتون ولی برای میکروکنترلرهاست و در محیط برنامه نویسی آردوینو و… برنامه نویسی کرد.

- خوشبختانه در بروزرسانی ها، افزونه ای برای برد ESP32  به محیط آردوینو IDE  افزوده شده است. پیشنهاد میشود برای پروژه های خود از زبان برنامه نویسی آردوینو استفاده کنید تا در ساده ترین حالت ممکن بتوانید پروژه های پیچیده را اجرا کنید.

---
layout: new-section
---
# Handling ESP32 GPIO Interrupts
![esp32](/ESP32-Tutorial-For-GPIO-Interrupt-Handling.webp)

---
---
# Interrupts In ESP32
ESP32 حداکثر 32 اسلات وقفه برای هر هسته فراهم می کند. هر وقفه دارای سطح اولویت خاصی است و می توان آن را به دو نوع طبقه بندی کرد.

- وقفه های سخت افزاری - این وقفه ها در پاسخ به یک رویداد خارجی رخ می دهند. به عنوان مثال، یک وقفه GPIO (زمانی که یک کلید فشار داده می شود) یا یک وقفه لمسی (زمانی که لمس تشخیص داده می شود).

- وقفه نرم افزار - این وقفه ها در پاسخ به یک دستورالعمل نرم افزار رخ می دهد. به عنوان مثال، یک وقفه ساده تایمر یا یک وقفه تایمر نگهبان (زمانی که تایمر تمام می شود).

---
---
# ESP32 GPIO وقفه
در ESP32 می‌توانیم یک تابع روتین سرویس وقفه تعریف کنیم که زمانی فراخوانی می‌شود که پین GPIO سطح منطقی خود را تغییر دهد.

تمام پین های GPIO در یک برد ESP32 را می توان طوری پیکربندی کرد که به عنوان ورودی درخواست وقفه عمل کند.

---
layout: text-window
---
# اتصال یک وقفه پین
در Arduino IDE، از تابعی به نام attachInterrupt() برای تنظیم وقفه بر اساس پین به پین استفاده می کنیم.

این تابع سه آرگومان را می پذیرد:

GPIOPin - پایه GPIO را به عنوان پایه وقفه تنظیم می کند که به ESP32 می گوید کدام پایه را نظارت کند.

ISR - نام تابعی است که با هر بار وقوع وقفه فراخوانی می شود.

حالت - تعیین می کند که چه زمانی وقفه باید راه اندازی شود. پنج ثابت به عنوان مقادیر معتبر از پیش تعریف شده اند


::window::

<div style="direction:ltr">
```ino
  attachInterrupt(GPIOPin, ISR, Mode);
```
</div>

---
layout: text-image
media: '/Wiring-Push-Buttons-to-ESP32-For-GPIO-Interrupt.webp'
---
# Hardware Hookup

بیایید یک دکمه فشاری را به GPIO#18 (D18) در ESP32 وصل کنیم. برای این پین نیازی به کشش ندارید زیرا ما پین را به صورت داخلی به سمت بالا می کشیم.

<div style="direction:ltr">

```ino {1-5|7|9-12|14-18|20-24}
 struct Button {
	const uint8_t PIN;
	uint32_t numberKeyPresses;
	bool pressed;
};

Button button1 = {18, 0, false};

void IRAM_ATTR isr() {
	button1.numberKeyPresses++;
	button1.pressed = true;
}

void setup() {
	Serial.begin(115200);
	pinMode(button1.PIN, INPUT_PULLUP);
	attachInterrupt(button1.PIN, isr, FALLING);
}

void loop() {
	if (button1.pressed) {
		Serial.printf("Button has been pressed %u times\n", button1.numberKeyPresses);
		button1.pressed = false;
	}
}
```
</div>

---
---
# Addressable LEDs with ESP32 and WLED
چه آنها را LED های RGB آدرس پذیر جداگانه، WS2812B یا NeoPixels بنامید، نمی توان انکار کرد که آنها بسیار محبوب هستند و برای هر پروژه درخشان و چشمک زن ضروری هستند.

نوشتن کد برای کنترل LED های آدرس پذیر دشوار نیست، اما اگر فقط بخواهید کمی نور محیط را به اتاق نشیمن یا دفتر خود اضافه کنید و همه آن را از طریق تلفن هوشمند خود مدیریت کنید، چه؟ در حال حاضر بهترین گزینه، دست پایین، WLED است—یک برنامه تلفن همراه رایگان، غنی از امکانات و منبع باز که به ما فرمان کامل را بر طیف گسترده ای از LED های RGB می دهد.

برنامه WLED کنترل LED های آدرس پذیر جداگانه را بسیار ساده تر، راحت تر و مهمتر از همه سرگرم کننده می کند. این برنامه خیلی جالب است که آن را امتحان نکنید.

در این آموزش نحوه نصب WLED بر روی برد ESP32 و استفاده از آن برای کنترل رشته ای از LED های آدرس پذیر را خواهیم آموخت.


---
layout: text-image
media: '/Connecting-WS2812B-Addressable-LED-Strip-to-ESP32-USB-Powered.webp'
---
# Connecting Addressable LED Strip to ESP32
سیم کشی نسبتا ساده است. فقط سه سیم برای اتصال وجود دارد: دو سیم برای برق و یکی برای انتقال داده.

سیم قرمز (+5V/VCC) نوار LED آدرس پذیر را به پین VIN ESP32 و سیم سفید/زرد (GND) را به پایه GND ESP32 وصل کنید.

در نهایت، سیم سبز (DIN) نوار LED را از طریق یک مقاومت 330 اهم به GPIO16 (RX2) ESP32 وصل کنید. این مقاومت درون خطی برای محافظت از پین داده وجود دارد. یک مقاومت بین 220 تا 470 اهم باید عملکرد خوبی داشته باشد. سعی کنید مقاومت را تا حد امکان نزدیک به LED های آدرس پذیر خود قرار دهید.


---
layout: text-image
media: '/Connecting-WS2812B-Addressable-LED-Strip-to-ESP32-5V-External-Power.webp'
---
# Connecting Addressable LED Strip to ESP32
اگر پروژه بزرگتری دارید که به LED های بیشتری نیاز دارد، برق USB کافی نخواهد بود. در عوض باید برق را از یک منبع خارجی به نوار تزریق کنید. به خاطر داشته باشید که هر LED RGB حدود 60 میلی آمپر (20 میلی آمپر در هر کانال رنگی) مصرف می کند، زمانی که روشنایی روی کامل تنظیم شود. این بدان معناست که برای هر 30 LED، نوار LED شما می تواند تا 1.8 آمپر را بکشد.

پس از اتمام سیم کشی، LED ها باید زنده شوند و نور زرد ملایمی از خود ساطع کنند. اگر اینطور نیست، قبل از ادامه، سیم کشی خود را دوباره بررسی کنید.

---
layout: nog
dir: ltr
---
# g                               Now the code
```c {all|1|2-3|4|5-7|8,17|9|10,14|11-14|15-16}
#include <Adafruit_NeoPixel.h>
#define PIN_WS2812B 16  // The ESP32 pin GPIO16 connected to WS2812B
#define NUM_PIXELS 30   // The number of LEDs (pixels) on WS2812B LED strip
Adafruit_NeoPixel ws2812b(NUM_PIXELS, PIN_WS2812B, NEO_GRB + NEO_KHZ800);
void setup() {
  ws2812b.begin();  // initialize WS2812B strip object (REQUIRED)
}
void changeColor() {
  ws2812b.clear();  // set all pixel colors to 'off'. It only takes effect if pixels.show() is called
  for (int pixel = 0; pixel < NUM_PIXELS; pixel++) {         // for each pixel
    ws2812b.setPixelColor(pixel, ws2812b.Color(0, 255, 0));  // it only takes effect if pixels.show() is called
    ws2812b.show();                                          // update to the WS2812B Led Strip
    delay(500);  // 500ms pause between each pixel
  }
  ws2812b.clear(); 
  ws2812b.show();
}
```


---
---
# اتصال به ESP32
یکی از مفیدترین ویژگی های ESP32 این است که نه تنها به یک شبکه وای فای موجود متصل می شود و به عنوان یک وب سرور عمل می کند، بلکه همچنین می تواند شبکه خود را ایجاد کند و به دستگاه های دیگر اجازه می دهد مستقیماً به آن متصل شوند و به صفحات وب دسترسی پیدا کنند. این امکان پذیر است زیرا ESP32 می تواند در سه حالت کار کند: حالت Station (STA)، حالت Soft Access Point (AP) و هر دو به طور همزمان.

---
layout: text-image
media: '/ESP32-Web-Server-Station-STA-Mode-Demonstration.webp'
---
# حالت Station (STA)
در حالت Station (STA)، ESP32 به یک شبکه WiFi موجود (شبکه ای که توسط روتر بی سیم شما ایجاد شده است) متصل می شود.
در حالت STA، ESP32 یک آدرس IP از روتر بی سیمی که به آن متصل است، دریافت می کند. با این آدرس IP، می‌تواند یک وب سرور راه‌اندازی کند و صفحات وب را به همه دستگاه‌های متصل در شبکه WiFi موجود ارائه کند.

---
layout: text-image
media: '/ESP32-Web-Server-Soft-Access-Point-AP-Mode-Demonstration.webp'
---
# حالت Soft Access Point
در حالت اکسس پوینت (AP)، ESP32 شبکه WiFi خود را راه اندازی می کند و مانند یک روتر وای فای به عنوان یک هاب عمل می کند. با این حال، برخلاف روتر وای فای، رابطی با شبکه سیمی ندارد. بنابراین، این حالت عملکرد، نقطه دسترسی نرم (Soft-AP) نامیده می شود. همچنین بیش از پنج ایستگاه نمی توانند به طور همزمان به آن متصل شوند.

---
---
# چرا Web Server 
بنابراین ممکن است از خود بپرسید: "چگونه می توانم چیزها را از وب سروری که فقط صفحات وب را پردازش و ارائه می کند کنترل کنم؟".

فوق العاده ساده است ما با بازدید از یک URL خاص، چیزها را کنترل می کنیم.

هنگامی که یک URL را در یک مرورگر وب وارد می‌کنید، یک درخواست HTTP (که به عنوان درخواست GET نیز شناخته می‌شود) به سرور وب ارسال می‌کند. مسئولیت رسیدگی به این درخواست بر عهده وب سرور است.

فرض کنید یک URL مانند http://192.168.1.1/ledon را در مرورگر وارد کرده اید. سپس مرورگر یک درخواست HTTP را به ESP32 ارسال می کند. هنگامی که ESP32 این درخواست را دریافت می کند، تشخیص می دهد که کاربر می خواهد LED را روشن کند. در نتیجه، LED را روشن می کند و یک صفحه وب پویا را به مرورگری می فرستد که وضعیت LED را به صورت "روشن" نشان می دهد. خیلی ساده است، مگه نه؟

---
layout: nog
dir: ltr
---
# g                         Now Lets connected to WI-FI
```c{all|1-2|3-5|6|7,23|8-10|11-14|15-17|18-21|22}
#include <WiFi.h>
#include <WebServer.h>
const char* ssid = " YourNetworkName";  // Enter SSID here
const char* password = " YourPassword";  //Enter Password here
WebServer server(80);
bool LED1status = LOW;
void setup() {
  Serial.begin(115200);
  delay(100);
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.print(".");
  }
  Serial.println("");
  Serial.println("WiFi connected..!");
  Serial.print("Got IP: ");  Serial.println(WiFi.localIP());
  server.on("/", handle_OnConnect);
  server.on("/ledon", handle_led1on);
  server.on("/ledoff", handle_led1off);
  server.begin();
  Serial.println("HTTP server started");
}

```

---
layout: nog
dir: ltr
---
# g                           handel the request

```c {all|1-5|6-9|10-13|14-18}
void handle_OnConnect() {
  LED1status = LOW;
  Serial.println("GPIO4 Status: OFF | GPIO5 Status: OFF");
  server.send(200, "text/html", SendHTML(LED1status)); 
}
void handle_led1on() {
  LED1status = HIGH;
  server.send(200, "text/html", SendHTML(true)); 
}
void handle_led1off() {
  LED1status = LOW;
  server.send(200, "text/html", SendHTML(false)); 
}
void loop() {
  server.handleClient();
  if(LED1status) changeColor() ;
}

```
 
---
layout: nog
dir: ltr
---

``` c
String SendHTML(uint8_t led1stat){
  String ptr = "<!DOCTYPE html> <html>\n";
  ptr +="<head><meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0, user-scalable=no\">\n";
  ptr +="<title>LED Control</title>\n";
  ptr +="<style>html { font-family: Helvetica; display: inline-block; margin: 0px auto; text-align: center;}\n";
  ptr +="body{margin-top: 50px;} h1 {color: #444444;margin: 50px auto 30px;} h3 {color: #444444;margin-bottom: 50px;}\n";
  ptr +=".button {display: block;width: 80px;background-color: #3498db;border: none;color: white;padding: 13px 30px;text-decoration: none;font-size: 25px;margin: 0px auto 35px;cursor: pointer;border-radius: 4px;}\n";
  ptr +=".button-on {background-color: #3498db;}\n";
  ptr +=".button-on:active {background-color: #2980b9;}\n";
  ptr +=".button-off {background-color: #34495e;}\n";
  ptr +=".button-off:active {background-color: #2c3e50;}\n";
  ptr +="p {font-size: 14px;color: #888;margin-bottom: 10px;}\n";
  ptr +="</style>\n";
  ptr +="</head>\n";
  ptr +="<body>\n";
  ptr +="<h1>ESP32 Web Server</h1>\n";
    ptr +="<h3>Using Station(STA) Mode</h3>\n";
  
   if(led1stat)
  {ptr +="<p>LED1 Status: ON</p><a class=\"button button-off\" href=\"/led1off\">OFF</a>\n";}
  else
  {ptr +="<p>LED1 Status: OFF</p><a class=\"button button-on\" href=\"/led1on\">ON</a>\n";}
  ptr +="</body>\n";
  ptr +="</html>\n";
  return ptr;
}
```

---
layout: two-cols
---
# اگر همه چیز درست پیش رود!!
![esp32](/ESP32-Web-Server-Station-Mode-Serial-Monitor-Output-Webpage-Accessed.webp)

::right::
# 
![esp32](/ESP32-Web-Server-Station-Mode-Web-Page.jpg)

---
layout: new-section
---
# WLED راه ساده تر
![esp32](/wled_logo_akemi.png)

A fast and feature-rich implementation of an ESP8266/ESP32 webserver to control NeoPixel (WS2812B, WS2811, SK6812) LEDs or also SPI based chipsets like the WS2801 and APA102!

[Look here for more info](https://kno.wled.ge/basics/getting-started/)

---
layout: center
---
<div style="height: 10vh" class="flex flex-col justify-center items-center">
<span class="text-7xl font-bold bg-gradient-to-r from-orange-700 via-blue-500 to-green-400 text-transparent bg-clip-text bg-300% animate-gradient p-0 m-0 h-42">
 Thank You
</span>

<p style="height: 10vh" class="text-2xl font-bold bg-gradient-to-r from-orange-700 via-blue-500 to-green-400 text-transparent bg-clip-text bg-300% animate-gradient p-0 m-0">
 Hope you have good day
</p>
</div>



<style>
.animate-gradient {
  background-size: 300%;
  -webkit-animation: animatedgradient 6s ease infinite alternate;
  -moz-animation: animatedgradient 6s ease infinite alternate;
  animation: animatedgradient 6s ease infinite alternate;
}

@keyframes animatedgradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>