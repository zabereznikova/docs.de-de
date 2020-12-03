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
# <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="a7375-103">Middleware: Datenbankfehlerseite als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="a7375-103">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="a7375-104">Die [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) und die zugehörigen Erweiterungsmethoden wurden in ASP.NET Core 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="a7375-104">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="a7375-105">Die Middleware und Erweiterungsmethoden werden in ASP.NET Core 6.0 entfernt.</span><span class="sxs-lookup"><span data-stu-id="a7375-105">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="a7375-106">Die Funktionalität wird stattdessen von `DatabaseDeveloperPageExceptionFilter` und den zugehörigen Erweiterungsmethoden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a7375-106">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="a7375-107">Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span><span class="sxs-lookup"><span data-stu-id="a7375-107">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a7375-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a7375-108">Version introduced</span></span>

<span data-ttu-id="a7375-109">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="a7375-109">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="a7375-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="a7375-110">Old behavior</span></span>

<span data-ttu-id="a7375-111">`DatabaseErrorPageMiddleware` und die zugehörigen Erweiterungsmethoden waren nicht veraltet.</span><span class="sxs-lookup"><span data-stu-id="a7375-111">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="a7375-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="a7375-112">New behavior</span></span>

<span data-ttu-id="a7375-113">`DatabaseErrorPageMiddleware` und die zugehörigen Erweiterungsmethoden sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="a7375-113">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a7375-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a7375-114">Reason for change</span></span>

<span data-ttu-id="a7375-115">`DatabaseErrorPageMiddleware` wurde in eine erweiterbare API für die [Seite mit Ausnahmen für Entwickler](/aspnet/core/fundamentals/error-handling#developer-exception-page) migriert.</span><span class="sxs-lookup"><span data-stu-id="a7375-115">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="a7375-116">Weitere Informationen zur erweiterbaren API finden Sie im GitHub-Issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span><span class="sxs-lookup"><span data-stu-id="a7375-116">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a7375-117">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a7375-117">Recommended action</span></span>

<span data-ttu-id="a7375-118">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a7375-118">Complete the following steps:</span></span>

1. <span data-ttu-id="a7375-119">Verwenden Sie `DatabaseErrorPageMiddleware` nicht mehr in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="a7375-119">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="a7375-120">Entfernen Sie beispielsweise den Methodenaufruf `UseDatabaseErrorPage` aus `Startup.Configure`:</span><span class="sxs-lookup"><span data-stu-id="a7375-120">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="a7375-121">Fügen Sie die Seite mit Ausnahmen für Entwickler zu Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7375-121">Add the developer exception page to your project.</span></span> <span data-ttu-id="a7375-122">Rufen Sie beispielsweise die Methode <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> in `Startup.Configure` auf:</span><span class="sxs-lookup"><span data-stu-id="a7375-122">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="a7375-123">Fügen Sie das NuGet-Paket [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) zur Projektdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7375-123">Add the [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet package to the project file.</span></span>

1. <span data-ttu-id="a7375-124">Fügen Sie den Datenbankfilter für die Seite mit Ausnahmen für Entwickler zu der Dienstsammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7375-124">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="a7375-125">Rufen Sie beispielsweise die Methode `AddDatabaseDeveloperPageExceptionFilter` in `Startup.ConfigureServices` auf:</span><span class="sxs-lookup"><span data-stu-id="a7375-125">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

## <a name="affected-apis"></a><span data-ttu-id="a7375-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a7375-126">Affected APIs</span></span>

- [<span data-ttu-id="a7375-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="a7375-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="a7375-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="a7375-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
