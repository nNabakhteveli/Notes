# Entity Framework Core CLI (tools library)

Run migration: ```dotnet ef migrations add <name>```

In case of multiple classes which inherit from DbContext class: ```dotnet ef migrations add <name> --context <class name>```

Update Database: ```dotnet ef database update```
