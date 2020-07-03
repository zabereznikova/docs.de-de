---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325247"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="02b46-101">IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten</span><span class="sxs-lookup"><span data-stu-id="02b46-101">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="02b46-102">Ein Fehler bei der IIS-UrlRewrite-Middleware hat verhindert, dass die Abfragezeichenfolge in Neuschreibungsregeln beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="02b46-102">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="02b46-103">Dieser Fehler wurde behoben, um Konsistenz mit dem Verhalten des IIS-UrlRewrite-Moduls sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="02b46-103">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="02b46-104">Weitere Informationen finden Sie im Issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="02b46-104">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="02b46-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="02b46-105">Version introduced</span></span>

<span data-ttu-id="02b46-106">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="02b46-106">ASP.NET Core 5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="02b46-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="02b46-107">Old behavior</span></span>

<span data-ttu-id="02b46-108">Sehen Sie sich die folgende Neuschreibungsregel an:</span><span class="sxs-lookup"><span data-stu-id="02b46-108">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="02b46-109">Die obige Regel fügt die Abfragezeichenfolge nicht an.</span><span class="sxs-lookup"><span data-stu-id="02b46-109">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="02b46-110">Bei einem URI wie `/about?id=1` findet eine Weiterleitung zu `/contact` anstelle von `/contact?id=1` statt.</span><span class="sxs-lookup"><span data-stu-id="02b46-110">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="02b46-111">Außerdem ist das Attribut `appendQueryString` standardmäßig auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="02b46-111">The `appendQueryString` attribute defaults to `true` as well.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="02b46-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="02b46-112">New behavior</span></span>

<span data-ttu-id="02b46-113">Die Abfragezeichenfolge wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="02b46-113">The query string is preserved.</span></span> <span data-ttu-id="02b46-114">Der URI aus dem Beispiel unter [Altes Verhalten](#old-behavior) wäre dann `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="02b46-114">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="02b46-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="02b46-115">Reason for change</span></span>

<span data-ttu-id="02b46-116">Das alte Verhalten entsprach nicht dem des IIS-UrlRewrite-Moduls.</span><span class="sxs-lookup"><span data-stu-id="02b46-116">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="02b46-117">Damit ein Übertragen zwischen Middleware und Modul unterstützt wird, soll ein konsistentes Verhalten gewährleistet sein.</span><span class="sxs-lookup"><span data-stu-id="02b46-117">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02b46-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="02b46-118">Recommended action</span></span>

<span data-ttu-id="02b46-119">Wenn Sie das Entfernen der Abfragezeichenfolge als Verhalten bevorzugen, legen Sie im `action`-Element `appendQueryString="false"` fest.</span><span class="sxs-lookup"><span data-stu-id="02b46-119">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

#### <a name="category"></a><span data-ttu-id="02b46-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="02b46-120">Category</span></span>

<span data-ttu-id="02b46-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02b46-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02b46-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="02b46-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
