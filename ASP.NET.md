# ASP.NET docs

# Minimal API

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "Hello World!");

app.Run();

# Controllers

builder.Services.AddControllers();
app.MapControllers();

[Route("api/[controller]")]
[ApiController]
public class TodoItemsController : ControllerBase {}

[HttpGet]
[HttpGet("{id}")]
[HttpPut("{id}")]
[HttpPost]
[HttpDelete("{id}")]

# Entity Framework
https://learn.microsoft.com/en-us/ef/ef6/querying/

builder.Services.AddDbContext<TodoContext>(opt =>
    opt.UseInMemoryDatabase("TodoList"));