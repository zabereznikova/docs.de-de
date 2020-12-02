---
title: Datenzugriff und-Verwaltung
description: Erfahren Sie, wie Sie auf Daten in ASP.net Web Forms und zugreifen und diese verarbeiten Blazor .
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 11/20/2020
ms.openlocfilehash: 66e6001cbcac612cb556e90fb86fd694ca7d1459
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509753"
---
# <a name="work-with-data"></a><span data-ttu-id="db7d3-103">Arbeiten mit Daten</span><span class="sxs-lookup"><span data-stu-id="db7d3-103">Work with data</span></span>

<span data-ttu-id="db7d3-104">Der Datenzugriff ist der Backbone einer ASP.net-Web Forms-app.</span><span class="sxs-lookup"><span data-stu-id="db7d3-104">Data access is the backbone of an ASP.NET Web Forms app.</span></span> <span data-ttu-id="db7d3-105">Was geschieht mit diesen Daten, wenn Sie Formulare für das Web entwickeln?</span><span class="sxs-lookup"><span data-stu-id="db7d3-105">If you're building forms for the web, what happens to that data?</span></span> <span data-ttu-id="db7d3-106">Mit Web Forms gab es mehrere Datenzugriffs Techniken, die Sie verwenden können, um mit einer Datenbank zu interagieren:</span><span class="sxs-lookup"><span data-stu-id="db7d3-106">With Web Forms, there were multiple data access techniques you could use to interact with a database:</span></span>

- <span data-ttu-id="db7d3-107">Projektmappen-Explorer</span><span class="sxs-lookup"><span data-stu-id="db7d3-107">Data Sources</span></span>
- <span data-ttu-id="db7d3-108">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="db7d3-108">ADO.NET</span></span>
- <span data-ttu-id="db7d3-109">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="db7d3-109">Entity Framework</span></span>

<span data-ttu-id="db7d3-110">Datenquellen waren Steuerelemente, die Sie auf einer Web Forms Seite platzieren und wie andere Steuerelemente konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="db7d3-110">Data Sources were controls that you could place on a Web Forms page and configure like other controls.</span></span> <span data-ttu-id="db7d3-111">Visual Studio bot einen benutzerfreundlichen Satz von Dialogfeldern, mit denen die Steuerelemente konfiguriert und an Ihre Web Forms Seiten gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="db7d3-111">Visual Studio provided a friendly set of dialogs to configure and bind the controls to your Web Forms pages.</span></span> <span data-ttu-id="db7d3-112">Entwickler, die einen "niedrigen Code"-oder "No-Code"-Ansatz nutzen, bevorzugten diese Technik, als Web Forms erstmals veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="db7d3-112">Developers who enjoy a "low code" or "no code" approach preferred this technique when Web Forms was first released.</span></span>

![Projektmappen-Explorer](media/data/datasources.png)

<span data-ttu-id="db7d3-114">ADO.net ist der Ansatz auf niedriger Ebene für die Interaktion mit einer-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="db7d3-114">ADO.NET is the low-level approach to interacting with a database.</span></span> <span data-ttu-id="db7d3-115">Ihre apps können eine Verbindung mit der Datenbank mit Befehlen, Recordsets und Datasets für die Interaktion herstellen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-115">Your apps could create a connection to the database with Commands, Recordsets, and Datasets for interacting.</span></span> <span data-ttu-id="db7d3-116">Die Ergebnisse können dann ohne großen Code an Felder auf dem Bildschirm gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="db7d3-116">The results could then be bound to fields on screen without much code.</span></span> <span data-ttu-id="db7d3-117">Der Nachteil dieses Ansatzes bestand darin, dass jeder Satz von ADO.NET-Objekten ( `Connection` , `Command` und `Recordset` ) an Bibliotheken gebunden wurde, die von einem Datenbankanbieter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="db7d3-117">The drawback of this approach was that each set of ADO.NET objects (`Connection`, `Command`, and `Recordset`) was bound to libraries provided by a database vendor.</span></span> <span data-ttu-id="db7d3-118">Durch die Verwendung dieser Komponenten wurde der Code starr und schwer zu einer anderen Datenbank migriert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-118">Use of these components made the code rigid and difficult to migrate to a different database.</span></span>

## <a name="entity-framework"></a><span data-ttu-id="db7d3-119">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="db7d3-119">Entity Framework</span></span>

<span data-ttu-id="db7d3-120">Entity Framework (EF) ist das Open Source-objektrelationales Mapping-Framework, das von der .Net Foundation verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="db7d3-120">Entity Framework (EF) is the open source object-relational mapping framework maintained by the .NET Foundation.</span></span> <span data-ttu-id="db7d3-121">Bei der ersten Veröffentlichung mit .NET Framework ermöglicht EF das Erstellen von Code für die Datenbankverbindungen, Speicher Schemas und Interaktionen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-121">Initially released with .NET Framework, EF allows for generating code for the database connections, storage schemas, and interactions.</span></span> <span data-ttu-id="db7d3-122">Mit dieser Abstraktion können Sie sich auf die Geschäftsregeln Ihrer APP konzentrieren und zulassen, dass die Datenbank von einem vertrauenswürdigen Datenbankadministrator verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="db7d3-122">With this abstraction, you can focus on your app's business rules and allow the database to be managed by a trusted database administrator.</span></span> <span data-ttu-id="db7d3-123">In .net können Sie eine aktualisierte Version von EF verwenden, die als EF Core bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="db7d3-123">In .NET, you can use an updated version of EF called EF Core.</span></span> <span data-ttu-id="db7d3-124">EF Core unterstützt Sie bei der Generierung und Aufrechterhaltung der Interaktionen zwischen Ihrem Code und der Datenbank mit einer Reihe von Befehlen, die Sie mithilfe des `dotnet ef` Befehlszeilen Tools zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-124">EF Core helps generate and maintain the interactions between your code and the database with a series of commands that are available for you using the `dotnet ef` command-line tool.</span></span> <span data-ttu-id="db7d3-125">Werfen wir einen Blick auf einige Beispiele, um Ihnen die Arbeit mit einer-Datenbank zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-125">Let's take a look at a few samples to get you working with a database.</span></span>

### <a name="ef-code-first"></a><span data-ttu-id="db7d3-126">EF-Code First</span><span class="sxs-lookup"><span data-stu-id="db7d3-126">EF Code First</span></span>

<span data-ttu-id="db7d3-127">Eine schnelle Möglichkeit, Ihre Daten Bank Interaktionen zu entwickeln, besteht darin, mit den Klassen Objekten zu beginnen, mit denen Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="db7d3-127">A quick way to get started building your database interactions is to start with the class objects you want to work with.</span></span> <span data-ttu-id="db7d3-128">EF bietet ein Tool, das Ihnen hilft, den entsprechenden Datenbankcode für Ihre Klassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="db7d3-128">EF provides a tool to help generate the appropriate database code for your classes.</span></span> <span data-ttu-id="db7d3-129">Diese Vorgehensweise wird als "Code First"-Entwicklung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="db7d3-129">This approach is called "Code First" development.</span></span> <span data-ttu-id="db7d3-130">Beachten Sie die folgende `Product` Klasse für eine Beispiel-Store Front-APP, die in einer relationalen Datenbank wie Microsoft SQL Server gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="db7d3-130">Consider the following `Product` class for a sample storefront app that we want to store in a relational database like Microsoft SQL Server.</span></span>

```csharp
public class Product
{
    public int Id { get; set; }

    [Required]
    public string Name { get; set; }

    [MaxLength(4000)]
    public string Description { get; set; }

    [Range(0, 99999,99)]
    [DataType(DataType.Currency)]
    public decimal Price { get; set; }
}
```

<span data-ttu-id="db7d3-131">Das Produkt verfügt über einen Primärschlüssel und drei zusätzliche Felder, die in der Datenbank erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="db7d3-131">Product has a primary key and three additional fields that would be created in our database:</span></span>  

- <span data-ttu-id="db7d3-132">EF identifiziert die `Id` Eigenschaft gemäß der Konvention als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="db7d3-132">EF will identify the `Id` property as a primary key by convention.</span></span>
- <span data-ttu-id="db7d3-133">`Name` wird in einer Spalte gespeichert, die für die Text Speicherung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="db7d3-133">`Name` will be stored in a column configured for text storage.</span></span> <span data-ttu-id="db7d3-134">Das `[Required]` Attribut, das diese Eigenschaft schmückt, fügt eine `not null` Einschränkung hinzu, um dieses deklarierte Verhalten der Eigenschaft zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-134">The `[Required]` attribute decorating this property will add a `not null` constraint to help enforce this declared behavior of the property.</span></span>
- <span data-ttu-id="db7d3-135">`Description` wird in einer Spalte gespeichert, die für die Text Speicherung konfiguriert ist, und kann eine maximale Länge von 4000 Zeichen aufweisen, die vom-Attribut vorgegeben wird `[MaxLength]` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-135">`Description` will be stored in a column configured for text storage, and have a maximum length configured of 4000 characters as dictated by the `[MaxLength]` attribute.</span></span> <span data-ttu-id="db7d3-136">Das Datenbankschema wird mit einer Spalte namens konfiguriert, die den- `MaxLength` Datentyp verwendet `varchar(4000)` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-136">The database schema will be configured with a column named `MaxLength` using data type `varchar(4000)`.</span></span>
- <span data-ttu-id="db7d3-137">Die `Price` Eigenschaft wird als Währung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-137">The `Price` property will be stored as currency.</span></span> <span data-ttu-id="db7d3-138">Das- `[Range]` Attribut generiert geeignete Einschränkungen, um die Datenspeicherung außerhalb der deklarierten Mindest-und Höchstwerte zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="db7d3-138">The `[Range]` attribute will generate appropriate constraints to prevent data storage outside of the minimum and maximum values declared.</span></span>

<span data-ttu-id="db7d3-139">Wir müssen diese `Product` Klasse einer Daten Bank Kontext Klasse hinzufügen, die die Verbindungs-und Übersetzungs Vorgänge mit unserer Datenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-139">We need to add this `Product` class to a database context class that defines the connection and translation operations with our database.</span></span>

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

<span data-ttu-id="db7d3-140">Die- `MyDbContext` Klasse stellt die eine Eigenschaft bereit, die den Zugriff und die Übersetzung für die- `Product` Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-140">The `MyDbContext` class provides the one property that defines the access and translation for the `Product` class.</span></span>  <span data-ttu-id="db7d3-141">Die Anwendung konfiguriert diese Klasse für die Interaktion mit der Datenbank mithilfe der folgenden Einträge in der `Startup` -Methode der-Klasse `ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="db7d3-141">Your application configures this class for interaction with the database using the following entries in the `Startup` class's `ConfigureServices` method:</span></span>

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

<span data-ttu-id="db7d3-142">Der vorangehende Code stellt eine Verbindung mit einer SQL Server Datenbank mit der angegebenen Verbindungs Zeichenfolge her.</span><span class="sxs-lookup"><span data-stu-id="db7d3-142">The preceding code will connect to a SQL Server database with the specified connection string.</span></span> <span data-ttu-id="db7d3-143">Sie können die Verbindungs Zeichenfolge in Ihrer *appsettings.jsfür* Datei, Umgebungsvariablen oder andere Konfigurations Speicherorte platzieren und diese eingebettete Zeichenfolge entsprechend ersetzen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-143">You can place the connection string in your *appsettings.json* file, environment variables, or other configuration storage locations and replace this embedded string appropriately.</span></span>

<span data-ttu-id="db7d3-144">Anschließend können Sie die für diese Klasse geeignete Datenbanktabelle mithilfe der folgenden Befehle generieren:</span><span class="sxs-lookup"><span data-stu-id="db7d3-144">You can then generate the database table appropriate for this class using the following commands:</span></span>

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

<span data-ttu-id="db7d3-145">Mit dem ersten Befehl werden die Änderungen, die Sie am Datenbankschema vornehmen, als neue EF-Migration namens definiert `Create Product table` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-145">The first command defines the changes you're making to the database schema as a new EF Migration called `Create Product table`.</span></span>  <span data-ttu-id="db7d3-146">Eine Migration definiert, wie die neuen Daten Bank Änderungen angewendet und entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="db7d3-146">A Migration defines how to apply and remove your new database changes.</span></span>

<span data-ttu-id="db7d3-147">Nach der Anwendung verfügen Sie über eine einfache `Product` Tabelle in der Datenbank und einige neue Klassen, die dem Projekt hinzugefügt wurden und die Verwaltung des Datenbankschemas erleichtern.</span><span class="sxs-lookup"><span data-stu-id="db7d3-147">Once applied, you have a simple `Product` table in your database and some new classes added to the project that help manage the database schema.</span></span>  <span data-ttu-id="db7d3-148">Sie finden diese generierten Klassen standardmäßig in einem neuen Ordner namens *Migrationen*.</span><span class="sxs-lookup"><span data-stu-id="db7d3-148">You can find these generated classes, by default, in a new folder called *Migrations*.</span></span>  <span data-ttu-id="db7d3-149">Wenn Sie Änderungen an der `Product` Klasse vornehmen oder weitere verwandte Klassen hinzufügen möchten, die mit der Datenbank interagieren sollen, müssen Sie die Befehlszeilen Befehle mit einem neuen Namen für die Migration erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-149">When you make changes to the `Product` class or add more related classes you would like interacting with your database, you need to run the command-line commands again with a new name of the migration.</span></span>  <span data-ttu-id="db7d3-150">Mit diesem Befehl wird ein weiterer Satz von Migrations Klassen generiert, um das Datenbankschema zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="db7d3-150">This command will generate another set of migration classes to update your database schema.</span></span>

### <a name="ef-database-first"></a><span data-ttu-id="db7d3-151">EF-Database First</span><span class="sxs-lookup"><span data-stu-id="db7d3-151">EF Database First</span></span>

<span data-ttu-id="db7d3-152">Für vorhandene Datenbanken können Sie die Klassen für EF Core mithilfe der .net-Befehlszeilen Tools generieren.</span><span class="sxs-lookup"><span data-stu-id="db7d3-152">For existing databases, you can generate the classes for EF Core by using the .NET command-line tools.</span></span> <span data-ttu-id="db7d3-153">Verwenden Sie zum Gerüstbau der Klassen eine Variation des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="db7d3-153">To scaffold the classes, use a variation of the following command:</span></span>

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

<span data-ttu-id="db7d3-154">Der vorherige Befehl stellt mithilfe der angegebenen Verbindungs Zeichenfolge und des Anbieters eine Verbindung mit der Datenbank her `Microsoft.EntityFrameworkCore.SqlServer` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-154">The preceding command connects to the database using the specified connection string and the `Microsoft.EntityFrameworkCore.SqlServer` provider.</span></span> <span data-ttu-id="db7d3-155">Nachdem die Verbindung hergestellt wurde, wird eine Daten Bank Kontext Klasse namens `MyDbContext` erstellt.</span><span class="sxs-lookup"><span data-stu-id="db7d3-155">Once connected, a database context class named `MyDbContext` is created.</span></span> <span data-ttu-id="db7d3-156">Außerdem werden Unterstützungs Klassen für die `Product` Tabellen und erstellt `Customer` , die mit den Optionen angegeben wurden `-t` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-156">Additionally, supporting classes are created for the `Product` and `Customer` tables that were specified with the `-t` options.</span></span> <span data-ttu-id="db7d3-157">Es gibt viele Konfigurationsoptionen für diesen Befehl, um die für Ihre Datenbank geeignete Klassenhierarchie zu generieren.</span><span class="sxs-lookup"><span data-stu-id="db7d3-157">There are many configuration options for this command to generate the class hierarchy appropriate for your database.</span></span> <span data-ttu-id="db7d3-158">Eine umfassende Referenz finden Sie in [der Dokumentation des Befehls](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span><span class="sxs-lookup"><span data-stu-id="db7d3-158">For a complete reference, see [the command's documentation](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span></span>

<span data-ttu-id="db7d3-159">Weitere Informationen zu [EF Core](/ef/core/) finden Sie auf der Microsoft-Dokumentation Website.</span><span class="sxs-lookup"><span data-stu-id="db7d3-159">More information about [EF Core](/ef/core/) can be found on the Microsoft Docs site.</span></span>

## <a name="interact-with-web-services"></a><span data-ttu-id="db7d3-160">Interagieren mit Webdiensten</span><span class="sxs-lookup"><span data-stu-id="db7d3-160">Interact with web services</span></span>

<span data-ttu-id="db7d3-161">Bei der ersten Veröffentlichung von ASP.net waren SOAP-Dienste die bevorzugte Methode für Webserver und Clients zum Austauschen von Daten.</span><span class="sxs-lookup"><span data-stu-id="db7d3-161">When ASP.NET was first released, SOAP services were the preferred way for web servers and clients to exchange data.</span></span> <span data-ttu-id="db7d3-162">Seit dieser Zeit hat sich viel geändert, und die bevorzugten Interaktionen mit Diensten wurden zu direkten http-Client Interaktionen verlagert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-162">Much has changed since that time, and the preferred interactions with services have shifted to direct HTTP client interactions.</span></span> <span data-ttu-id="db7d3-163">Mit ASP.net Core und Blazor können Sie die Konfiguration Ihrer `HttpClient` in der `Startup` -Methode der-Klasse registrieren `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-163">With ASP.NET Core and Blazor, you can register the configuration of your `HttpClient` in the `Startup` class's `ConfigureServices` method.</span></span> <span data-ttu-id="db7d3-164">Verwenden Sie diese Konfiguration, wenn Sie mit dem HTTP-Endpunkt interagieren müssen.</span><span class="sxs-lookup"><span data-stu-id="db7d3-164">Use that configuration when you need to interact with the HTTP endpoint.</span></span> <span data-ttu-id="db7d3-165">Beachten Sie den folgenden Konfigurations Code:</span><span class="sxs-lookup"><span data-stu-id="db7d3-165">Consider the following configuration code:</span></span>

```csharp
services.AddHttpClient("github", client =>
{
    client.BaseAddress = new Uri("http://api.github.com/");
    // Github API versioning
    client.DefaultRequestHeaders.Add("Accept", "application/vnd.github.v3+json");
    // Github requires a user-agent
    client.DefaultRequestHeaders.Add("User-Agent", "BlazorWebForms-Sample");
});
```

<span data-ttu-id="db7d3-166">Wenn Sie auf Daten von GitHub zugreifen müssen, erstellen Sie einen Client mit dem Namen `github` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-166">Whenever you need to access data from GitHub, create a client with a name of `github`.</span></span> <span data-ttu-id="db7d3-167">Der Client wird mit der Basisadresse konfiguriert, und die Anforderungs Header sind entsprechend festgelegt.</span><span class="sxs-lookup"><span data-stu-id="db7d3-167">The client is configured with the base address, and the request headers are set appropriately.</span></span> <span data-ttu-id="db7d3-168">Fügen `IHttpClientFactory` Sie das- Blazor Objekt mit der- `@inject` Anweisung oder einem- `[Inject]` Attribut für eine Eigenschaft in die-Komponenten ein.</span><span class="sxs-lookup"><span data-stu-id="db7d3-168">Inject the `IHttpClientFactory` into your Blazor components with the `@inject` directive or an `[Inject]` attribute on a property.</span></span> <span data-ttu-id="db7d3-169">Erstellen Sie den benannten Client, und interagieren Sie mit den Diensten mit der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="db7d3-169">Create your named client and interact with services using the following syntax:</span></span>

```razor
@inject IHttpClientFactory factory

...

@code {
    protected override async Task OnInitializedAsync()
    {
        var client = factory.CreateClient("github");
        var response = await client.GetAsync("repos/dotnet/docs/issues");
        response.EnsureStatusCode();
        var content = await response.Content.ReadAsStringAsync();
    }
}
```

<span data-ttu-id="db7d3-170">Diese Methode gibt die Zeichenfolge zurück, die die Sammlung von Problemen im *dotnet/docs-* GitHub-Repository beschreibt.</span><span class="sxs-lookup"><span data-stu-id="db7d3-170">This method returns the string describing the collection of issues in the *dotnet/docs* GitHub repository.</span></span> <span data-ttu-id="db7d3-171">Der Inhalt wird im JSON-Format zurückgegeben und in entsprechende GitHub-Issue-Objekte deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-171">It returns content in JSON format and is deserialized into appropriate GitHub issue objects.</span></span> <span data-ttu-id="db7d3-172">Es gibt viele Methoden, die Sie so konfigurieren können `HttpClientFactory` , dass vorkonfigurierte Objekte bereitgestellt werden `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="db7d3-172">There are many ways that you can configure the `HttpClientFactory` to deliver preconfigured `HttpClient` objects.</span></span> <span data-ttu-id="db7d3-173">Versuchen Sie, mehrere `HttpClient` Instanzen mit unterschiedlichen Namen und Endpunkten für die verschiedenen Webdienste zu konfigurieren, mit denen Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="db7d3-173">Try configuring multiple `HttpClient` instances with different names and endpoints for the various web services you work with.</span></span> <span data-ttu-id="db7d3-174">Diese Vorgehensweise führt dazu, dass die Interaktion mit diesen Diensten auf jeder Seite einfacher funktioniert.</span><span class="sxs-lookup"><span data-stu-id="db7d3-174">This approach will make your interactions with those services easier to work with on each page.</span></span> <span data-ttu-id="db7d3-175">Weitere Informationen finden Sie in [der Dokumentation für die ihttpclientfactory](/aspnet/core/fundamentals/http-requests).</span><span class="sxs-lookup"><span data-stu-id="db7d3-175">For more details, read [the documentation for the IHttpClientFactory](/aspnet/core/fundamentals/http-requests).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="db7d3-176">[Zurück](forms-validation.md)
>[Weiter](middleware.md)</span><span class="sxs-lookup"><span data-stu-id="db7d3-176">[Previous](forms-validation.md)
[Next](middleware.md)</span></span>
