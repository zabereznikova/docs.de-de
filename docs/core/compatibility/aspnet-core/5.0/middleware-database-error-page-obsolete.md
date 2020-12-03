---
title: 'Breaking Change: Middleware: Datenbankfehlerseite als veraltet markiert'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Middleware: Datenbankfehlerseite als veraltet markiert'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f828b5e20c2a9a709d675e435caa99727aebd5b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759507"
---
# <a name="middleware-database-error-page-marked-as-obsolete"></a>Middleware: Datenbankfehlerseite als veraltet markiert

Die [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) und die zugehörigen Erweiterungsmethoden wurden in ASP.NET Core 5.0 als veraltet markiert. Die Middleware und Erweiterungsmethoden werden in ASP.NET Core 6.0 entfernt. Die Funktionalität wird stattdessen von `DatabaseDeveloperPageExceptionFilter` und den zugehörigen Erweiterungsmethoden bereitgestellt.

Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).

## <a name="version-introduced"></a>Eingeführt in Version

5.0 RC 1

## <a name="old-behavior"></a>Altes Verhalten

`DatabaseErrorPageMiddleware` und die zugehörigen Erweiterungsmethoden waren nicht veraltet.

## <a name="new-behavior"></a>Neues Verhalten

`DatabaseErrorPageMiddleware` und die zugehörigen Erweiterungsmethoden sind veraltet.

## <a name="reason-for-change"></a>Grund für die Änderung

`DatabaseErrorPageMiddleware` wurde in eine erweiterbare API für die [Seite mit Ausnahmen für Entwickler](/aspnet/core/fundamentals/error-handling#developer-exception-page) migriert. Weitere Informationen zur erweiterbaren API finden Sie im GitHub-Issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).

## <a name="recommended-action"></a>Empfohlene Aktion

Führen Sie die folgenden Schritte aus:

1. Verwenden Sie `DatabaseErrorPageMiddleware` nicht mehr in Ihrem Projekt. Entfernen Sie beispielsweise den Methodenaufruf `UseDatabaseErrorPage` aus `Startup.Configure`:

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. Fügen Sie die Seite mit Ausnahmen für Entwickler zu Ihrem Projekt hinzu. Rufen Sie beispielsweise die Methode <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> in `Startup.Configure` auf:

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. Fügen Sie das NuGet-Paket [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) zur Projektdatei hinzu.

1. Fügen Sie den Datenbankfilter für die Seite mit Ausnahmen für Entwickler zu der Dienstsammlung hinzu. Rufen Sie beispielsweise die Methode `AddDatabaseDeveloperPageExceptionFilter` in `Startup.ConfigureServices` auf:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

## <a name="affected-apis"></a>Betroffene APIs

- [Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
