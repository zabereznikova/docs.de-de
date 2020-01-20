---
ms.openlocfilehash: 53d2c989120c92f4e2d18f50ce4b364bd4c9b604
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902033"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="fc5aa-101">HTTP: Synchrones E/A auf allen Servern deaktiviert</span><span class="sxs-lookup"><span data-stu-id="fc5aa-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="fc5aa-102">Ab ASP.NET Core 3.0 sind synchrone Servervorgänge standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fc5aa-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="fc5aa-103">Change description</span></span>

<span data-ttu-id="fc5aa-104">`AllowSynchronousIO` ist eine Option auf sämtlichen Servern, die synchrone E/A-APIs wie `HttpRequest.Body.Read`, `HttpResponse.Body.Write` und `Stream.Flush` aktiviert bzw. deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="fc5aa-105">Diese APIs waren schon länger Ursache für fehlende Threads und hängende Apps.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="fc5aa-106">Ab ASP.NET Core 3.0 Preview 3 sind diese synchronen Vorgänge standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="fc5aa-107">Betroffene Server:</span><span class="sxs-lookup"><span data-stu-id="fc5aa-107">Affected servers:</span></span>

- <span data-ttu-id="fc5aa-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="fc5aa-108">Kestrel</span></span>
- <span data-ttu-id="fc5aa-109">HttpSys</span><span class="sxs-lookup"><span data-stu-id="fc5aa-109">HttpSys</span></span>
- <span data-ttu-id="fc5aa-110">IIS In-Process</span><span class="sxs-lookup"><span data-stu-id="fc5aa-110">IIS in-process</span></span>
- <span data-ttu-id="fc5aa-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="fc5aa-111">TestServer</span></span>

<span data-ttu-id="fc5aa-112">Erwartbare Fehler:</span><span class="sxs-lookup"><span data-stu-id="fc5aa-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="fc5aa-113">Jeder Server verfügt über eine `AllowSynchronousIO`-Option, die dieses Verhalten steuert und nun standardmäßig `false` ist.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="fc5aa-114">Das Verhalten kann auch auf Anforderung als vorübergehende Entschärfung überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="fc5aa-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fc5aa-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="fc5aa-116">Wenn Sie Probleme mit einem `TextWriter` oder einem anderen Stream haben, der eine synchrone API in `Dispose` aufruft, rufen Sie stattdessen die neue `DisposeAsync`-API auf.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="fc5aa-117">Weitere Informationen finden Sie unter [dotnet/aspnetcore#7644](https://github.com/dotnet/aspnetcore/issues/7644).</span><span class="sxs-lookup"><span data-stu-id="fc5aa-117">For discussion, see [dotnet/aspnetcore#7644](https://github.com/dotnet/aspnetcore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fc5aa-118">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="fc5aa-118">Version introduced</span></span>

<span data-ttu-id="fc5aa-119">3.0</span><span class="sxs-lookup"><span data-stu-id="fc5aa-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="fc5aa-120">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="fc5aa-120">Old behavior</span></span>

<span data-ttu-id="fc5aa-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write` und `Stream.Flush` waren standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="fc5aa-122">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="fc5aa-122">New behavior</span></span>

<span data-ttu-id="fc5aa-123">Diese synchronen APIs sind nun standardmäßig nicht mehr zulässig:</span><span class="sxs-lookup"><span data-stu-id="fc5aa-123">These synchronous APIs are disallowed by default:</span></span>

<span data-ttu-id="fc5aa-124">Erwartbare Fehler:</span><span class="sxs-lookup"><span data-stu-id="fc5aa-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="fc5aa-125">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="fc5aa-125">Reason for change</span></span>

<span data-ttu-id="fc5aa-126">Diese synchronen APIs waren schon länger Ursache für fehlende Threads und hängende Apps.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="fc5aa-127">Ab ASP.NET Core 3.0 Preview 3 sind synchrone Vorgänge standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fc5aa-128">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="fc5aa-128">Recommended action</span></span>

<span data-ttu-id="fc5aa-129">Verwenden Sie die asynchronen Versionen der Methoden.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="fc5aa-130">Das Verhalten kann auch auf Anforderung als vorübergehende Entschärfung überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fc5aa-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="fc5aa-131">Kategorie</span><span class="sxs-lookup"><span data-stu-id="fc5aa-131">Category</span></span>

<span data-ttu-id="fc5aa-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fc5aa-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fc5aa-133">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fc5aa-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
