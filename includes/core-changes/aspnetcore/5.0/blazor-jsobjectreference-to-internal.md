---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077591"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="cad0d-101">Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert</span><span class="sxs-lookup"><span data-stu-id="cad0d-101">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="cad0d-102">Die neuen Typen `Microsoft.JSInterop.JSObjectReference` und `Microsoft.JSInterop.JSInProcessObjectReference`, die in ASP.NET Core 5.0 RC1 eingeführt wurden, wurden als `internal` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="cad0d-102">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cad0d-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="cad0d-103">Version introduced</span></span>

<span data-ttu-id="cad0d-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="cad0d-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cad0d-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="cad0d-105">Old behavior</span></span>

<span data-ttu-id="cad0d-106">`JSObjectReference` kann über `IJSRuntime` über einen JavaScript-Interop-Befehl abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cad0d-106">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="cad0d-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cad0d-107">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a><span data-ttu-id="cad0d-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="cad0d-108">New behavior</span></span>

<span data-ttu-id="cad0d-109">`JSObjectReference` verwendet den Zugriffsmodifizierer [internal](../../../../docs/csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="cad0d-109">`JSObjectReference` uses the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="cad0d-110">Stattdessen muss die `public` `IJSObjectReference`-Schnittstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cad0d-110">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="cad0d-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cad0d-111">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="cad0d-112">`JSInProcessObjectReference` wurde ebenfalls als `internal` gekennzeichnet und durch `IJSInProcessObjectReference` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="cad0d-112">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cad0d-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="cad0d-113">Reason for change</span></span>

<span data-ttu-id="cad0d-114">Durch die Änderung wird das JavaScript-Interop-Feature mit anderen Mustern in Blazor vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="cad0d-114">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="cad0d-115">`IJSObjectReference` ist analog zu `IJSRuntime`, da beide Objekte einen ähnlichen Zweck erfüllen und ähnliche Methoden und Erweiterung umfassen.</span><span class="sxs-lookup"><span data-stu-id="cad0d-115">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cad0d-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="cad0d-116">Recommended action</span></span>

<span data-ttu-id="cad0d-117">Ersetzen Sie `JSObjectReference` durch `IJSObjectReference` und `JSInProcessObjectReference` durch `IJSInProcessObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="cad0d-117">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

#### <a name="category"></a><span data-ttu-id="cad0d-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="cad0d-118">Category</span></span>

<span data-ttu-id="cad0d-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cad0d-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cad0d-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cad0d-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
