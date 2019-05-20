---
title: Untersuchen benutzerdefinierter Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff
description: Erfahren Sie, wie Sie Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff von Grund auf neu implementieren können, um mögliche HTTP-Fehlerszenarios zu verarbeiten.
ms.date: 10/16/2018
ms.openlocfilehash: 2b40b73a014faa87d4eb42192c72b5a9b6c8d4fa
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644730"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a>Untersuchen benutzerdefinierter Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff

Sie müssen mögliche HTTP-Fehlerszenarios verarbeiten können, um robuste Microservices zu erstellen. Eine Möglichkeit, diese Fehler zu verarbeiten, die jedoch nicht empfohlen wird, ist das Erstellen einer eigenen Implementierung von Wiederholungen mit exponentiellem Backoff.

**Wichtiger Hinweis**: In diesem Abschnitt wird veranschaulicht, wie Sie benutzerdefinierten Code erstellen können, um Wiederholungen von HTTP-Aufrufen zu implementieren. Es wird jedoch nicht empfohlen, dies selbst durchzuführen. Verwenden Sie leistungsfähigere und zuverlässigere Mechanismen wie `HttpClientFactory` mit Polly (verfügbar seit .NET Core 2.1), die zudem einfacher anzuwenden sind. Die empfohlenen Vorgehensweisen werden im nächsten Abschnitt beschrieben.

Zunächst können Sie eigenen Code wie in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) mit einer Hilfsklasse für exponentielle Backoffs sowie Code implementieren, der Folgendem entspricht.

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

Das Verwenden dieses Codes in einer C\#-Clientanwendung (in einem Web-API-Clientmicroservice, einer ASP.NET MVC-Anwendung oder sogar in einer C\#-Xamarin-Anwendung) ist einfach. Dies wird im folgenden Beispiel anhand der HttpClient-Klasse dargestellt.

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

Bedenken Sie jedoch, dass dieser Code nur als Proof of Concept geeignet ist. Im nächsten Abschnitt wird erklärt, wie Sie optimierte und einfachere Ansätze (z.B. HttpClientFactory) verwenden können. HttpClientFactory ist seit .NET Core 2.1 verfügbar und enthält bewährte stabile Bibliotheken wie Polly.

>[!div class="step-by-step"]
>[Zurück](implement-resilient-entity-framework-core-sql-connections.md)
>[Weiter](use-httpclientfactory-to-implement-resilient-http-requests.md)
