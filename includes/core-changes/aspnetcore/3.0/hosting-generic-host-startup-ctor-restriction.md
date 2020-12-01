---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032506"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein.

Die einzigen Typen, die vom generischen Host für Konstruktorinjektionen der `Startup`-Klasse unterstützt werden, sind `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration`. Apps, die `WebHost` verwenden, sind nicht betroffen.

#### <a name="change-description"></a>Änderungsbeschreibung

Vor ASP.NET Core 3.0 konnte die Konstruktorinjektion für beliebige Typen im Konstruktor der `Startup`-Klasse verwendet werden. In ASP.NET Core 3.0 wurde der Webstapel der Bibliothek des generischen Hosts zugeordnet. Sie können die Änderung in der Datei *Program.cs*  der Vorlagen sehen:

**ASP.NET Core 2.x:**

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3.0:**

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host` verwendet einen Container zur Abhängigkeitsinjektion, um die App zu erstellen. `WebHost` verwendet zwei Container: einen für den Host und einen für die App. Daher unterstützt der `Startup`-Konstruktor keine benutzerdefinierte Dienstinjektion mehr. Es können nur `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration` eingefügt werden. Diese Änderung verhindert Probleme mit Abhängigkeitsinjektionen, z. B. die doppelte Erstellung eines Singletondiensts.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ist eine Folge der geänderten Zuordnung des Webstapels zur Bibliothek des generischen Hosts.

#### <a name="recommended-action"></a>Empfohlene Aktion

Fügen Sie Dienste in die Signatur der `Startup.Configure`-Methode ein. Zum Beispiel:

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
