---
title: Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly
description: Erfahren Sie, wie Sie HTTP-Fehler mit Polly und IHttpClientFactory verarbeiten können.
ms.date: 01/13/2021
ms.openlocfilehash: 8cffc644d73eaec5019e00c6a83de8635b569cde
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189049"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-ihttpclientfactory-and-polly-policies"></a><span data-ttu-id="fa8c2-103">Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit IHttpClientFactory und Polly-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="fa8c2-103">Implement HTTP call retries with exponential backoff with IHttpClientFactory and Polly policies</span></span>

<span data-ttu-id="fa8c2-104">Für Wiederholungen mit exponentiellem Backoff wird empfohlen, fortgeschrittenere .NET-Bibliotheken wie die Open Source-Bibliothek [Polly](https://github.com/App-vNext/Polly) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="fa8c2-105">Polly ist eine .NET-Bibliothek, die Funktionen für die Flexibilität und die Behandlung von vorübergehenden Fehlern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="fa8c2-106">Sie können diese Funktionen implementieren, indem Sie Polly-Richtlinien wie „Retry“, „Circuit Breaker“, „Bulkhead Isolation“, „Timeout“, und „Fallback“ anwenden.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="fa8c2-107">Polly unterstützt .NET Framework 4.x und .NET Standard 1.0, 1.1 und 2.0 (unterstützt .NET Core und höher).</span><span class="sxs-lookup"><span data-stu-id="fa8c2-107">Polly targets .NET Framework 4.x and .NET Standard 1.0, 1.1, and 2.0 (which supports .NET Core and later).</span></span>

<span data-ttu-id="fa8c2-108">Die folgenden Schritte veranschaulichen, wie Sie HTTP-Wiederholungen mit Polly in `IHttpClientFactory` verwenden können. Die Integration von Polly wird im vorherigen Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-108">The following steps show how you can use Http retries with Polly integrated into `IHttpClientFactory`, which is explained in the previous section.</span></span>

<span data-ttu-id="fa8c2-109">**Verweisen auf die ASP.NET Core 3.1-Pakete**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-109">**Reference the ASP.NET Core 3.1 packages**</span></span>

<span data-ttu-id="fa8c2-110">`IHttpClientFactory` ist seit .NET Core 2.1 verfügbar. Wir empfehlen jedoch die Verwendung der neuesten ASP.NET Core 3.1-Pakete auf NuGet in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-110">`IHttpClientFactory` is available since .NET Core 2.1 however we recommend you to use the latest ASP.NET Core 3.1 packages from NuGet in your project.</span></span> <span data-ttu-id="fa8c2-111">In der Regel müssen Sie auch auf das Erweiterungspaket `Microsoft.Extensions.Http.Polly` verweisen.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-111">You typically also need to reference the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="fa8c2-112">**Konfigurieren eines Clients mit der Wiederholungsrichtlinie von Polly in der Startup-Klasse**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-112">**Configure a client with Polly's Retry policy, in Startup**</span></span>

<span data-ttu-id="fa8c2-113">Wie in den vorherigen Abschnitten beschrieben wurde, müssen Sie eine benannte oder typisierte HttpClient-Clientkonfiguration in Ihrer Startup.ConfigureServices(...)-Standardmethode definieren. Nun fügen Sie jedoch inkrementellen Code hinzu, der die Richtlinie für die HTTP-Wiederholungen mit exponentiellem Backoff angibt:</span><span class="sxs-lookup"><span data-stu-id="fa8c2-113">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="fa8c2-114">Durch die Methode **AddPolicyHandler()** werden Richtlinien zu `HttpClient`-Objekten hinzugefügt, die Sie verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-114">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="fa8c2-115">In diesem Fall wird eine Richtlinie von Polly für HTTP-Wiederholungen mit exponentiellem Backoff hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-115">In this case, it's adding a Polly's policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="fa8c2-116">Für einen modulareren Ansatz kann die HTTP-Wiederholungsrichtlinie in einer separaten Methode innerhalb der `Startup.cs`-Datei definiert werden. Dies wird im folgenden Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fa8c2-116">To have a more modular approach, the Http Retry Policy can be defined in a separate method within the `Startup.cs` file, as shown in the following code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

<span data-ttu-id="fa8c2-117">Mit Polly können Sie eine Wiederholungsrichtlinie definieren, die die Anzahl von Wiederholungen, die Konfiguration des exponentiellen Backoffs und die Aktionen enthält, die ausgeführt werden, wenn eine HTTP-Ausnahme ausgelöst wird, z.B. die Protokollierung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-117">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there's an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="fa8c2-118">In diesem Fall ist die Richtlinie dafür konfiguriert, sechs Versuche mit einer exponentiellen Wiederholung durchzuführen, die bei zwei Sekunden beginnt.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-118">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span>

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="fa8c2-119">Hinzufügen einer Jitterstrategie zur Wiederholungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="fa8c2-119">Add a jitter strategy to the retry policy</span></span>

<span data-ttu-id="fa8c2-120">Eine reguläre Wiederholungsrichtlinie kann ein System negativ beeinflussen, falls hohe Parallelität, hohe Skalierbarkeit und ein hohes Konfliktpotenzial vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-120">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="fa8c2-121">Um mit Spitzenlasten umgehen zu können, die bei ähnlichen Wiederholungsanforderungen von vielen Clients bei einem Teilausfall auftreten, empfiehlt es sich als Notlösung, den Wiederholungsalgorithmus oder die Wiederholungsrichtlinie um eine Jitterstrategie zu ergänzen.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-121">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="fa8c2-122">Wenn für den exponentiellen Backoff der Jitter zufällig festgelegt wird, kann dies die Gesamtleistung des End-to-End-Systems verbessern.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-122">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="fa8c2-123">Dadurch lassen sich beim Auftreten von Problemen Lastspitzen verteilen.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-123">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="fa8c2-124">Das Prinzip wird im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="fa8c2-124">The principle is illustrated by the following example:</span></span>

```csharp
Random jitterer = new Random();
var retryWithJitterPolicy = HttpPolicyExtensions
    .HandleTransientHttpError()
    .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
    .WaitAndRetryAsync(6,    // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                      + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

<span data-ttu-id="fa8c2-125">Polly stellt über die Projektwebsite produktionsreife Jitteralgorithmen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-125">Polly provides production-ready jitter algorithms via the project website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa8c2-126">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fa8c2-126">Additional resources</span></span>

- <span data-ttu-id="fa8c2-127">**Wiederholungsmuster**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-127">**Retry pattern**</span></span>  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- <span data-ttu-id="fa8c2-128">**Polly und IHttpClientFactory**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-128">**Polly and IHttpClientFactory**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- <span data-ttu-id="fa8c2-129">**Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-129">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <https://github.com/App-vNext/Polly>

- <span data-ttu-id="fa8c2-130">**Polly: Wiederholen mit Jitter**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-130">**Polly: Retry with Jitter**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- <span data-ttu-id="fa8c2-131">**Marc Brooker. Jitter: Making Things Better With Randomness** (Marc Brooker. Jitter: Dinge durch Zufall verbessern)</span><span class="sxs-lookup"><span data-stu-id="fa8c2-131">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
><span data-ttu-id="fa8c2-132">[Zurück](use-httpclientfactory-to-implement-resilient-http-requests.md)
>[Weiter](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="fa8c2-132">[Previous](use-httpclientfactory-to-implement-resilient-http-requests.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
