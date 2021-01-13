---
title: 'Breaking Change: Blazor: Änderungen der Routinglogik in Blazor-Apps'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Änderungen der Routinglogik in Blazor-Apps'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513506"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a><span data-ttu-id="2ec09-103">Blazor: Logik für die Routingrangfolge in Blazor-Apps geändert</span><span class="sxs-lookup"><span data-stu-id="2ec09-103">Blazor: Route precedence logic changed in Blazor apps</span></span>

<span data-ttu-id="2ec09-104">Ein Fehler in der Blazor-Routingimplementierung hat die Bestimmung der Rangfolge von Routen beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="2ec09-104">A bug in the Blazor routing implementation affected how the precedence of routes was determined.</span></span> <span data-ttu-id="2ec09-105">Dieser Fehler betraf Catch-All-Routen oder Routen mit optionalen Parametern in Blazor-Apps.</span><span class="sxs-lookup"><span data-stu-id="2ec09-105">This bug affects catch-all routes or routes with optional parameters within your Blazor app.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2ec09-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2ec09-106">Version introduced</span></span>

<span data-ttu-id="2ec09-107">5.0.1</span><span class="sxs-lookup"><span data-stu-id="2ec09-107">5.0.1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="2ec09-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="2ec09-108">Old behavior</span></span>

<span data-ttu-id="2ec09-109">Durch das fehlerhafte Verhalten werden Routen mit niedrigerem Rang gegenüber Routen mit höherem Rang bevorzugt berücksichtigt und abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="2ec09-109">With the erroneous behavior, routes with lower precedence are considered and matched over routes with higher precedence.</span></span> <span data-ttu-id="2ec09-110">Beispielsweise wird die Route `{*slug}` vor `/customer/{id}` abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="2ec09-110">For example, the `{*slug}` route is matched before `/customer/{id}`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="2ec09-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="2ec09-111">New behavior</span></span>

<span data-ttu-id="2ec09-112">Das aktuelle Verhalten stimmt stärker mit dem Routingverhalten überein, das in ASP.NET Core-Apps definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2ec09-112">The current behavior more closely matches the routing behavior defined in ASP.NET Core apps.</span></span> <span data-ttu-id="2ec09-113">Das Framework bestimmt zuerst die Rangfolge der Routen für die einzelnen Segmente.</span><span class="sxs-lookup"><span data-stu-id="2ec09-113">The framework determines the route precedence for each segment first.</span></span> <span data-ttu-id="2ec09-114">Die Länge der Route wird nur als zweites Kriterium verwendet, wenn zwei Routen denselben Rang haben.</span><span class="sxs-lookup"><span data-stu-id="2ec09-114">The route's length is used only as a second criteria to break ties.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2ec09-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="2ec09-115">Reason for change</span></span>

<span data-ttu-id="2ec09-116">Das ursprüngliche Verhalten wird in der Implementierung als Fehler betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2ec09-116">The original behavior is considered a bug in the implementation.</span></span> <span data-ttu-id="2ec09-117">Ziel ist es, dass sich das Routingsystem in Blazor-Apps genauso verhält wie im Rest von ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2ec09-117">As a goal, the routing system in Blazor apps should behave the same way as the routing system in the rest of ASP.NET Core.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2ec09-118">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="2ec09-118">Recommended action</span></span>

<span data-ttu-id="2ec09-119">Wenn Sie ein Upgrade von früheren Versionen von Blazor auf Version 5.x durchführen, sollten Sie das Attribut `PreferExactMatches` für die Komponente `Router` verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ec09-119">If upgrading from previous versions of Blazor to 5.x, use the `PreferExactMatches` attribute on the `Router` component.</span></span> <span data-ttu-id="2ec09-120">Dieses Attribut kann verwendet werden, um das richtige Verhalten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2ec09-120">This attribute can be used to opt into the correct behavior.</span></span> <span data-ttu-id="2ec09-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ec09-121">For example:</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

<span data-ttu-id="2ec09-122">Wenn `PreferExactMatches` auf `true` festgelegt ist, bevorzugt die Routenzuordnung exakte Übereinstimmungen gegenüber Platzhaltern.</span><span class="sxs-lookup"><span data-stu-id="2ec09-122">When `PreferExactMatches` is set to `true`, route matching prefers exact matches over wildcards.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2ec09-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2ec09-123">Affected APIs</span></span>

<span data-ttu-id="2ec09-124">Keine</span><span class="sxs-lookup"><span data-stu-id="2ec09-124">None</span></span>

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
