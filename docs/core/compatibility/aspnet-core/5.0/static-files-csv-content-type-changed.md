---
title: 'Breaking Change: Statische Dateien: CSV-Inhaltstyp in standardkonform geändert'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Statische Dateien: CSV-Inhaltstyp in standardkonform geändert'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c94a0cf213970d20559b7c061d8be220b43961e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759560"
---
# <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>Statische Dateien: CSV-Inhaltstyp in standardkonform geändert

In ASP.NET Core 5.0 wurde der von der [Middleware für statische Dateien](/aspnet/core/fundamentals/static-files) verwendete Standardwert des `Content-Type`-Antwortheaders für *CSV*-Dateien in den standardkonformen Wert `text/csv` geändert.

Dieses Problem wird unter [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385) behandelt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

## <a name="old-behavior"></a>Altes Verhalten

Es wurde der `Content-Type`-Headerwert `application/octet-stream` verwendet.

## <a name="new-behavior"></a>Neues Verhalten

Es wird der `Content-Type`-Headerwert `text/csv` verwendet.

## <a name="reason-for-change"></a>Grund für die Änderung

Konformität mit dem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1)-Standard.

## <a name="recommended-action"></a>Empfohlene Aktion

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

## <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
