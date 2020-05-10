# DotNetCore
## Notes
* At its heart, ASP.NET Core apps map incoming requests to outgoing responses.
* `[ApiController]` attribute adds automatic model validation checking and any action with an invalid model will return a BadRequest with the details of the validation errors. The attribute also requires all actions have an attribute route.
* Static cling (code smell) occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.
* Each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.
* You should follow the Explicit Dependencies Principle, requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.
* Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling.
* A filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action `[ValidateAuthorExists]`.

## References
* [Architect Modern Web Applications with ASP.NET Core and Azure](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/)
* [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/en-us/dotnet/architecture/microservices/)
