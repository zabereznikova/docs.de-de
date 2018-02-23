---
title: Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 122f617874188d3bffe689d6b3cf7d7249c59c3b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a><span data-ttu-id="8225d-104">Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly</span><span class="sxs-lookup"><span data-stu-id="8225d-104">Implementing HTTP call retries with exponential backoff with Polly</span></span>

<span data-ttu-id="8225d-105">Für Wiederholungen mit exponentiellem Backoff wird empfohlen, fortgeschrittenere .NET-Bibliotheken wie die Open Source-Bibliothek [Polly](https://github.com/App-vNext/Polly) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8225d-105">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open source [Polly](https://github.com/App-vNext/Polly) library.</span></span>

<span data-ttu-id="8225d-106">Polly ist eine .NET-Bibliothek, die Funktionen für die Flexibilität und die Behandlung von vorübergehenden Fehlern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8225d-106">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="8225d-107">Sie können diese Funktionen einfach implementieren, indem Sie Polly-Richtlinien wie „Retry“, „Circuit Breaker“, „Bulkhead Isolation“, „Timeout“, und „Fallback“ anwenden.</span><span class="sxs-lookup"><span data-stu-id="8225d-107">You can implement those capabilities easily by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="8225d-108">Polly ist auf .NET 4.x und die Version 1.0 von .NET Standard (die .NET Core unterstützt) ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="8225d-108">Polly targets .NET 4.x and the .NET Standard version 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="8225d-109">In Polly wird die Richtlinie „Retry“ in „eShopOnContainers“ verwendet, um HTTP-Wiederholungsversuche zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="8225d-109">The Retry policy in Polly is the approach used in eShopOnContainers when implementing HTTP retries.</span></span> <span data-ttu-id="8225d-110">Sie können eine Schnittstelle implementieren, damit Sie eine Standardfunktion von „HttpClient“ oder eine robuste Version von „HttpClient“ mithilfe von Polly injizieren können, je nach der gewünschten Konfiguration der Wiederholungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="8225d-110">You can implement an interface so you can inject either standard HttpClient functionality or a resilient version of HttpClient using Polly, depending on what retry policy configuration you want to use.</span></span>

<span data-ttu-id="8225d-111">Das folgende Beispiel zeigt die implementierte Schnittstelle in „eShopOnContainers“.</span><span class="sxs-lookup"><span data-stu-id="8225d-111">The following example shows the interface implemented in eShopOnContainers.</span></span>

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

<span data-ttu-id="8225d-112">Sie können die Standardimplementierung verwenden, wenn Sie keinen robusten Mechanismus verwenden möchten, z.B. wenn Sie einfachere Ansätze entwickeln oder testen.</span><span class="sxs-lookup"><span data-stu-id="8225d-112">You can use the standard implementation if you do not want to use a resilient mechanism, as when you are developing or testing simpler approaches.</span></span> <span data-ttu-id="8225d-113">Der folgende Code zeigt die Standardimplementierung von „HttpClient“, was Anforderungen mit Authentifizierungstokens als optionaler Fall ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8225d-113">The following code shows the standard HttpClient implementation allowing requests with authentication tokens as an optional case.</span></span>

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

<span data-ttu-id="8225d-114">Die interessante Implementierung besteht darin, eine weitere ähnliche Klasse zu codieren, aber Polly zu verwenden, um die robusten Mechanismen zu implementieren, die Sie verwenden möchten. Im folgenden Beispiel sind das Wiederholungen mit exponentiellem Backoff.</span><span class="sxs-lookup"><span data-stu-id="8225d-114">The interesting implementation is to code another, similar class, but using Polly to implement the resilient mechanisms you want to use—in the following example, retries with exponential backoff.</span></span>

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

<span data-ttu-id="8225d-115">Mit Polly definieren Sie eine Wiederholungsrichtlinie mit der Anzahl an Wiederholungen, der Konfiguration des exponentiellen Backoffs und den Aktionen, die ausgeführt werden, wenn eine HTTP-Ausnahme ausgelöst wird, z.B. die Protokollierung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="8225d-115">With Polly, you define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="8225d-116">In diesem Fall ist die Richtlinie so konfiguriert, dass sie den Versuch so oft wie angegeben wiederholt, wenn die Typen im IoC-Container registriert werden.</span><span class="sxs-lookup"><span data-stu-id="8225d-116">In this case, the policy is configured so it will try the number of times specified when registering the types in the IoC container.</span></span> <span data-ttu-id="8225d-117">Wegen der Konfiguration des exponentiellen Backoffs werden HTTP-Anforderungen nach einer bestimmten Zeit wiederholt, wenn der Code eine HttpRequest-Ausnahme erkennt. Die Anzahl der Wiederholungen steigt exponentiell an, je nachdem, wie die Richtlinie konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="8225d-117">Because of the exponential backoff configuration, whenever the code detects an HttpRequest exception, it retries the Http request after waiting an amount of time that increases exponentially depending on how the policy was configured.</span></span>

<span data-ttu-id="8225d-118">Die wichtige Methode ist „HttpInvoker“, die die HTTP-Anforderungen in dieser gesamten Hilfsprogrammklasse stellt.</span><span class="sxs-lookup"><span data-stu-id="8225d-118">The important method is HttpInvoker, which is what makes HTTP requests throughout this utility class.</span></span> <span data-ttu-id="8225d-119">Diese Methode führt die HTTP-Anforderung mit \_policyWrapper.ExecuteAsync aus, wobei die Wiederholungsrichtlinie berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="8225d-119">That method internally executes the HTTP request with \_policyWrapper.ExecuteAsync, which takes into account the retry policy.</span></span>

<span data-ttu-id="8225d-120">In „eShopOnContainers“ geben Sie wie im folgenden Code aus der [MVC-Web-App in der startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs)-Klasse Polly-Richtlinien an, wenn die Typen im IoC-Container registriert werden.</span><span class="sxs-lookup"><span data-stu-id="8225d-120">In eShopOnContainers you specify Polly policies when registering the types at the IoC container, as in the following code from the [MVC web app at the startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) class.</span></span>

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

<span data-ttu-id="8225d-121">Beachten Sie, dass die IHttpClient-Objekte als Singleton instanziiert sind und nicht als vorübergehend, sodass TCP-Verbindungen effizient von dem Dienst genutzt werden und kein [Problem mit Sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) auftritt.</span><span class="sxs-lookup"><span data-stu-id="8225d-121">Note that the IHttpClient objects are instantiated as singleton instead of as transient so that TCP connections are used efficiently by the service and [an issue with sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) will not occur.</span></span>

<span data-ttu-id="8225d-122">Der wichtige Punkt zur Flexibilität ist, dass Sie die Polly-Richtlinie „WaitAndRetryAsync“ innerhalb von „ResilientHttpClientFactory“ in der Methode „CreateResilientHttpClient“ anwenden. Dies wird im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8225d-122">But the important point about resiliency is that you apply the Polly WaitAndRetryAsync policy within ResilientHttpClientFactory in the CreateResilientHttpClient method, as shown in the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
<span data-ttu-id="8225d-123">[Zurück] (implement-custom-http-call-retries-exponential-backoff.md) [Weiter] (implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="8225d-123">[Previous] (implement-custom-http-call-retries-exponential-backoff.md) [Next] (implement-circuit-breaker-pattern.md)</span></span>
