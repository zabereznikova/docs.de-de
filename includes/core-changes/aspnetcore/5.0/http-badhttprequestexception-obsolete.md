---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507082"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="4e780-101">HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt</span><span class="sxs-lookup"><span data-stu-id="4e780-101">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="4e780-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` wurden als veraltet markiert und so geändert, dass sie von `Microsoft.AspNetCore.Http.BadHttpRequestException` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4e780-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="4e780-103">Die Kestrel- und IIS-Server lösen die alten Ausnahmetypen aus Gründen der Abwärtskompatibilität weiterhin aus.</span><span class="sxs-lookup"><span data-stu-id="4e780-103">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="4e780-104">Die veralteten Typen werden in einem zukünftigen Release entfernt.</span><span class="sxs-lookup"><span data-stu-id="4e780-104">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="4e780-105">Weitere Informationen finden Sie unter [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="4e780-105">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4e780-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4e780-106">Version introduced</span></span>

<span data-ttu-id="4e780-107">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="4e780-107">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4e780-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="4e780-108">Old behavior</span></span>

<span data-ttu-id="4e780-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` werden von <xref:System.IO.IOException?displayProperty=nameWithType> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e780-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4e780-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="4e780-110">New behavior</span></span>

<span data-ttu-id="4e780-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="4e780-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="4e780-112">Werttypen werden von der `Microsoft.AspNetCore.Http.BadHttpRequestException`-Klasse abgeleitet, die wiederum von `System.IO.IOException` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="4e780-112">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4e780-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="4e780-113">Reason for change</span></span>

<span data-ttu-id="4e780-114">Die Änderung wurde aus folgenden Gründen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="4e780-114">The change was made to:</span></span>

* <span data-ttu-id="4e780-115">zur Konsolidierung duplizierter Typen</span><span class="sxs-lookup"><span data-stu-id="4e780-115">Consolidate duplicate types.</span></span>
* <span data-ttu-id="4e780-116">zur Vereinheitlichen des Verhaltens von Serverimplementierungen</span><span class="sxs-lookup"><span data-stu-id="4e780-116">Unify behavior across server implementations.</span></span>

<span data-ttu-id="4e780-117">damit Apps die Standardausnahme `Microsoft.AspNetCore.Http.BadHttpRequestException` abfangen können, wenn Kestrel oder IIS verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4e780-117">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4e780-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="4e780-118">Recommended action</span></span>

<span data-ttu-id="4e780-119">Ersetzen Sie die Instanzen von `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` durch `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="4e780-119">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

#### <a name="category"></a><span data-ttu-id="4e780-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4e780-120">Category</span></span>

<span data-ttu-id="4e780-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4e780-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e780-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4e780-122">Affected APIs</span></span>

- [<span data-ttu-id="4e780-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="4e780-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="4e780-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="4e780-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
