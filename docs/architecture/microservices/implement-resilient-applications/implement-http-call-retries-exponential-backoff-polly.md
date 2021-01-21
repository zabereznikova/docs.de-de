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
# <a name="implement-http-call-retries-with-exponential-backoff-with-ihttpclientfactory-and-polly-policies"></a>Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit IHttpClientFactory und Polly-Richtlinien

Für Wiederholungen mit exponentiellem Backoff wird empfohlen, fortgeschrittenere .NET-Bibliotheken wie die Open Source-Bibliothek [Polly](https://github.com/App-vNext/Polly) zu verwenden.

Polly ist eine .NET-Bibliothek, die Funktionen für die Flexibilität und die Behandlung von vorübergehenden Fehlern bereitstellt. Sie können diese Funktionen implementieren, indem Sie Polly-Richtlinien wie „Retry“, „Circuit Breaker“, „Bulkhead Isolation“, „Timeout“, und „Fallback“ anwenden. Polly unterstützt .NET Framework 4.x und .NET Standard 1.0, 1.1 und 2.0 (unterstützt .NET Core und höher).

Die folgenden Schritte veranschaulichen, wie Sie HTTP-Wiederholungen mit Polly in `IHttpClientFactory` verwenden können. Die Integration von Polly wird im vorherigen Abschnitt erläutert.

**Verweisen auf die ASP.NET Core 3.1-Pakete**

`IHttpClientFactory` ist seit .NET Core 2.1 verfügbar. Wir empfehlen jedoch die Verwendung der neuesten ASP.NET Core 3.1-Pakete auf NuGet in Ihrem Projekt. In der Regel müssen Sie auch auf das Erweiterungspaket `Microsoft.Extensions.Http.Polly` verweisen.

**Konfigurieren eines Clients mit der Wiederholungsrichtlinie von Polly in der Startup-Klasse**

Wie in den vorherigen Abschnitten beschrieben wurde, müssen Sie eine benannte oder typisierte HttpClient-Clientkonfiguration in Ihrer Startup.ConfigureServices(...)-Standardmethode definieren. Nun fügen Sie jedoch inkrementellen Code hinzu, der die Richtlinie für die HTTP-Wiederholungen mit exponentiellem Backoff angibt:

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

Durch die Methode **AddPolicyHandler()** werden Richtlinien zu `HttpClient`-Objekten hinzugefügt, die Sie verwenden werden. In diesem Fall wird eine Richtlinie von Polly für HTTP-Wiederholungen mit exponentiellem Backoff hinzugefügt.

Für einen modulareren Ansatz kann die HTTP-Wiederholungsrichtlinie in einer separaten Methode innerhalb der `Startup.cs`-Datei definiert werden. Dies wird im folgenden Code veranschaulicht:

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

Mit Polly können Sie eine Wiederholungsrichtlinie definieren, die die Anzahl von Wiederholungen, die Konfiguration des exponentiellen Backoffs und die Aktionen enthält, die ausgeführt werden, wenn eine HTTP-Ausnahme ausgelöst wird, z.B. die Protokollierung des Fehlers. In diesem Fall ist die Richtlinie dafür konfiguriert, sechs Versuche mit einer exponentiellen Wiederholung durchzuführen, die bei zwei Sekunden beginnt.

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a>Hinzufügen einer Jitterstrategie zur Wiederholungsrichtlinie

Eine reguläre Wiederholungsrichtlinie kann ein System negativ beeinflussen, falls hohe Parallelität, hohe Skalierbarkeit und ein hohes Konfliktpotenzial vorhanden sind. Um mit Spitzenlasten umgehen zu können, die bei ähnlichen Wiederholungsanforderungen von vielen Clients bei einem Teilausfall auftreten, empfiehlt es sich als Notlösung, den Wiederholungsalgorithmus oder die Wiederholungsrichtlinie um eine Jitterstrategie zu ergänzen. Wenn für den exponentiellen Backoff der Jitter zufällig festgelegt wird, kann dies die Gesamtleistung des End-to-End-Systems verbessern. Dadurch lassen sich beim Auftreten von Problemen Lastspitzen verteilen. Das Prinzip wird im folgenden Beispiel dargestellt:

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

Polly stellt über die Projektwebsite produktionsreife Jitteralgorithmen zur Verfügung.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Wiederholungsmuster**  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- **Polly und IHttpClientFactory**  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- **Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**  
  <https://github.com/App-vNext/Polly>

- **Polly: Wiederholen mit Jitter**  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- **Marc Brooker. Jitter: Making Things Better With Randomness** (Marc Brooker. Jitter: Dinge durch Zufall verbessern)  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
>[Zurück](use-httpclientfactory-to-implement-resilient-http-requests.md)
>[Weiter](implement-circuit-breaker-pattern.md)
