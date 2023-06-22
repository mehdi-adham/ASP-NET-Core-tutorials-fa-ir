# بررسی اجمالی ASP.NET Core

ASP.NET Core یک فریموورک چند پلتفرمی، با کارایی بالا و اپن سورس برای ساخت برنامه های مدرن، ابری و متصل به اینترنت است.


## با ASP.NET Core می توان:

- ساخت وب سرویس‌ها و برنامه‌ های  وب، برنامه‌های اینترنت اشیا (IoT) و بک اند تلفن همراه.
- استفاده از ابزارهای توسعه مورد علاقه خود در Windows، macOS و Linux
- گسترش در فضای ابری یا در محل
- اجرا  روی NET Core


## دلیل انتخاب ASP.NET Core

میلیون‌ها توسعه‌دهنده از ASP.NET 4.x برای ایجاد برنامه‌های وب استفاده می‌کنند یا از آن استفاده کرده‌اند. ASP.NET Core یک طراحی مجدد از ASP.NET 4.x است که شامل تغییرات معماری می شود که منجر به یک فریوورک ماژولارتر می شود.


##  مزایای ASP.NET Core:

- یک unified story برای ساخت رابط کاربری وب و APIهای وب.
- برای آزمایش پذیری طراحی شده است.
- Razor Pages کدنویسی سناریوهای متمرکز بر صفحه را آسان‌تر و سازنده‌تر می‌کند.
- Blazor به شما امکان می دهد از C# در مرورگر در کنار جاوا اسکریپت استفاده کنید. منطق برنامه سمت سرور و سمت کلاینت را به اشتراک بگذارید که همه با دات نت نوشته شده اند.
- قابلیت توسعه و اجرا بر روی ویندوز، macOS و لینوکس.
- اپن سورس و جامعه محور.
- یکپارچه سازی فریموورک های مدرن، سمت کلاینت و گردش کار توسعه.
- پشتیبانی از خدمات هاست Remote_Procedure_Call (RPC) با استفاده از gRPC.
- یک سیستم پیکربندی مبتنی بر محیط cloud ready.
- تزریق وابستگی داخلی
- یک درخواست HTTP سبک، با کارایی بالا وماژولار pipeline.
- قابلیت هاست در موارد زیر:
<ul dir="rtl">
<li>Kestrel</li>
<li>IIS</li>
<li>HTTP.sys</li>
<li>Nginx</li>
<li>Apache</li>
<li>Docker</li>
</ul>

- نسخه ساید بای ساید.
- ابزاری که توسعه وب مدرن را ساده می کند.


## ساخت API های وب و رابط های کاربر وب با استفاده از ASP.NET Core MVC

- الگوی Model-View-Controller (MVC) کمک می کند تا API های وب و برنامه های وب شما قابل آزمایش باشند.
- Razor Pages یک مدل برنامه نویسی مبتنی بر صفحه است که ساخت رابط کاربری وب را آسان تر و کارآمدتر می کند.
- Razor markup یک syntax مولد برای Razor Pages و ویوهای MVC فراهم می کند.
- Tag Helpers کد سمت سرور را برای مشارکت در ایجاد و رندرعناصر HTML در فایل‌های Razor فعال می‌کند.
- پشتیبانی داخلی از data formats و content negotiation متعدد به API های وب شما امکان دسترسی به طیف وسیعی از کلاینت ها، از جمله مرورگرها و دستگاه های تلفن همراه را می دهد.
- Model binding به طور خودکار داده ها را از درخواست های HTTP به پارامترهای متد اکشن نگاشت می کند.
- اعتبار سنجی مدل به طور خودکار اعتبار سنجی سمت مشتری و سمت سرور را انجام می دهد.


## توسعه سمت کلاینت

<p dir="rtl">ASP.NET Core به طور یکپارچه با چارچوب ها و کتابخانه های محبوب سمت کلاینت، از جمله Blazor، Angular، React و Bootstrap ادغام می شود. برای اطلاعات بیشتر، به <a href="https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-7.0" rel="nofollow">ASP.NET Core Blazor</a> و موضوعات مرتبط زیر <em>توسعه سمت کلاینت</em> مراجعه کنید.</p>



## چارچوب های هدف اصلی ASP.NET

<p dir="rtl">ASP.NET Core 3.x یا جدیدتر فقط می تواند .NET Core را هدف قرار دهد. به طور کلی، هسته ASP.NET از کتابخانه های استاندارد دات نت تشکیل شده است. کتابخانه های نوشته شده با دات نت استاندارد 2.0 روی هر پلتفرم دات نت که دات نت استاندارد 2.0 را پیاده سازی می کند اجرا می شود.</p>


چندین مزیت برای هدف قرار دادن .NET Core وجود دارد و این مزایا با هر انتشار افزایش می یابد. برخی از مزایای NET Core نسبت به .NET Framework عبارتند از:

- کراس پلت فرم. قابل اجرا بر روی ویندوز، macOS و لینوکس.
- عملکرد بهبود یافته است
-  نسخه ساید بای ساید
- API های جدید
- متن باز



## مسیر یادگیری توصیه شده

مایکروسافت آموزش های زیر را برای آشنایی با توسعه برنامه های ASP.NET Core توصیه می کند:

1. آموزش برای نوع برنامه ای که می خواهید توسعه دهید یا نگهداری کنید.

| نوع برنامه | سناریو | آموزش |
| --- | --- | --- |
| برنامه وب | توسعه UI وب سمت سرور جدید | [با Razor Pages شروع کنید](https://learn.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/razor-pages-start?view=aspnetcore-7.0) |
| برنامه وب | نگهداری از برنامه MVC | [با MVC شروع کنید](https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-7.0) |
| برنامه وب | توسعه رابط کاربری وب سمت کلاینت| [با Blazor شروع کنید](https://dotnet.microsoft.com/learn/aspnet/blazor-tutorial/intro) |
| Web API | سرویس HTTP RESTful | [Create a web API†](https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-7.0) |
| برنامه تماس از راه دور | یرویس های قرارداد اول با استفاده از بافرهای پروتکل | [با یک سرویس gRPC شروع کنید](https://learn.microsoft.com/en-us/aspnet/core/tutorials/grpc/grpc-start?view=aspnetcore-7.0) |
| برنامه بلادرنگ | ارتباط دو طرفه بین سرورها و کلاینت ها متصل | [با SignalR شروع کنید ](https://learn.microsoft.com/en-us/aspnet/core/tutorials/signalr?view=aspnetcore-7.0)|


2. آموزشی که نحوه دسترسی به داده های اولیه را نشان می دهد.

| سناریو | آموزش |
| --- | --- |
| توسعه جدید | [Razor Pages with Entity Framework Core](https://learn.microsoft.com/en-us/aspnet/core/data/ef-rp/intro?view=aspnetcore-7.0) |
| نگهداری از برنامه MVC | [MVC با Entity Framework Core](https://learn.microsoft.com/en-us/aspnet/core/data/ef-mvc/intro?view=aspnetcore-7.0) |

<ol start="3" dir="rtl">
<li>
<p dir="auto">یک نمای کلی از ASP.NET Core <a href="https://learn.microsoft.com/en-us/aspnet/core/fundamentals/?view=aspnetcore-7.0" rel="nofollow">مبانی</a> را بخوانید که برای همه انواع برنامه ها اعمال می شود.</p>
</li>
<li>
<p dir="auto">فهرست مطالب را برای سایر موضوعات مورد علاقه مرور کنید.</p>
</li>
</ol>

† همچنین [آموزش تعاملی وب API](https://learn.microsoft.com/en-us/training/modules/build-web-api-net-core) وجود دارد. نصب محلی ابزارهای توسعه مورد نیاز نیست. کد در یک Azure Cloud Shell در مرورگر شما اجرا می شود و از curl برای آزمایش استفاده می شود.




## مهاجرت از دات نت فریم ورک

برای یک راهنمای مرجع برای انتقال برنامه‌های ASP.NET 4.x به ASP.NET Core، به‌روزرسانی از [ASP.NET به ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/migration/proper-to-2x/?view=aspnetcore-7.0) را ببینید.