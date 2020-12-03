---
title: 'Breaking Change: IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759202"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="b84aa-103">IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten</span><span class="sxs-lookup"><span data-stu-id="b84aa-103">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="b84aa-104">Ein Fehler bei der IIS-UrlRewrite-Middleware hat verhindert, dass die Abfragezeichenfolge in Neuschreibungsregeln beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="b84aa-104">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="b84aa-105">Dieser Fehler wurde behoben, um Konsistenz mit dem Verhalten des IIS-UrlRewrite-Moduls sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b84aa-105">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="b84aa-106">Weitere Informationen finden Sie im Issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="b84aa-106">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b84aa-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b84aa-107">Version introduced</span></span>

<span data-ttu-id="b84aa-108">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="b84aa-108">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b84aa-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="b84aa-109">Old behavior</span></span>

<span data-ttu-id="b84aa-110">Sehen Sie sich die folgende Neuschreibungsregel an:</span><span class="sxs-lookup"><span data-stu-id="b84aa-110">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="b84aa-111">Die obige Regel fügt die Abfragezeichenfolge nicht an.</span><span class="sxs-lookup"><span data-stu-id="b84aa-111">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="b84aa-112">Bei einem URI wie `/about?id=1` findet eine Weiterleitung zu `/contact` anstelle von `/contact?id=1` statt.</span><span class="sxs-lookup"><span data-stu-id="b84aa-112">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="b84aa-113">Außerdem ist das Attribut `appendQueryString` standardmäßig auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b84aa-113">The `appendQueryString` attribute defaults to `true` as well.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="b84aa-114">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="b84aa-114">New behavior</span></span>

<span data-ttu-id="b84aa-115">Die Abfragezeichenfolge wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b84aa-115">The query string is preserved.</span></span> <span data-ttu-id="b84aa-116">Der URI aus dem Beispiel unter [Altes Verhalten](#old-behavior) wäre dann `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="b84aa-116">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b84aa-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b84aa-117">Reason for change</span></span>

<span data-ttu-id="b84aa-118">Das alte Verhalten entsprach nicht dem des IIS-UrlRewrite-Moduls.</span><span class="sxs-lookup"><span data-stu-id="b84aa-118">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="b84aa-119">Damit ein Übertragen zwischen Middleware und Modul unterstützt wird, soll ein konsistentes Verhalten gewährleistet sein.</span><span class="sxs-lookup"><span data-stu-id="b84aa-119">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b84aa-120">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="b84aa-120">Recommended action</span></span>

<span data-ttu-id="b84aa-121">Wenn Sie das Entfernen der Abfragezeichenfolge als Verhalten bevorzugen, legen Sie im `action`-Element `appendQueryString="false"` fest.</span><span class="sxs-lookup"><span data-stu-id="b84aa-121">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b84aa-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b84aa-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
