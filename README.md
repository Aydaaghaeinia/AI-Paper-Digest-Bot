# AI Paper Digest Bot (arXiv + GPT-4o)

یکی از دغدغه‌های اصلی من این بود که بتونم به ساده‌ترین و جذاب‌ترین شکل، جدیدترین مقالات حوزه هوش مصنوعی (به‌ویژه arXiv) رو دنبال کنم.

برای همین یک ابزار طراحی کردم که:  
- هر روز مقالات جدید arXiv رو می‌گیره.  
- اون‌ها رو با کمک GPT-4o خلاصه می‌کنه.  
- با لحن دلخواه شما (مثلاً لحن بامزه یا رسمی) ارائه می‌ده.  
- می‌تونه از طریق ربات تلگرام باهاتون صحبت کنه.

---

## توضیح کتابخانه‌ها

- `python-telegram-bot`: برای تعامل با API تلگرام و ساخت ربات.  
- `openai`: برای استفاده از API شرکت OpenAI در اینجا برای مدل GPT-4o جهت خلاصه‌سازی  
- `feedparser`: برای خواندن و تجزیه فیدهای RSS در اینجا برای دریافت مقالات از arXiv  
- `nest_asyncio`: برای حل مشکل event loop در محیط‌هایی مانند Jupyter Notebook یا Google Colab که asyncio ممکن است با مشکل مواجه شود.

---

## کلیدهای API

### OpenAI API Key  
- باید در سایت [platform.openai.com](https://platform.openai.com) یک حساب بسازی.  
- سپس یک API Key بساز.  
- در این پروژه، این کلید از `userdata.get('chatgp')` خونده می‌شه (ویژه Google Colab). اگر در محیط دیگری هستید، پیشنهاد می‌شه از متغیر محیطی یا فایل `.env` استفاده کنید.

### Telegram Bot Token  
- وارد تلگرام شو و با [@BotFather](https://t.me/BotFather) صحبت کن.  
- یک ربات بساز و توکنش رو دریافت کن.  
- این توکن هم از `userdata.get('TELEGRAM_TOKEN')` خونده می‌شه و مشابه OpenAI Key باید مدیریت بشه.  
- توکن ها در قسمت رمزهای گوگل کلب باید ذخیره باشند.

---

## نحوه اجرا

ابزار فعلاً به‌صورت محلی (لوکال) اجرا می‌شه و برای استفاده عمومی باید روی سرور یا تلگرام Deploy بشه.

---

## توسعه‌پذیری

دست شما برای توسعه این ابزار بازه!  
می‌تونی:  
- از هر مدل دیگه LLM مثل Mistral یا Claude به‌جای GPT استفاده کنی.  
- خروجی رو به‌جای تلگرام در ایمیل، وب‌اپ، اپلیکیشن یا هر پلتفرم دیگه‌ای نمایش بدی.  
- ظاهر کاراکتر و لحن‌ها رو شخصی‌سازی کنی.  
- بیشتر از یک مقاله رو پوشش بدی.  
- خروجی صدا بگیری.  
- دارای تایم باشه که هرساعتی خواستی پیام خلاصه مقاله رو بگیری.

---

## پیش‌نیازها

برای نصب کتابخانه‌های مورد نیاز، این دستور رو اجرا کن:

```bash
pip install python-telegram-bot openai feedparser nest_asyncio
