---
title: Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly
description: Erfahren Sie, wie Sie HTTP-Fehler mit Polly und HttpClientFactory verarbeiten können.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 07333b84896c223f076e9c36cc90ab7ea7ac37c7
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465723"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a><span data-ttu-id="ad7fb-103">Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit HttpClientFactory und Polly-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ad7fb-103">Implement HTTP call retries with exponential backoff with HttpClientFactory and Polly policies</span></span>

<span data-ttu-id="ad7fb-104">Für Wiederholungen mit exponentiellem Backoff wird empfohlen, fortgeschrittenere .NET-Bibliotheken wie die Open Source-Bibliothek [Polly](https://github.com/App-vNext/Polly) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="ad7fb-105">Polly ist eine .NET-Bibliothek, die Funktionen für die Flexibilität und die Behandlung von vorübergehenden Fehlern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="ad7fb-106">Sie können diese Funktionen implementieren, indem Sie Polly-Richtlinien wie „Retry“, „Circuit Breaker“, „Bulkhead Isolation“, „Timeout“, und „Fallback“ anwenden.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="ad7fb-107">Polly ist auf .NET 4.x und die .NET Standard-Bibliothek 1.0 (die .NET Core unterstützt) ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-107">Polly targets .NET 4.x and the .NET Standard Library 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="ad7fb-108">Die Verwendung der Polly-Bibliothek mit eigenem benutzerdefinierten Code mit HttpClient kann sich jedoch sehr komplex gestalten.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-108">However, using Polly’s library with your own custom code with HttpClient can be significantly complex.</span></span> <span data-ttu-id="ad7fb-109">In der ursprünglichen Version von eShopOnContainers war der Baustein [ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) enthalten, der auf Polly basierte.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-109">In the original version of eShopOnContainers, there was a [ResilientHttpClient building-block](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) based on Polly.</span></span> <span data-ttu-id="ad7fb-110">Mit dem Release von HttpClientFactory wurde die Implementierung von robuster HTTP-Kommunikation wesentlich einfacher, sodass dieser Baustein von eShopOnContainers nun als veraltet gilt.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-110">But with the release of HttpClientFactory, resilient Http communication has become much simpler to implement, so that building-block was deprecated from eShopOnContainers.</span></span> 

<span data-ttu-id="ad7fb-111">Die folgenden Schritte veranschaulichen, wie Sie HTTP-Wiederholungen mit Polly in HttpClientFactory verwenden können. Die Integration von Polly wird im vorherigen Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-111">The following steps show how you can use Http retries with Polly integrated into HttpClientFactory, which is explained in the previous section.</span></span>

<span data-ttu-id="ad7fb-112">**Verweisen auf die ASP.NET Core 2.2-Pakete**</span><span class="sxs-lookup"><span data-stu-id="ad7fb-112">**Reference the ASP.NET Core 2.2 packages**</span></span>

<span data-ttu-id="ad7fb-113">`HttpClientFactory` ist seit .NET Core 2.1 verfügbar. Wir empfehlen jedoch die Verwendung der aktuellsten ASP.NET Core 2.2-Pakete von NuGet in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-113">`HttpClientFactory` is available since .NET Core 2.1 however we recommend you to use the latest ASP.NET Core 2.2 packages from NuGet in your project.</span></span> <span data-ttu-id="ad7fb-114">Sie benötigen üblicherweise das Metapaket `AspNetCore` und das Erweiterungspaket `Microsoft.Extensions.Http.Polly`.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-114">You typically need the `AspNetCore` metapackage, and the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="ad7fb-115">**Konfigurieren eines Clients mit der Polly-Wiederholungsrichtlinie in der Startup-Klasse**</span><span class="sxs-lookup"><span data-stu-id="ad7fb-115">**Configure a client with Polly’s Retry policy, in Startup**</span></span>

<span data-ttu-id="ad7fb-116">Wie in den vorherigen Abschnitten beschrieben wurde, müssen Sie eine benannte oder typisierte HttpClient-Clientkonfiguration in Ihrer Startup.ConfigureServices(...)-Standardmethode definieren. Nun fügen Sie jedoch inkrementellen Code hinzu, der die Richtlinie für die HTTP-Wiederholungen mit exponentiellem Backoff angibt:</span><span class="sxs-lookup"><span data-stu-id="ad7fb-116">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="ad7fb-117">Durch die Methode **AddPolicyHandler()** werden Richtlinien zu `HttpClient`-Objekten hinzugefügt, die Sie verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-117">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="ad7fb-118">In diesem Fall wird eine Polly-Richtlinie für HTTP-Wiederholungen mit exponentiellem Backoff hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-118">In this case, it's adding a Polly’s policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="ad7fb-119">Für einen modulareren Ansatz kann die HTTP-Wiederholungsrichtlinie in einer separaten Methode innerhalb der `Startup.cs`-Datei definiert werden. Dies wird im folgenden Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ad7fb-119">To have a more modular approach, the Http Retry Policy can be defined in a separate method within the `Startup.cs` file, as shown in the following code:</span></span>

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

<span data-ttu-id="ad7fb-120">Mit Polly können Sie eine Wiederholungsrichtlinie definieren, die die Anzahl von Wiederholungen, die Konfiguration des exponentiellen Backoffs und die Aktionen enthält, die ausgeführt werden, wenn eine HTTP-Ausnahme ausgelöst wird, z.B. die Protokollierung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-120">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there's an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="ad7fb-121">In diesem Fall ist die Richtlinie dafür konfiguriert, sechs Versuche mit einer exponentiellen Wiederholung durchzuführen, die bei zwei Sekunden beginnt.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-121">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span> 

<span data-ttu-id="ad7fb-122">Es werden also sechs Versuche durchgeführt, und die Sekunden zwischen jeder Wiederholung steigen beginnend bei zwei Sekunden exponentiell.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-122">so it will try six times and the seconds between each retry will be exponential, starting on two seconds.</span></span>

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="ad7fb-123">Hinzufügen einer Jitterstrategie zur Wiederholungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ad7fb-123">Add a jitter strategy to the retry policy</span></span>

<span data-ttu-id="ad7fb-124">Eine reguläre Wiederholungsrichtlinie kann ein System negativ beeinflussen, falls hohe Parallelität, hohe Skalierbarkeit und ein hohes Konfliktpotenzial vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-124">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="ad7fb-125">Um mit Spitzenlasten umgehen zu können, die bei ähnlichen Wiederholungsanforderungen von vielen Clients bei einem Teilausfall auftreten, empfiehlt es sich als Notlösung, den Wiederholungsalgorithmus oder die Wiederholungsrichtlinie um eine Jitterstrategie zu ergänzen.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-125">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="ad7fb-126">Wenn für den exponentiellen Backoff der Jitter zufällig festgelegt wird, kann dies die Gesamtleistung des End-to-End-Systems verbessern.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-126">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="ad7fb-127">Dadurch lassen sich beim Auftreten von Problemen Lastspitzen verteilen.</span><span class="sxs-lookup"><span data-stu-id="ad7fb-127">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="ad7fb-128">Wenn Sie eine einfache Polly-Richtlinie verwenden, könnte der Code zum Implementieren des Jitters wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ad7fb-128">When you use a plain Polly policy, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a><span data-ttu-id="ad7fb-129">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ad7fb-129">Additional resources</span></span>

- <span data-ttu-id="ad7fb-130">**Wiederholungsmuster**\\</span><span class="sxs-lookup"><span data-stu-id="ad7fb-130">**Retry pattern**\\</span></span>
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- <span data-ttu-id="ad7fb-131">**Polly und HttpClientFactory**\\</span><span class="sxs-lookup"><span data-stu-id="ad7fb-131">**Polly and HttpClientFactory**\\</span></span>
  [https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)

- <span data-ttu-id="ad7fb-132">**Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**\\</span><span class="sxs-lookup"><span data-stu-id="ad7fb-132">**Polly (.NET resilience and transient-fault-handling library)**\\</span></span>
  [https://github.com/App-vNext/Polly](https://github.com/App-vNext/Polly)

- <span data-ttu-id="ad7fb-133">**Marc Brooker. Jitter: Dinge durch Zufall verbessern**\\</span><span class="sxs-lookup"><span data-stu-id="ad7fb-133">**Marc Brooker. Jitter: Making Things Better With Randomness**\\</span></span>
  [https://brooker.co.za/blog/2015/03/21/backoff.html](https://brooker.co.za/blog/2015/03/21/backoff.html)

>[!div class="step-by-step"]
><span data-ttu-id="ad7fb-134">[Zurück](explore-custom-http-call-retries-exponential-backoff.md)
>[Weiter](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="ad7fb-134">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>