---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391181"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="b1148-101">Statische Dateien: CSV-Inhaltstyp in standardkonform geändert</span><span class="sxs-lookup"><span data-stu-id="b1148-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="b1148-102">In ASP.NET Core 5.0 wurde der von der [Middleware für statische Dateien ](/aspnet/core/fundamentals/static-files) verwendete Standardwert des `Content-Type`-Antwortheaders für *CSV*-Dateien in den standardkonformen Wert `text/csv` geändert.</span><span class="sxs-lookup"><span data-stu-id="b1148-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="b1148-103">Dieses Problem wird unter [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385) behandelt.</span><span class="sxs-lookup"><span data-stu-id="b1148-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b1148-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b1148-104">Version introduced</span></span>

<span data-ttu-id="b1148-105">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="b1148-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b1148-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="b1148-106">Old behavior</span></span>

<span data-ttu-id="b1148-107">Es wurde der `Content-Type`-Headerwert `application/octet-stream` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1148-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b1148-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="b1148-108">New behavior</span></span>

<span data-ttu-id="b1148-109">Es wird der `Content-Type`-Headerwert `text/csv` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1148-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b1148-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b1148-110">Reason for change</span></span>

<span data-ttu-id="b1148-111">Konformität mit dem [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1)-Standard.</span><span class="sxs-lookup"><span data-stu-id="b1148-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b1148-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="b1148-112">Recommended action</span></span>

<span data-ttu-id="b1148-113">Wenn sich diese Änderung auf Ihre App auswirkt, können Sie die Zuordnung von Dateierweiterungen zu MIME-Typen anpassen.</span><span class="sxs-lookup"><span data-stu-id="b1148-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="b1148-114">Um wieder den MIME-Typ `application/octet-stream` zu verwenden, ändern Sie den <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A>-Methodenaufruf in `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b1148-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="b1148-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b1148-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="b1148-116">Weitere Informationen zum Anpassen der Zuordnung finden Sie unter [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span><span class="sxs-lookup"><span data-stu-id="b1148-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="b1148-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b1148-117">Category</span></span>

<span data-ttu-id="b1148-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b1148-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b1148-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b1148-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
