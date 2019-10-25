---
ms.openlocfilehash: be9a79f6ead3e72d7ffaade758704f0c1e2477f0
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394304"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein.

Die einzigen Typen, die vom generischen Host für Konstruktorinjektionen der `Startup`-Klasse unterstützt werden, sind `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration`. Apps, die `WebHost` verwenden, sind nicht betroffen.

#### <a name="change-description"></a>Änderungsbeschreibung

Vor ASP.NET Core 3.0 konnte die Konstruktorinjektion für beliebige Typen im Konstruktor der `Startup`-Klasse verwendet werden. In ASP.NET Core 3.0 wurde der Webstapel der Bibliothek des generischen Hosts zugeordnet. Sie können die Änderung in der Datei *Program.cs*  der Vorlagen sehen:

**ASP.NET Core 2.x:**

<https://github.com/aspnet/AspNetCore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3.0:**

<https://github.com/aspnet/AspNetCore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host` verwendet einen Container zur Abhängigkeitsinjektion, um die App zu erstellen. `WebHost` verwendet zwei Container: einen für den Host und einen für die App. Daher unterstützt der `Startup`-Konstruktor keine benutzerdefinierte Dienstinjektion mehr. Es können nur `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration` eingefügt werden. Diese Änderung verhindert Probleme mit Abhängigkeitsinjektionen, z. B. die doppelte Erstellung eines Singletondiensts.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ist eine Folge der geänderten Zuordnung des Webstapels zur Bibliothek des generischen Hosts.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Fügen Sie Dienste in die Signatur der `Startup.Configure`-Methode ein. Beispiel:

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
