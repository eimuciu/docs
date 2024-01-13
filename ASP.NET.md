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

    public class TodoContext : DbContext

{
public TodoContext(DbContextOptions<TodoContext> options)
: base(options)
{
}
public DbSet<TodoItem> TodoItems { get; set; } = null!;

}

protected override void OnModelCreating(DbModelBuilder modelBuilder)
{
modelBuilder.Properties()
.Where(p => p.Name == "Key")
.Configure(p => p.IsKey());

modelBuilder.Entity<Student>()
.Property(s => s.StudentId)
.HasColumnName("Id")
.HasDefaultValue(0)
.IsRequired();
}

Fluent API
https://www.entityframeworktutorial.net/efcore/fluent-api-in-entity-framework-core.aspx#:~:text=Entity%20Framework%20Fluent%20API%20is,acts%20as%20a%20Fluent%20API.

