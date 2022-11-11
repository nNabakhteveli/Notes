# Entity Framework Core CLI (tools library)

Run migration: ```dotnet ef migrations add <name>```

In case of multiple classes which inherit from DbContext class: ```dotnet ef migrations add <name> --context <class name>```

Update Database: ```dotnet ef database update```



# Common errors 
### 1.
```Method not found: 'Void CoreTypeMappingParameters..ctor(System.Type, Microsoft.EntityFrameworkCore.Storage.ValueConversion.ValueConverter, Microsoft.EntityFrameworkCore.ChangeTracking.ValueComparer, Microsoft.EntityFrameworkCore.ChangeTracking.ValueComparer, System.Func`3<Microsoft.EntityFrameworkCore.Metadata.IProperty,Microsoft.EntityFrameworkCore.Metadata.IEntityType,Microsoft.EntityFrameworkCore.ValueGeneration.ValueGenerator>)'.```

Usually happens when EntityFrameworkCore packages have different versions. For example:
```
  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="7.0.0-rc.2.22472.11"/>
    <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="7.0.0-rc.2.22472.11">
    <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="6.0.10"/> // <-- all packages should be the same version
  </ItemGroup>
```
