---
title: 'Breaking Change: Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759430"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="96874-103">Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert</span><span class="sxs-lookup"><span data-stu-id="96874-103">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="96874-104">Die neuen Typen `Microsoft.JSInterop.JSObjectReference` und `Microsoft.JSInterop.JSInProcessObjectReference`, die in ASP.NET Core 5.0 RC1 eingeführt wurden, wurden als `internal` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="96874-104">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="96874-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="96874-105">Version introduced</span></span>

<span data-ttu-id="96874-106">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="96874-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="96874-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="96874-107">Old behavior</span></span>

<span data-ttu-id="96874-108">`JSObjectReference` kann über `IJSRuntime` über einen JavaScript-Interop-Befehl abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96874-108">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="96874-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96874-109">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a><span data-ttu-id="96874-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="96874-110">New behavior</span></span>

<span data-ttu-id="96874-111">`JSObjectReference` verwendet den Zugriffsmodifizierer [internal](../../../../csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="96874-111">`JSObjectReference` uses the [internal](../../../../csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="96874-112">Stattdessen muss die `public` `IJSObjectReference`-Schnittstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96874-112">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="96874-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96874-113">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="96874-114">`JSInProcessObjectReference` wurde ebenfalls als `internal` gekennzeichnet und durch `IJSInProcessObjectReference` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="96874-114">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="96874-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="96874-115">Reason for change</span></span>

<span data-ttu-id="96874-116">Durch die Änderung wird das JavaScript-Interop-Feature mit anderen Mustern in Blazor vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="96874-116">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="96874-117">`IJSObjectReference` ist analog zu `IJSRuntime`, da beide Objekte einen ähnlichen Zweck erfüllen und ähnliche Methoden und Erweiterung umfassen.</span><span class="sxs-lookup"><span data-stu-id="96874-117">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="96874-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="96874-118">Recommended action</span></span>

<span data-ttu-id="96874-119">Ersetzen Sie `JSObjectReference` durch `IJSObjectReference` und `JSInProcessObjectReference` durch `IJSInProcessObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="96874-119">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="96874-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="96874-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
