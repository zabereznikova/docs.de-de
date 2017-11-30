---
title: Implementieren einen Trennschalter
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren einen Trennschalter"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a>Implementieren einen Trennschalter

Wie bereits erwähnt, sollten Sie Fehler behandeln, die in Anspruch eine Variable Menge an Zeit nehmen können aus, der wiederhergestellt werden soll, wie möglicherweise auftreten, wenn Sie versuchen, eine Verbindung mit einer remote-Dienst oder eine Ressource. Diese Art von Fehler zu behandeln, kann die Stabilität und Stabilität von einer Anwendung verbessern.

In einer verteilten Umgebung können Aufrufe von remote-Ressourcen und Dienste zu einem Fehler aufgrund von vorübergehenden Fehlern, z. B. langsame Verbindungen und Timeouts verursacht, oder wenn Ressourcen werden langsam oder vorübergehend nicht verfügbar sind. Diese Fehler korrigieren selbst in der Regel nach kurzer Zeit ein, und eine robusten Cloud-Anwendung zu deren Behandlung durch eine Strategie wie die Wiederholung (Muster) vorbereitet werden soll.

Allerdings möglich gibt es auch Situationen, in denen Fehler aufgrund unerwarteter Ereignisse sind, die beheben wesentlich länger dauern. Diese Fehler können in Schweregrad aus einem teilweise Verlust der Verbindung abgeschlossen bei Ausfall eines Diensts im Bereich. In diesen Situationen ist es möglicherweise nicht sinnvoll, damit eine Anwendung ständig einen Vorgang zu wiederholen, der wahrscheinlich nicht erfolgreich ist. Stattdessen sollte die Anwendung codiert werden, um annehmen, dass der Vorgang fehlgeschlagen ist und den Fehler entsprechend zu behandeln.

Einen Trennschalter wurde einen anderen Zweck als die Wiederholung (Muster). Die Wiederholung (Muster) kann eine Anwendung einen Vorgang in der Annahme zu wiederholen, die der Vorgang schließlich erfolgreich sein wird. Einen Trennschalter verhindert, dass eine Anwendung eine Operation aus, die vermutlich fehlschlägt. Eine Anwendung kann diese beiden Muster mithilfe des Wiederholungsmusters, das zum Aufrufen eines Vorgangs über ein Trennschalter kombinieren. Allerdings sollte die Wiederholungslogik für alle Ausnahmen, die von der Trennschalter zurückgegeben werden, und es sollte Wiederholungsversuche verwerfen, wenn der Trennschalter gibt an, dass ein Problem nicht vorübergehend ist.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Implementieren eine einen Trennschalter mit Polly

Wie bei der Implementierung von Wiederholungen die empfohlene Vorgehensweise für Trennschalter ist bewährte .NET Bibliotheken wie Polly nutzen.

Die eShopOnContainers-Anwendung verwendet die Polly Circuit-Breaker-Richtlinie aus, bei der Implementierung von HTTP-Wiederholungsversuchen. In der Tat gilt die Anwendung beide Richtlinien für die ResilientHttpClient Utility-Klasse. Wenn Sie ein Objekt des Typs ResilientHttpClient für HTTP-Anforderungen (von eShopOnContainers) verwenden, Sie werden sowohl diese Richtlinien anwenden, jedoch zusätzliche Richtlinien konnte zu hinzugefügt werden.

Die einzige zusätzliche auf den Code für Wiederholungen für HTTP-Aufrufs verwendet ist der Code, in dem Sie das Circuit-Breaker Richtlinie hinzufügen zur Liste der Richtlinien zu verwenden, wie am Ende den folgenden Code gezeigt:

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

Der Code Fügt eine Richtlinie an den HTTP-Wrapper. Übergeben, dass die Richtlinie definiert ein Trennschalter, das geöffnet wird, wenn der Code die angegebene Anzahl von aufeinander folgenden Ausnahmen (Ausnahmen in einer Zeile), erkennt als im Parameters ExceptionsAllowedBeforeBreaking (5 in diesem Fall). Wenn die Verbindung geöffnet ist, HTTP-Anforderungen nicht funktionsfähig, aber eine Ausnahme ausgelöst.

Trennschalter sollte auch verwendet werden, um Anforderungen zu einer fallback-Infrastruktur umzuleiten, haben möglicherweise Probleme in eine bestimmte Ressource, die in einer anderen Umgebung als der Clientanwendung bereitgestellt wird oder einen Dienst, der den HTTP-Aufruf ausführt. Auf diese Weise ist es ein Ausfall im Datencenter, der nur die Back-End-Microservices jedoch nicht Ihre Clientanwendungen angewendet, wirkt sich auf die können die Clientanwendungen fallback Dienste umleiten. Plant eine neue Richtlinie aus, um dies zu automatisieren Polly [Failoverrichtlinie](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) Szenario.

Alle diese Funktionen sind natürlich für Fälle, in dem Sie das Failover aus, in der .NET Code, anstatt sie automatisch für Sie von Azure verwaltet wird, mit Speicherorttransparenz verwalten.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Verwenden die Hilfsprogrammklasse ResilientHttpClient aus eShopOnContainers

Sie verwenden die Hilfsprogrammklasse ResilientHttpClient, ähnlich wie die .NET HttpClient-Klasse verwenden. Im folgenden Beispiel von der eShopOnContainers MVC-Webanwendung (OrderingService Agent-Klasse von OrderController verwendet) wird das Objekt ResilientHttpClient über den "HttpClient"-Parameter des Konstruktors eingefügt. Anschließend wird das Objekt zum Ausführen von HTTP-Anforderungen verwendet.

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

Wenn die \_ApiClient Member-Objekt verwendet wird, verwendet intern die Wrapperklasse mit Polly Policiesؙ – die wiederholungsrichtlinie der Trennschalter-Richtlinie und alle anderen Richtlinien, die aus der Auflistung der Polly-Richtlinien angewendet werden sollen.

## <a name="testing-retries-in-eshoponcontainers"></a>Testen von Wiederholungen in eShopOnContainers

Sobald Sie die eShopOnContainers-Lösung in einem Docker-Host starten, muss er mehrere Container zu starten. Einige der Container werden langsamer starten und zu initialisieren, wie die SQL Server-Container. Dies gilt insbesondere, beim ersten der Anwendung eShopOnContainers in Docker bereitstellen, da er die Images und die Datenbank einrichten muss. Die Tatsache, dass die einige Container langsamer als die andere den Rest der Dienste für anfänglich HTTP-Ausnahmen auslösen, verursachen können, selbst wenn Sie festlegen, dass Abhängigkeiten zwischen Containern am start der Docker-verfassen Ebene, wie in vorherigen Abschnitten beschrieben. Die Docker-verfassen Abhängigkeiten zwischen Containern sind nur auf der Prozessebene. Des Containers Eintrag Punkt Prozess gestartet werden kann, aber SQL Server möglicherweise nicht für Abfragen bereit. Das Ergebnis einer Cascade von Fehlern werden kann, und die Anwendung kann eine Ausnahme abgerufen, beim Versuch, diesen Container nutzen.

Diese Art von Fehlern beim Start möglicherweise auch angezeigt werden, wenn die Anwendung in der Cloud bereitgestellt wird. In diesem Fall Orchestrators möglicherweise werden Container von einem Knoten oder virtuellen Computer in einen anderen verschieben (die neue Instanzen gestartet wird,), wenn die Anzahl der Container über die Cluster-Knoten hinweg Lastenausgleich.

Die Möglichkeit, die eShopOnContainers dieses Problem gelöst ist mithilfe des Wiederholungsmusters, das die wir zuvor veranschaulicht. Es ist auch an, warum, wenn Sie die Projektmappe zu starten, ablaufverfolgungen oder Warnungen wie folgt auftreten können:

> "**Wiederholung 1 implementiert, mit Pollys RetryPolicy**, da: System.Net.Http.HttpRequestException: beim Senden der Anforderung ist ein Fehler aufgetreten. ---&gt;System.Net.Http.CurlException: Konnte keine Verbindung mit Server herstellen\\am System.Net.Http.CurlHandler.ThrowIfCURLEError (CURLcode Fehler) n\\am n \[... \].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Testen der Trennschalter in eShopOnContainers

Es gibt mehrere Möglichkeiten, Sie können die Verbindung zu öffnen und mit eShopOnContainers zu testen.

Eine Möglichkeit besteht darin senken Sie die zulässige Anzahl von Wiederholungen auf 1 in der Trennschalter Richtlinie und stellen Sie die gesamte Lösung in Docker. Klicken Sie mit einem einzelnen Neuversuch besteht eine hohe Wahrscheinlichkeit, die eine HTTP-Anforderung während der Bereitstellung fehl, der Trennschalter wird geöffnet, und Sie erhalten eine Fehlermeldung.

Eine andere Möglichkeit ist die Verwendung von benutzerdefinierten Middleware, die in der Reihenfolge Microservice implementiert wird. Wenn diese Middleware aktiviert ist, fängt Sie alle HTTP-Anforderungen ab und gibt den Statuscode 500 zurück. Sie können die Middleware aktivieren, indem Sie eine GET-Anforderung an der fehlerhaften URI wie folgt:

-   GET/fehlschlagen

Diese Anforderung gibt den aktuellen Status der Middleware zurück. Wenn die Middleware aktiviert ist, die Anforderung den Statuscode 500 zurück. Wenn die Middleware deaktiviert ist, ist es jedoch keine Antwort.

-   GET/fehlschlägt? aktivieren

Diese Anforderung aktiviert die Middleware.

-   GET/fehlschlägt? deaktivieren

Diese Anforderung wird die Middleware deaktiviert.

Sobald die Anwendung ausgeführt wird, können Sie die Middleware aktivieren, indem Sie eine Anforderung mit den folgenden URI in einen beliebigen Browser. Beachten Sie, dass die Sortierung Microservice Port 5102 verwendet.

Http://localhost:5102 / fehlschlägt? aktivieren

Sie können dann überprüfen Sie den Status mit dem URI [Http://localhost:5102 / fehlschlagen](http://localhost:5100/failing), wie in Abbildung 10 – 4 dargestellt.

![](./media/image4.png)

**Abbildung 10 – 4**. Einen Fehler mit ASP.NET Middleware simulieren

An diesem Punkt Aufrufen der Reihenfolge Microservice antwortet mit dem Statuscode 500 bei jedem Aufruf sie.

Sobald die Middleware ausgeführt wird, können Sie versuchen, eine Bestellung von der MVC-Webanwendung vornehmen. Da die Anforderungen ein Fehler auftritt, wird die Verbindung geöffnet.

Im folgenden Beispiel sehen Sie, dass die MVC-Webanwendung einen Catch weist in der Logik zum Platzieren einer Bestellung zu blockieren. Wenn der Code eine Open-Circuit-Ausnahme abfängt, wird dem Benutzer eine benutzerfreundliche Meldung informiert wird gewartet.

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

Hier ist eine Zusammenfassung. Die wiederholungsrichtlinie versucht, mehrere Male die HTTP-Anforderung und ruft HTTP-Fehler. Wenn die Anzahl der Versuche, die maximale Anzahl Satz für die Richtlinie "Circuit-Breaker" (in diesem Fall 5) erreicht, löst die Anwendung eine BrokenCircuitException an. Das Ergebnis ist eine benutzerfreundliche Meldung an, wie in Abbildung 10 – 5 gezeigt.

![](./media/image5.png)

**Abbildung 10 – 5**. Trennschalter ein Fehler zurückgegeben, in die Benutzeroberfläche.

Sie können eine unterschiedliche Logik für den Fall, öffnen Sie die Verbindung implementieren. Oder Sie können eine HTTP-Anforderung für einen anderen Back-End-Microservice versuchen, ob ein fallback Datacenter oder redundante Back-End-System vorliegt.

Schließlich ist eine weitere Möglichkeit für die CircuitBreakerPolicy isolieren (der erzwingt öffnen und die Verbindung geöffnet hält) und zurückgesetzt (Dies schließt erneut) zu verwenden. Diese können verwendet werden, einen Hilfsprogramm HTTP-Endpunkt zu erstellen, der isoliert und Zurücksetzen der direkt auf die Richtlinie aufruft. Solche ein HTTP-Endpunkt kann auch verwendet werden entsprechend geschützt werden, in der Produktion vorübergehend isolieren ein downstreamsystem, z. B. wenn das Upgrade ausgeführt werden sollen. Oder es konnte die Verbindung manuell, um ein downstreamsystem schützen Sie vermuten, werden fehlgeschlagene auslöst.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Die wiederholungsrichtlinie für hinzugefügt eine Strategie jitter

Eine reguläre wiederholungsrichtlinie kann Ihr System in Fällen hoher Parallelität und Skalierbarkeit und unter hohes konfliktpotenzial auswirken. Um Spitzen ähnliche Wiederholungen, die von vielen Clients bei einem teilweise Ausfälle zu vermeiden, ist eine gute Lösung eine Strategie für die Jitter an die wiederholungsrichtlinie/Algorithmus hinzufügen. Dies kann die gesamtleistung des Systems End-to-End-verbessern, indem Exponentielles Backoff hinsichtlich Ihrer Zufälligkeit hinzugefügt. Dies ausbreitet die Spitzen beim Auftreten von Problemen. Wenn Sie Polly verwenden, kann Code zum Implementieren von Jitter wie im folgenden Beispiel aussehen:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Wiederholen Sie die Muster**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Verbindungsresilienz** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (.NET Stabilität und vorübergehend fehlerverarbeitung Bibliothek) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Einen Trennschalter**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker. Jitter: Macht es besser mit Zufälligkeit** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Vorherigen] (Implement-http-call-retries-exponential-backoff-polly.md) [weiter] (Monitor-app-health.md)
