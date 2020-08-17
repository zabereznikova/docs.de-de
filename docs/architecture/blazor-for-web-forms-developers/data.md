---
title: Datenzugriff und-Verwaltung
description: Erfahren Sie, wie Sie auf Daten in ASP.net Web Forms und zugreifen und diese verarbeiten Blazor .
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/26/2020
ms.openlocfilehash: 8bd326e6952708b2099c3a575d6811990335df17
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267593"
---
# <a name="work-with-data"></a>Arbeiten mit Daten

Der Datenzugriff ist der Backbone einer ASP.net-Web Forms-app. Was geschieht mit diesen Daten, wenn Sie Formulare für das Web entwickeln? Mit Web Forms gab es mehrere Datenzugriffs Techniken, die Sie verwenden können, um mit einer Datenbank zu interagieren:

- Projektmappen-Explorer
- ADO.NET
- Entity Framework

Datenquellen waren Steuerelemente, die Sie auf einer Web Forms Seite platzieren und wie andere Steuerelemente konfigurieren können. Visual Studio bot einen benutzerfreundlichen Satz von Dialogfeldern, mit denen die Steuerelemente konfiguriert und an Ihre Web Forms Seiten gebunden werden können. Entwickler, die einen "niedrigen Code"-oder "No-Code"-Ansatz nutzen, bevorzugten diese Technik, als Web Forms erstmals veröffentlicht wurde.

![Projektmappen-Explorer](media/data/datasources.png)

ADO.net ist der Ansatz auf niedriger Ebene für die Interaktion mit einer-Datenbank. Ihre apps können eine Verbindung mit der Datenbank mit Befehlen, Recordsets und Datasets für die Interaktion herstellen. Die Ergebnisse können dann ohne großen Code an Felder auf dem Bildschirm gebunden werden. Der Nachteil dieses Ansatzes bestand darin, dass jeder Satz von ADO.NET-Objekten ( `Connection` , `Command` und `Recordset` ) an Bibliotheken gebunden wurde, die von einem Datenbankanbieter bereitgestellt werden. Durch die Verwendung dieser Komponenten wurde der Code starr und schwer zu einer anderen Datenbank migriert.

## <a name="entity-framework"></a>Entity Framework

Entity Framework (EF) ist das Open Source-objektrelationales Mapping-Framework, das von der .Net Foundation verwaltet wird. Bei der ersten Veröffentlichung mit .NET Framework ermöglicht EF das Erstellen von Code für die Datenbankverbindungen, Speicher Schemas und Interaktionen. Mit dieser Abstraktion können Sie sich auf die Geschäftsregeln Ihrer APP konzentrieren und zulassen, dass die Datenbank von einem vertrauenswürdigen Datenbankadministrator verwaltet wird. In .net Core können Sie eine aktualisierte Version von EF namens EF Core verwenden. EF Core unterstützt Sie bei der Generierung und Aufrechterhaltung der Interaktionen zwischen Ihrem Code und der Datenbank mit einer Reihe von Befehlen, die Sie mithilfe des `dotnet ef` Befehlszeilen Tools zur Verfügung stellen. Werfen wir einen Blick auf einige Beispiele, um Ihnen die Arbeit mit einer-Datenbank zu ermöglichen.

### <a name="ef-code-first"></a>EF-Code First

Eine schnelle Möglichkeit, Ihre Daten Bank Interaktionen zu entwickeln, besteht darin, mit den Klassen Objekten zu beginnen, mit denen Sie arbeiten möchten. EF bietet ein Tool, das Ihnen hilft, den entsprechenden Datenbankcode für Ihre Klassen zu generieren. Diese Vorgehensweise wird als "Code First"-Entwicklung bezeichnet. Beachten Sie die folgende `Product` Klasse für eine Beispiel-Store Front-APP, die in einer relationalen Datenbank wie Microsoft SQL Server gespeichert werden soll.

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

Das Produkt verfügt über einen Primärschlüssel und drei zusätzliche Felder, die in der Datenbank erstellt werden:  

- EF identifiziert die `Id` Eigenschaft gemäß der Konvention als Primärschlüssel.
- `Name` wird in einer Spalte gespeichert, die für die Text Speicherung konfiguriert ist. Das `[Required]` Attribut, das diese Eigenschaft schmückt, fügt eine `not null` Einschränkung hinzu, um dieses deklarierte Verhalten der Eigenschaft zu erzwingen.
- `Description` wird in einer Spalte gespeichert, die für die Text Speicherung konfiguriert ist, und kann eine maximale Länge von 4000 Zeichen aufweisen, die vom-Attribut vorgegeben wird `[MaxLength]` . Das Datenbankschema wird mit einer Spalte namens konfiguriert, die den- `MaxLength` Datentyp verwendet `varchar(4000)` .
- Die `Price` Eigenschaft wird als Währung gespeichert. Das- `[Range]` Attribut generiert geeignete Einschränkungen, um die Datenspeicherung außerhalb der deklarierten Mindest-und Höchstwerte zu verhindern.

Wir müssen diese `Product` Klasse einer Daten Bank Kontext Klasse hinzufügen, die die Verbindungs-und Übersetzungs Vorgänge mit unserer Datenbank definiert.

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

Die- `MyDbContext` Klasse stellt die eine Eigenschaft bereit, die den Zugriff und die Übersetzung für die- `Product` Klasse definiert.  Die Anwendung konfiguriert diese Klasse für die Interaktion mit der Datenbank mithilfe der folgenden Einträge in der `Startup` -Methode der-Klasse `ConfigureServices` :

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

Der vorangehende Code stellt eine Verbindung mit einer SQL Server Datenbank mit der angegebenen Verbindungs Zeichenfolge her. Sie können die Verbindungs Zeichenfolge in Ihrer *appsettings.jsfür* Datei, Umgebungsvariablen oder andere Konfigurations Speicherorte platzieren und diese eingebettete Zeichenfolge entsprechend ersetzen.

Anschließend können Sie die für diese Klasse geeignete Datenbanktabelle mithilfe der folgenden Befehle generieren:

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

Mit dem ersten Befehl werden die Änderungen, die Sie am Datenbankschema vornehmen, als neue EF-Migration namens definiert `Create Product table` .  Eine Migration definiert, wie die neuen Daten Bank Änderungen angewendet und entfernt werden.

Nach der Anwendung verfügen Sie über eine einfache `Product` Tabelle in der Datenbank und einige neue Klassen, die dem Projekt hinzugefügt wurden und die Verwaltung des Datenbankschemas erleichtern.  Sie finden diese generierten Klassen standardmäßig in einem neuen Ordner namens *Migrationen*.  Wenn Sie Änderungen an der `Product` Klasse vornehmen oder weitere verwandte Klassen hinzufügen möchten, die mit der Datenbank interagieren sollen, müssen Sie die Befehlszeilen Befehle mit einem neuen Namen für die Migration erneut ausführen.  Mit diesem Befehl wird ein weiterer Satz von Migrations Klassen generiert, um das Datenbankschema zu aktualisieren.

### <a name="ef-database-first"></a>EF-Database First

Für vorhandene Datenbanken können Sie die Klassen für EF Core mithilfe der .net-Befehlszeilen Tools generieren. Verwenden Sie zum Gerüstbau der Klassen eine Variation des folgenden Befehls:

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

Der vorherige Befehl stellt mithilfe der angegebenen Verbindungs Zeichenfolge und des Anbieters eine Verbindung mit der Datenbank her `Microsoft.EntityFrameworkCore.SqlServer` . Nachdem die Verbindung hergestellt wurde, wird eine Daten Bank Kontext Klasse namens `MyDbContext` erstellt. Außerdem werden Unterstützungs Klassen für die `Product` Tabellen und erstellt `Customer` , die mit den Optionen angegeben wurden `-t` . Es gibt viele Konfigurationsoptionen für diesen Befehl, um die für Ihre Datenbank geeignete Klassenhierarchie zu generieren. Eine umfassende Referenz finden Sie in [der Dokumentation des Befehls](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).

Weitere Informationen zu [EF Core](/ef/core/) finden Sie auf der Microsoft-Dokumentation Website.

## <a name="interact-with-web-services"></a>Interagieren mit Webdiensten

Bei der ersten Veröffentlichung von ASP.net waren SOAP-Dienste die bevorzugte Methode für Webserver und Clients zum Austauschen von Daten. Seit dieser Zeit hat sich viel geändert, und die bevorzugten Interaktionen mit Diensten wurden zu direkten http-Client Interaktionen verlagert. Mit ASP.net Core und Blazor können Sie die Konfiguration Ihrer `HttpClient` in der `Startup` -Methode der-Klasse registrieren `ConfigureServices` . Verwenden Sie diese Konfiguration, wenn Sie mit dem HTTP-Endpunkt interagieren müssen. Beachten Sie den folgenden Konfigurations Code:

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

Wenn Sie auf Daten von GitHub zugreifen müssen, erstellen Sie einen Client mit dem Namen `github` . Der Client wird mit der Basisadresse konfiguriert, und die Anforderungs Header sind entsprechend festgelegt. Fügen `IHttpClientFactory` Sie das- Blazor Objekt mit der- `@inject` Anweisung oder einem- `[Inject]` Attribut für eine Eigenschaft in die-Komponenten ein. Erstellen Sie den benannten Client, und interagieren Sie mit den Diensten mit der folgenden Syntax:

```razor
@inject IHttpClientFactory factory

...

@code {
    protected override async Task OnInitializedAsync()
    {
        var client = factory.CreateClient("github");
        var response = await client.GetAsync("repos/dotnet/docs/issues");
        response.EnsureStatusCode();
        var content = async response.Content.ReadAsStringAsync();
    }
}
```

Diese Methode gibt die Zeichenfolge zurück, die die Sammlung von Problemen im *dotnet/docs-* GitHub-Repository beschreibt. Der Inhalt wird im JSON-Format zurückgegeben und in entsprechende GitHub-Issue-Objekte deserialisiert. Es gibt viele Methoden, die Sie so konfigurieren können `HttpClientFactory` , dass vorkonfigurierte Objekte bereitgestellt werden `HttpClient` . Versuchen Sie, mehrere `HttpClient` Instanzen mit unterschiedlichen Namen und Endpunkten für die verschiedenen Webdienste zu konfigurieren, mit denen Sie arbeiten. Diese Vorgehensweise führt dazu, dass die Interaktion mit diesen Diensten auf jeder Seite einfacher funktioniert. Weitere Informationen finden Sie in [der Dokumentation für die ihttpclientfactory](/aspnet/core/fundamentals/http-requests).

>[!div class="step-by-step"]
>[Zurück](forms-validation.md)
>[Weiter](middleware.md)
