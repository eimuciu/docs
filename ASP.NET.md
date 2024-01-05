# ASP.NET docs

# Controllers

builder.Services.AddControllers();
app.MapControllers();

[Route("api/[controller]")]
[ApiController]
public class TodoItemsController : ControllerBase

[HttpGet]
[HttpGet("{id}")]
[HttpPut("{id}")]
[HttpPost]
[HttpDelete("{id}")]
