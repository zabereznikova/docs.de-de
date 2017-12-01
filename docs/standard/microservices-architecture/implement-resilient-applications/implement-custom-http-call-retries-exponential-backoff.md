---
title: Implementieren von benutzerdefinierten HTTP-Aufruf Wiederholungen mit exponenzieller Wartezeit
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren von benutzerdefinierten HTTP-Aufruf Wiederholungen mit exponenzieller Wartezeit"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4449e5d7e0ca3c81aead26fac653de3ba2187a92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a>Implementieren von benutzerdefinierten HTTP-Aufruf Wiederholungen mit exponenzieller Wartezeit

Um robusten Microservices zu erstellen, müssen Sie mögliche Szenarien der HTTP-Fehler zu behandeln. Sie könnten zu diesem Zweck eine eigene Implementierung von Wiederholungen mit exponenzieller erstellen.

Neben der Handhabung von temporale Ressource nicht verfügbar sind, muss exponentielle Backoff auch berücksichtigen, dass Cloudanbieter Verfügbarkeit der Ressourcen, um zu verhindern, dass bei der Verwendung Überladung einschränken kann. Beispielsweise zu viele verbindungsanforderungen sehr schnell erstellen möglicherweise angezeigt werden als ein Denial-of-Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) Angriff von Cloud-Dienstanbieter. Daher müssen Sie bieten einen Mechanismus zur Back verbindungsanforderungen zu skalieren, wenn ein Schwellenwert für die Kapazität erreicht wurde.

Als eine erste Untersuchungen durchzuführen, konnte Sie Ihren eigenen Code eine Dienstprogrammklasse für Exponentielles Backoff wie in implementieren [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), sowie Code wie den folgenden (steht auch auf eine [GitHub-Repository ](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

Verwenden diesen Code in einem Client C\# Anwendung (Microservice von einer anderen Web-API-Client, eine ASP.NET MVC-Anwendung oder sogar eine C\# Xamarin-Anwendung) ist einfach. Das folgende Beispiel zeigt, mit der HttpClient-Klasse.

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

Dieser Code ist jedoch nur als ein Proof of Concept geeignet ist. Im nächste Thema wird erläutert, wie mehr hochentwickelte und bewährte Bibliotheken verwendet wird.


>[!div class="step-by-step"]
[Vorherigen] (Implement-resilient-entity-framework-core-sql-connections.md) [weiter] (Implement-http-call-retries-exponential-backoff-polly.md)
