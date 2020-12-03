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
# <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="80fd7-103">Statische Dateien: CSV-Inhaltstyp in standardkonform geändert</span><span class="sxs-lookup"><span data-stu-id="80fd7-103">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="80fd7-104">In ASP.NET Core 5.0 wurde der von der [Middleware für statische Dateien](/aspnet/core/fundamentals/static-files) verwendete Standardwert des `Content-Type`-Antwortheaders für *CSV*-Dateien in den standardkonformen Wert `text/csv` geändert.</span><span class="sxs-lookup"><span data-stu-id="80fd7-104">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="80fd7-105">Dieses Problem wird unter [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385) behandelt.</span><span class="sxs-lookup"><span data-stu-id="80fd7-105">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="80fd7-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="80fd7-106">Version introduced</span></span>

<span data-ttu-id="80fd7-107">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="80fd7-107">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="80fd7-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="80fd7-108">Old behavior</span></span>

<span data-ttu-id="80fd7-109">Es wurde der `Content-Type`-Headerwert `application/octet-stream` verwendet.</span><span class="sxs-lookup"><span data-stu-id="80fd7-109">The `Content-Type` header value `application/octet-stream` was used.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="80fd7-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="80fd7-110">New behavior</span></span>

<span data-ttu-id="80fd7-111">Es wird der `Content-Type`-Headerwert `text/csv` verwendet.</span><span class="sxs-lookup"><span data-stu-id="80fd7-111">The `Content-Type` header value `text/csv` is used.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="80fd7-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="80fd7-112">Reason for change</span></span>

<span data-ttu-id="80fd7-113">Konformität mit dem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1)-Standard.</span><span class="sxs-lookup"><span data-stu-id="80fd7-113">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="80fd7-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="80fd7-114">Recommended action</span></span>

<span data-ttu-id="80fd7-115">Wenn sich diese Änderung auf Ihre App auswirkt, können Sie die Zuordnung von Dateierweiterungen zu MIME-Typen anpassen.</span><span class="sxs-lookup"><span data-stu-id="80fd7-115">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="80fd7-116">Um wieder den MIME-Typ `application/octet-stream` zu verwenden, ändern Sie den <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A>-Methodenaufruf in `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="80fd7-116">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="80fd7-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80fd7-117">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="80fd7-118">Weitere Informationen zum Anpassen der Zuordnung finden Sie unter [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="80fd7-118">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="80fd7-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="80fd7-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
