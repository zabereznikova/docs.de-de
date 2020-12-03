---
title: 'Breaking Change: HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759421"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="cad3d-103">HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt</span><span class="sxs-lookup"><span data-stu-id="cad3d-103">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="cad3d-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` wurden als veraltet markiert und so geändert, dass sie von `Microsoft.AspNetCore.Http.BadHttpRequestException` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cad3d-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="cad3d-105">Die Kestrel- und IIS-Server lösen die alten Ausnahmetypen aus Gründen der Abwärtskompatibilität weiterhin aus.</span><span class="sxs-lookup"><span data-stu-id="cad3d-105">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="cad3d-106">Die veralteten Typen werden in einem zukünftigen Release entfernt.</span><span class="sxs-lookup"><span data-stu-id="cad3d-106">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="cad3d-107">Weitere Informationen finden Sie unter [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="cad3d-107">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cad3d-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="cad3d-108">Version introduced</span></span>

<span data-ttu-id="cad3d-109">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="cad3d-109">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="cad3d-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="cad3d-110">Old behavior</span></span>

<span data-ttu-id="cad3d-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` werden von <xref:System.IO.IOException?displayProperty=nameWithType> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="cad3d-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="cad3d-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="cad3d-112">New behavior</span></span>

<span data-ttu-id="cad3d-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="cad3d-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="cad3d-114">Werttypen werden von der `Microsoft.AspNetCore.Http.BadHttpRequestException`-Klasse abgeleitet, die wiederum von `System.IO.IOException` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="cad3d-114">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="cad3d-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="cad3d-115">Reason for change</span></span>

<span data-ttu-id="cad3d-116">Die Änderung wurde aus folgenden Gründen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="cad3d-116">The change was made to:</span></span>

* <span data-ttu-id="cad3d-117">zur Konsolidierung duplizierter Typen</span><span class="sxs-lookup"><span data-stu-id="cad3d-117">Consolidate duplicate types.</span></span>
* <span data-ttu-id="cad3d-118">zur Vereinheitlichen des Verhaltens von Serverimplementierungen</span><span class="sxs-lookup"><span data-stu-id="cad3d-118">Unify behavior across server implementations.</span></span>

<span data-ttu-id="cad3d-119">damit Apps die Standardausnahme `Microsoft.AspNetCore.Http.BadHttpRequestException` abfangen können, wenn Kestrel oder IIS verwendet werden</span><span class="sxs-lookup"><span data-stu-id="cad3d-119">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="cad3d-120">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="cad3d-120">Recommended action</span></span>

<span data-ttu-id="cad3d-121">Ersetzen Sie die Instanzen von `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` durch `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="cad3d-121">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="cad3d-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cad3d-122">Affected APIs</span></span>

- [<span data-ttu-id="cad3d-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="cad3d-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="cad3d-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="cad3d-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
