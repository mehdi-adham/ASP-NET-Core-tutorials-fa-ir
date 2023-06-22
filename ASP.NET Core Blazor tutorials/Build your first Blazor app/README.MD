# اولین برنامه Blazor خود را بسازید


**Visual Studio 2022 را دانلود و نصب کنید**

![installer](installer.png)

**آیا از قبل Visual Studio 2022 دارید؟**

اگر از قبل Visual Studio 2022 دارید، می توانید ASP.NET و web_development را اضافه کنید:

- کلید Windows را انتخاب کنید، Visual Studio Installer را تایپ کنید و Enter را فشار دهید.
- اگر از شما خواسته شد، به نصب کننده اجازه دهید خودش را به روز کند.
- اگر بروزرسانی برای ویژوال استودیو 2022 در دسترس باشد، دکمه Update نشان داده می شود. قبل از اصلاح نصب، آن را برای به روز رسانی انتخاب کنید.
- نصب Visual Studio 2022 خود را پیدا کنید و دکمه Modify را انتخاب کنید.
- اگر قبلاً انتخاب نشده‌اید، ASP.NET و web_development را انتخاب کرده و دکمه Modify را انتخاب کنید. در غیر این صورت، فقط پنجره را ببندید.


1. ویژوال استودیو را راه اندازی کنید و Create a new project را انتخاب کنید.

![create-project](create-project.png)

2. در پنجره Create a new project کلمه Blazor را در کادر جستجو تایپ کرده و Enter را بزنید.
3. قالب Blazor Server App را انتخاب کرده و Next را انتخاب کنید.

![pick-blazor](pick-blazor.png)

4. در پنجره Configure your new project، نام BlazorApp را به عنوان نام پروژه وارد کرده و Next را انتخاب کنید.
5. در پنجره اطلاعات اضافی، .NET 7.0 (Standard Term Support) را درمنو کشویی Framework در صورتی که قبلاً انتخاب نکرده اید انتخاب کنید و روی دکمه Create کلیک کنید.


![vs-additional-info](vs-additional-info.png)

پروژه شما در ویژوال استودیو ایجاد و بارگذاری می شود. با استفاده از Solution Explorer به محتویات پروژه خود نگاهی بیندازید.


![solution-explorer-after-project-create](solution-explorer-after-project-create.png)

چندین فایل ایجاد شد تا یک برنامه ساده Blazor را به شما ارائه دهد که آماده اجرا است.

- فایل Program.cs نقطه ورود برنامه‌ای است که سرور را راه‌اندازی می‌کند و در آن سرویس‌های برنامه و میان‌افزار را پیکربندی می‌کنید.
- فایل App.razor جزء اصلی برنامه است.
- دایرکتوری pages شامل چند صفحه وب نمونه برای برنامه است.
- فایل BlazorApp.csproj پروژه برنامه و وابستگی های آن را تعریف می کند و با دوبار کلیک کردن بر روی گره پروژه BlazorApp در Solution Explorer قابل مشاهده است.
- فایل launchSettings.json در دایرکتوری Properties تنظیمات پروفایل متفاوتی را برای محیط توسعه محلی تعریف می کند. یک شماره پورت به طور خودکار هنگام ایجاد پروژه اختصاص داده می شود و در این فایل ذخیره می شود.

