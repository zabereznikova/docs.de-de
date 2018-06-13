---
title: Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 66ac57fc824e01f96d6584ab86bb95ba1b0174a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576980"
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly

Für Wiederholungen mit exponentiellem Backoff wird empfohlen, fortgeschrittenere .NET-Bibliotheken wie die Open Source-Bibliothek [Polly](https://github.com/App-vNext/Polly) zu verwenden.

Polly ist eine .NET-Bibliothek, die Funktionen für die Flexibilität und die Behandlung von vorübergehenden Fehlern bereitstellt. Sie können diese Funktionen einfach implementieren, indem Sie Polly-Richtlinien wie „Retry“, „Circuit Breaker“, „Bulkhead Isolation“, „Timeout“, und „Fallback“ anwenden. Polly ist auf .NET 4.x und die Version 1.0 von .NET Standard (die .NET Core unterstützt) ausgelegt.

In Polly wird die Richtlinie „Retry“ in „eShopOnContainers“ verwendet, um HTTP-Wiederholungsversuche zu implementieren. Sie können eine Schnittstelle implementieren, damit Sie eine Standardfunktion von „HttpClient“ oder eine robuste Version von „HttpClient“ mithilfe von Polly injizieren können, je nach der gewünschten Konfiguration der Wiederholungsrichtlinie.

Das folgende Beispiel zeigt die implementierte Schnittstelle in „eShopOnContainers“.

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

Sie können die Standardimplementierung verwenden, wenn Sie keinen robusten Mechanismus verwenden möchten, z.B. wenn Sie einfachere Ansätze entwickeln oder testen. Der folgende Code zeigt die Standardimplementierung von „HttpClient“, was Anforderungen mit Authentifizierungstokens als optionaler Fall ermöglicht.

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

Die interessante Implementierung besteht darin, eine weitere ähnliche Klasse zu codieren, aber Polly zu verwenden, um die robusten Mechanismen zu implementieren, die Sie verwenden möchten. Im folgenden Beispiel sind das Wiederholungen mit exponentiellem Backoff.

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

Mit Polly definieren Sie eine Wiederholungsrichtlinie mit der Anzahl an Wiederholungen, der Konfiguration des exponentiellen Backoffs und den Aktionen, die ausgeführt werden, wenn eine HTTP-Ausnahme ausgelöst wird, z.B. die Protokollierung des Fehlers. In diesem Fall ist die Richtlinie so konfiguriert, dass sie den Versuch so oft wie angegeben wiederholt, wenn die Typen im IoC-Container registriert werden. Wegen der Konfiguration des exponentiellen Backoffs werden HTTP-Anforderungen nach einer bestimmten Zeit wiederholt, wenn der Code eine HttpRequest-Ausnahme erkennt. Die Anzahl der Wiederholungen steigt exponentiell an, je nachdem, wie die Richtlinie konfiguriert wurde.

Die wichtige Methode ist „HttpInvoker“, die die HTTP-Anforderungen in dieser gesamten Hilfsprogrammklasse stellt. Diese Methode führt die HTTP-Anforderung mit \_policyWrapper.ExecuteAsync aus, wobei die Wiederholungsrichtlinie berücksichtigt wird.

In „eShopOnContainers“ geben Sie wie im folgenden Code aus der [MVC-Web-App in der startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs)-Klasse Polly-Richtlinien an, wenn die Typen im IoC-Container registriert werden.

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

Beachten Sie, dass die IHttpClient-Objekte als Singleton instanziiert sind und nicht als vorübergehend, sodass TCP-Verbindungen effizient von dem Dienst genutzt werden und kein [Problem mit Sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) auftritt.

Der wichtige Punkt zur Flexibilität ist, dass Sie die Polly-Richtlinie „WaitAndRetryAsync“ innerhalb von „ResilientHttpClientFactory“ in der Methode „CreateResilientHttpClient“ anwenden. Dies wird im folgenden Code dargestellt:

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
[Zurück] (implement-custom-http-call-retries-exponential-backoff.md) [Weiter] (implement-circuit-breaker-pattern.md)
