---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391181"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>Statische Dateien: CSV-Inhaltstyp in standardkonform geändert

In ASP.NET Core 5.0 wurde der von der [Middleware für statische Dateien ](/aspnet/core/fundamentals/static-files) verwendete Standardwert des `Content-Type`-Antwortheaders für *CSV*-Dateien in den standardkonformen Wert `text/csv` geändert.

Dieses Problem wird unter [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385) behandelt.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

#### <a name="old-behavior"></a>Altes Verhalten

Es wurde der `Content-Type`-Headerwert `application/octet-stream` verwendet.

#### <a name="new-behavior"></a>Neues Verhalten

Es wird der `Content-Type`-Headerwert `text/csv` verwendet.

#### <a name="reason-for-change"></a>Grund für die Änderung

Konformität mit dem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1)-Standard.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn sich diese Änderung auf Ihre App auswirkt, können Sie die Zuordnung von Dateierweiterungen zu MIME-Typen anpassen. Um wieder den MIME-Typ `application/octet-stream` zu verwenden, ändern Sie den <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A>-Methodenaufruf in `Startup.Configure`. Zum Beispiel:

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

Weitere Informationen zum Anpassen der Zuordnung finden Sie unter [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
