# DotNetCore
## Notes
* At its heart, ASP.NET Core apps map incoming requests to outgoing responses.
* `[ApiController]` attribute adds automatic model validation checking and any action with an invalid model will return a BadRequest with the details of the validation errors. The attribute also requires all actions have an attribute route.
* Static cling (code smell) occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.
* Each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.
* You should follow the Explicit Dependencies Principle, requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.
* Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling.
* A filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action `[ValidateAuthorExists]`.
* Claims are name value pairs that represent properties of an authenticated user.
* Most web APIs should implement a token-based authentication system.
* Value objects, which represent concepts that can be compared on the basis of the sum of their property values. For example, DateRange consisting of a start and end date.
* The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.
* It's important in the above example to add the call to ToListAsync in order to execute the query immediately. Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.
* t's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.
* In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.
* Eager loading means that the related data is loaded from the database as part of the initial query.
* To include relationships with an entity using eager loading, you specify the property using the Include extension method on the query.
```csharp
  .Include("Items.Products");
  .Include(blog => blog.Posts).ThenInclude(post => post.Author)
```


## References
* [Architect Modern Web Applications with ASP.NET Core and Azure](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/)
* [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/en-us/dotnet/architecture/microservices/)
* [Real-World ASP.NET Core MVC Filters](https://docs.microsoft.com/en-us/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters)
