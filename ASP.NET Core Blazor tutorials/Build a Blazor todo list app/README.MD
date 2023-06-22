# ساخت یک برنامه Blazor todo list 

این آموزش یک تجربه کاری اساسی برای ساخت و اصلاح برنامه Blazor ارائه می دهد.

یاد بگیرید چگونه:

- یک پروژه برنامه Blazor لیست کار ایجاد کنید
- کامپوننت Razor را تغییر دهید
- از مدیریت رویداد و اتصال داده در کامپوننت ها استفاده کنید
- از مسیریابی در برنامه Blazor استفاده کنید


در پایان این آموزش، شما یک برنامه لیست کارها (todo list) خواهید داشت.

## یک برنامه Blazor ایجاد کنید

یک برنامه Blazor جدید به نام TodoList در یک command shell ایجاد کنید:

```text

dotnet new blazorserver -o TodoList
```

دستور قبلی یک پوشه به نام `TodoList` با گزینه `-o|--output` برای نگه داشتن برنامه ایجاد می کند. پوشه `TodoList` پوشه اصلی پروژه است. دایرکتوری ها را با دستور زیر به پوشه `TodoList` تغییر دهید:

```text

cd TodoList
```

## یک برنامه لیست کارهای Blazor بسازید

1. یک کامپوننت جدید Todo Razor را با استفاده از دستور زیر به برنامه اضافه کنید:

```text 

dotnet new razorcomponent -n Todo -o Pages
```

گزینه `-n|--name` در دستور قبلی نام کامپوننت جدید `Razor` را مشخص می کند. کامپوننت جدید در پوشه `Pages` پروژه با گزینه `-o|--output` ایجاد می شود.


**مهم**

نام فایل کامپوننت Razor به یک حرف اول بزرگ نیاز دارد. پوشه Pages را باز کنید و تأیید کنید که نام فایل کامپوننت Todo با حرف بزرگ T شروع می شود. نام فایل باید Todo.razor باشد.

2. کامپوننت `Todo` را در هر ویرایشگر فایلی باز کنید و یک دستور `@page Razor` با URL وابسته `/todo` به بالای فایل اضافه کنید.

`Pages/Todo.razor:`

```C#

@page "/todo"

<PageTitle>Todo</PageTitle>

<h1>Todo</h1>

@code {

}
```

فایل `Pages/Todo.razor` را ذخیره کنید.
