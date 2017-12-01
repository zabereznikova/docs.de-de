---
title: Implementieren von HTTP-Aufruf Wiederholungen mit exponenzieller mit Polly
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren von HTTP-Aufruf Wiederholungen mit exponenzieller mit Polly"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1ed48142546403ea710f4c132e038521232c20ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Implementieren von HTTP-Aufruf Wiederholungen mit exponenzieller mit Polly

Die empfohlene Vorgehensweise für Wiederholungen mit exponenzieller Wartezeit ist erweiterte .NET Bibliotheken wie der open Source nutzen [Polly](https://github.com/App-vNext/Polly) Bibliothek.

Polly ist eine .NET-Bibliothek, die Flexibilität und Behandlung vorübergehender Fehler Funktionen bereitstellt. Sie können diese Funktionen durch Anwenden von Richtlinien Polly, z. B. versuchen Sie es erneut, Trennschalter sein Isolation, Timeout und Fallback problemlos implementieren. Polly Ziel .NET 4.x und das .NET Standard Version 1.0 (der .NET Core unterstützt).

Die wiederholungsrichtlinie in Polly ist der Ansatz in eShopOnContainers verwendet, wenn HTTP-Wiederholungsversuche implementieren. Sie können eine Schnittstelle implementieren, damit Sie einfügen können, Standardfunktionen für "HttpClient" oder eine robuste Version von "HttpClient" mithilfe von Polly, je nachdem welche wiederholen-Richtlinienkonfiguration, die Sie verwenden möchten.

Das folgende Beispiel zeigt die Schnittstelle, die in eShopOnContainers implementiert.

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

Sie können die Standardimplementierung verwenden, wenn Sie nicht als einen robusten Mechanismus verwenden, beim Entwickeln oder einfacher Ansätze testen möchten. Der folgende Code zeigt die standardmäßigen "HttpClient" Implementierung ermöglichen-Anforderungen mit Authentifizierungstoken als ein optionaler Fall.

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

Die interessante Implementierung besteht darin, code mit Polly die robusten Mechanismen, implementieren Sie verwenden möchten, jedoch ein anderes, ähnliches-Klasse – im folgenden Beispiel Wiederholungen mit exponenzieller Wartezeit.

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

Mit Polly definieren Sie eine wiederholungsrichtlinie mit der Anzahl der Wiederholungen, die exponentielle Backoff-Konfiguration und die Aktionen an, wenn eine HTTP-Ausnahme, wie die Protokollierung des Fehlers aufgetreten ist. In diesem Fall wird die Richtlinie konfiguriert, damit die Anzahl der Male, die beim Registrieren von Typen in den IoC-Container angegeben versucht wird. Aufgrund der exponentiellen Backoff-Konfiguration Wenn der Code eine Ausnahme HttpRequest erkennt erneute Versuche durchgeführt die HTTP-Anforderung nach einer Wartezeit von eine Zeitspanne, die sich exponentiell zu, je nachdem, wie die Richtlinie konfiguriert wurde.

Wichtige Methode ist HttpInvoker, was ist der HTTP-Anforderungen in der gesamten diese hilfsprogrammmklasse. Dass die Methode intern ausgeführt, wird die HTTP-Anforderung mit \_policyWrapper.ExecuteAsync, die die wiederholungsrichtlinie berücksichtigt.

Im eShopOnContainers Geben Sie Polly Richtlinien beim Registrieren der Typen auf IoC-Container, wie im folgenden Code aus der [MVC-Web-app auf die startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) Klasse.

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

Beachten Sie, dass die IHttpClient Objekte als Singleton statt als vorübergehend instanziiert werden, sodass TCP-Verbindungen effizient vom Dienst verwendet werden und [ein Problem mit Sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) erfolgt nicht.

Jedoch über die Stabilität der wichtige Punkt ist, dass Sie die Richtlinie Polly WaitAndRetryAsync in ResilientHttpClientFactory in der Methode CreateResilientHttpClient anwenden, wie im folgenden Code gezeigt:

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
[Vorherigen] (Implement-custom-http-call-retries-exponential-backoff.md) [weiter] (implementieren-Circuit-Breaker-pattern.md)
