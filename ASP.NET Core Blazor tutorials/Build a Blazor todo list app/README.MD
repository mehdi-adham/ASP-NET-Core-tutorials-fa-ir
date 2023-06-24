# ساخت یک برنامه Blazor todo list 

این آموزش یک تجربه کاری اساسی برای ساخت و تغییر برنامه Blazor ارائه می دهد.

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


1. کامپوننت `Todo` را به navigation اضافه کنید.

کامپوننت `NavMenu` در لایوت برنامه استفاده می‌شود. لایوت ها کامپوننت هایی هستند که به شما امکان می دهند از تکرار محتوا در یک برنامه جلوگیری کنید. هنگامی که URL کامپوننت توسط برنامه بارگیری می شود، کامپوننت `NavLink` یک نشانه در رابط کاربری برنامه ارائه می دهد.

در محتوای عنصر navigation (`<nav class="flex-column">`) کامپوننت NavMenu، عنصر `<div>` زیر را برای کامپوننت Todo اضافه کنید.

```C#

<div class="nav-item px-3">
    <NavLink class="nav-link" href="todo">
        <span class="oi oi-list-rich" aria-hidden="true"></span> Todo
    </NavLink>
</div>
```


فایل `Shared/NavMenu.razor` را ذخیره کنید.



1. برنامه را با اجرای دستور dotnet watch run در command shell از پوشه TodoList بیلد و اجرا کنید. پس از اجرای برنامه، با انتخاب لینک Todo در navigation برنامه، که صفحه را در `/todo` بارگیری می کند، از صفحه جدید **`Todo`** دیدن کنید.

برنامه را رها کنید command shell را اجرا کند. هر بار که یک فایل ذخیره می شود، برنامه به طور خودکار  rebuilt می شود و صفحه در مرورگر به طور خودکار بارگیری می شود.


2. یک فایل `TodoItem.cs` را به ریشه پروژه (پوشه TodoList) اضافه کنید تا کلاسی را نگه دارید که نشان دهنده یک آیتم `todo` است. از کد سی شارپ زیر برای کلاس `TodoItem` استفاده کنید.

```C#

public class TodoItem
{
    public string? Title { get; set; }
    public bool IsDone { get; set; }
}
```

**توجه داشته باشید**

اگر از ویژوال استودیو برای ایجاد فایل TodoItem.cs و کلاس TodoItem استفاده می کنید، از یکی از روش های زیر استفاده کنید:

فضای نامی که ویژوال استودیو برای کلاس ایجاد می کند را حذف کنید.
از دکمه **Copy** در بلوک کد قبلی استفاده کنید و کل محتوای فایلی را که ویژوال استودیو تولید می کند جایگزین کنید.


1. به کامپوننت Todo برگردید و کارهای زیر را انجام دهید:

یک فیلد برای موارد انجام کار در بلوک `@code` اضافه کنید. کامپوننت Todo از این فیلد برای حفظ وضعیت لیست کارها استفاده می کند.
یک لیست نامرتب و یک حلقه foreach را اضافه کنید تا هر مورد todo را به عنوان یک آیتم فهرست رندرکند (`<li>`).

Pages/Todo.razor:

```C#

@page "/todo"

<PageTitle>Todo</PageTitle>

<h1>Todo</h1>

<ul>
    @foreach (var todo in todos)
    {
        <li>@todo.Title</li>
    }
</ul>

@code {
    private List<TodoItem> todos = new();
}
```

1. برنامه برای افزودن todo آیتم ها به لیست به عناصر UI نیاز دارد. یک ورودی متن (`<input>`) و یک دکمه (`<button>`) در زیر لیست نامرتب (`<ul>...</ul>`) اضافه کنید


```C#

@page "/todo"

<PageTitle>Todo</PageTitle>

<h1>Todo</h1>

<ul>
    @foreach (var todo in todos)
    {
        <li>@todo.Title</li>
    }
</ul>

<input placeholder="Something todo" />
<button>Add todo</button>

@code {
    private List<TodoItem> todos = new();
}
```

1. فایل `TodoItem.cs` و فایل `Pages/Todo.razor` به روز شده را ذخیره کنید. در command shell، برنامه به طور خودکار rebuilt  می شود، زمانی که فایل ها ذخیره می شوند. مرورگر صفحه را دوباره لود می کند.


2. وقتی دکمه `Add todo` انتخاب می‌شود، هیچ اتفاقی نمی‌افتد، زیرا Event handler به دکمه متصل نیست.

3. یک متد `AddTodo` را به کامپوننت `Todo` اضافه کنید و با استفاده از ویژگی `@onclick`، متد را برای دکمه ثبت کنید. متد `AddTodo` زمانی فراخوانی می شود که دکمه کلیک شود:


```C#

<input placeholder="Something todo" />
<button @onclick="AddTodo">Add todo</button>

@code {
    private List<TodoItem> todos = new();

    private void AddTodo()
    {
        // Todo: Add the todo
    }
}
```

1. برای دریافت عنوان مورد جدید todo، یک فیلد رشته `newTodo` در بالای بلوک `@code` اضافه کنید:

```C#

private string? newTodo;
```

عنصر متن `<input>` را تغییر دهید برایر بایند `newTodo`  با ویژگی `@bind` :

```C#

<input placeholder="Something todo" @bind="newTodo" />
```

1. متد `AddTodo` را به روز کنید تا `TodoItem` با title مشخص شده به لیست اضافه شود. با تنظیم `newTodo` روی یک رشته خالی، مقدار ورودی متن را پاک کنید:

```C#

@page "/todo"

<PageTitle>Todo</PageTitle>

<h1>Todo</h1>

<ul>
    @foreach (var todo in todos)
    {
        <li>@todo.Title</li>
    }
</ul>

<input placeholder="Something todo" @bind="newTodo" />
<button @onclick="AddTodo">Add todo</button>

@code {
    private List<TodoItem> todos = new();
    private string? newTodo;

    private void AddTodo()
    {
        if (!string.IsNullOrWhiteSpace(newTodo))
        {
            todos.Add(new TodoItem { Title = newTodo });
            newTodo = string.Empty;
        }
    }
}
```

1. فایل `Pages/Todo.razor` را ذخیره کنید. برنامه به طور خودکار در command shell  rebuilt می شود و صفحه در مرورگر روباره لود می شود.


2. متن title برای هر مورد todo قابل ویرایش است و یک چک باکس می تواند به کاربر کمک کند تا موارد تکمیل شده را پیگیری کند. یک ورودی چک باکس برای هر مورد todo اضافه کنید و مقدار آن را به ویژگی `IsDone` متصل کنید. `@todo.Title` را به عنصر `<input>` محدود به `todo.Title` با `@bind` تغییر دهید:

```C#

<ul>
    @foreach (var todo in todos)
    {
        <li>
            <input type="checkbox" @bind="todo.IsDone" />
            <input @bind="todo.Title" />
        </li>
    }
</ul>
```


3. هدر `<h1>` را به روز کنید تا تعداد موارد انجام کار کامل نشده را نشان دهد (مقدار `IsDone` `false` است). عبارت Razor در هدر زیر هر بار که Blazor کامپوننت را رندر می کند ارزیابی می کند.


```C#

<h1>Todo (@todos.Count(todo => !todo.IsDone))</h1>
```

4. کامپوننت Todo  تکمیل شده (`Pages/Todo.razor`):


```C#

@page "/todo"

<PageTitle>Todo</PageTitle>

<h1>Todo (@todos.Count(todo => !todo.IsDone))</h1>

<ul>
    @foreach (var todo in todos)
    {
        <li>
            <input type="checkbox" @bind="todo.IsDone" />
            <input @bind="todo.Title" />
        </li>
    }
</ul>

<input placeholder="Something todo" @bind="newTodo" />
<button @onclick="AddTodo">Add todo</button>

@code {
    private List<TodoItem> todos = new();
    private string? newTodo;

    private void AddTodo()
    {
        if (!string.IsNullOrWhiteSpace(newTodo))
        {
            todos.Add(new TodoItem { Title = newTodo });
            newTodo = string.Empty;
        }
    }
}
```


1. فایل `Pages/Todo.razor` را ذخیره کنید. برنامه به طور خودکار در command shell  rebuilt می شود و صفحه در مرورگر بارگذاری مجدد می شود.


2. آیتم ها را اضافه کنید، آیتم ها را ویرایش کنید و موارد انجام کار را برای آزمایش کامپوننت علامت گذاری کنید.

3. پس از اتمام، برنامه را در command shell خاموش کنید. بسیاری از command shell‌ها دستورات صفحه کلید `Ctrl`+`C` (ویندوز) یا `⌘`+`C` (macOS) را برای توقف یک برنامه می‌پذیرند.


## انتشار در Azure

For information on deploying to Azure, see Quickstart: [Deploy an ASP.NET web app](https://learn.microsoft.com/en-us/azure/app-service/quickstart-dotnetcore).



**منبع:**

[https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/build-a-blazor-app?view=aspnetcore-7.0&pivots=server](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/build-a-blazor-app?view=aspnetcore-7.0&pivots=server)
