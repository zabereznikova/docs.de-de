---
title: Implementieren des Trennschaltermusters
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren des Trennschaltermusters"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d7db6899068f84f9165022cfbf17767a75e7db9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a>Implementieren des Trennschaltermusters

Wie bereits in einem vorherigen Artikel erwähnt wurde, sollten Sie Fehler behandeln, deren Behebung unterschiedlich lange dauern kann. Dies kann beispielsweise der Fall sein, wenn Sie versuchen, sich mit einem Remote-Dienst oder einer Remote-Ressource zu verbinden. Die Behandlung derartiger Fehler kann die Stabilität und Robustheit einer Anwendung erhöhen.

In einer verteilten Umgebung können Aufrufe von Remote-Ressourcen und -Diensten fehlschlagen, wenn vorübergehende Fehler wie langsame Netzwerkverbindungen und Timeouts auftreten oder wenn Ressourcen zu langsam oder vorübergehend nicht verfügbar sind. Diese Fehler werden in der Regel nach kurzer Zeit korrigiert, und eine robuste Cloudanwendung sollte diese durch eine Strategie wie das Wiederholungsmuster behandeln können.

Es gibt jedoch auch Situationen, in denen Fehler aufgrund unerwarteter Ereignisse auftreten. Die Behebung dieser Fehler kann deutlich mehr Zeit in Anspruch nehmen. Zu unterscheiden sind unterschiedliche Schweregrade, die von einem Teilverlust der Konnektivität bis hin zum vollständigen Ausfall des Diensts reichen können. In diesen Situationen ist es möglicherweise nicht sinnvoll, wenn eine Anwendung einen Vorgang mehrfach wiederholt, der wahrscheinlich nicht erfolgreich ausgeführt werden kann. Stattdessen sollte die Anwendung so programmiert sein, dass ein fehlgeschlagener Vorgang akzeptiert und der Fehler entsprechend behandelt wird.

Das Wiederholungsmuster hat einen anderen Zweck als das Trennschaltermuster. Ersteres ermöglicht es einer Anwendung, einen Vorgang erneut auszuführen, wobei davon ausgegangen wird, dass dieser irgendwann erfolgreich sein wird. Letzteres hindert eine Anwendung daran, einen Vorgang auszuführen, der vermutlich fehlschlagen wird. Eine Anwendung kann beide Muster kombinieren, wenn sie das Wiederholungsmuster nutzt, um einen Vorgang über das Trennschaltermuster aufzurufen. Die Wiederholungslogik sollte jedoch Ausnahmen behandeln können, die eventuell von dem Trennschalter zurückgegeben werden, und auf Wiederholungsversuche verzichten, wenn durch den Trennschalter darauf hingewiesen wird, dass ein Fehler nicht vorübergehend ist.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Implementieren eines Trennschaltermusters mit Polly

Ebenso wie für die Implementierung von Wiederholungen wird auch für Trennschalter empfohlen, auf bewährte .NET-Bibliotheken wie Polly zurückzugreifen.

Die eShopOnContainers-Anwendung verwendet die Polly-Richtlinie für Trennschalter bei der Implementierung von HTTP-Wiederholungsversuchen. Tatsächlich verwendet die Anwendung sogar beide Richtlinien für die Hilfsklasse ResilientHttpClient. Wenn Sie ein Objekt des Typs ResilientHttpClient für HTTP-Anforderungen (von eShopOnContainers) nutzen, wenden Sie beide Richtlinien an. Sie könnten jedoch auch zusätzliche Richtlinien hinzufügen.

Der nachfolgende Code für Wiederholungen von HTTP-Aufrufen wird nur insofern geändert, als die Trennschalterrichtlinie der zu verwendenden Richtlinienliste hinzugefügt wird. Dies wird am Ende des folgenden Codeausschnitts gezeigt:

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

Durch den Code wird dem HTTP-Wrapper eine Richtlinie hinzugefügt. In der Richtlinie wird ein Trennschalter definiert, der sich „öffnet“, wenn der Code die vorgegebene Anzahl aufeinander folgender Ausnahmen erkennt. Die Anzahl der Ausnahmen (in diesem Fall fünf) wird als der Parameter exceptionsAllowedBeforeBreaking übergeben. Wenn der Trennschalter geöffnet ist, können keine HTTP-Anforderungen gestellt werden, und eine Ausnahme wird ausgelöst.

Trennschalter sollten auch verwendet werden, um Anforderungen an eine Fallbackinfrastruktur umzuleiten, wenn möglicherweise Probleme bei einer bestimmten Ressource auftreten, die in einer anderen Umgebung als die Clientanwendung oder der Dienst bereitgestellt wird, die/der den HTTP-Aufruf ausführt. Auf diese Weise kann die Clientanwendung bei einem Ausfall im Datencenter, der nur Back-End-Microservices, nicht aber Clientanwendungen betrifft, Anforderungen an Fallbackdienste umleiten. Für Polly wird aktuell eine Richtlinie zur Automatisierung dieses [Failoverrichtlinienszenarios](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) geplant.

Anzumerken ist, dass die erwähnten Features nur für Fälle geeignet sind, in denen das Failover mit .NET Code und nicht automatisch von Azure unter Berücksichtigung von Speicherorttransparenz verwaltet wird.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Verwenden der Hilfsklasse ResilientHttpClient aus eShopOnContainers

Die Hilfsklasse ResilientHttpClient wird ähnlich verwendet wie die .NET-Klasse HttpClient. Im folgenden Beispiel aus der eShopOnContainers-MVC-Webanwendung (der OrderingService-Agent-Klasse, die von OrderController verwendet wird) wird das ResilientHttpClient-Objekt über den httpClient-Parameter des Konstruktors eingefügt. Anschließend werden mit dem Objekt HTTP-Anforderungen gestellt.

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

Wenn das \_apiClient-Memberobjekt verwendet wird, nutzt es intern die Wrapperklasse mit der Polly-Wiederholungsrichtlinie und der Polly-Trennschalterrichtlinie. Außerdem können alle weiteren gewünschten Richtlinien der Polly-Richtlinienauflistung angewendet werden.

## <a name="testing-retries-in-eshoponcontainers"></a>Testen von Wiederholungen in eShopOnContainers

Sobald Sie die eShopOnContainers-Lösung in einem Docker-Host starten, müssen mehrere Container gestartet werden. Einige Container wie der SQL Server-Container werden langsamer gestartet und initialisiert. Dies ist v.a. dann der Fall, wenn Sie die eShopOnContainers-Anwendung zum ersten Mal in Docker bereitstellen, da die Images und die Datenbank eingerichtet werden müssen. Der langsamere Start einiger Container kann dazu führen, dass die anderen Dienste auch dann anfänglich HTTP-Ausnahmen auslösen, wenn Sie, wie in den vorherigen Abschnitten beschrieben, Abhängigkeiten zwischen Containern auf der docker-compose-Ebene festlegen. Diese docker-compose-Abhängigkeiten zwischen Containern befinden sich nur auf der Prozessebene. Auch wenn der Einstiegspunktprozess des Containers bereits gestartet wurde, ist SQL Server möglicherweise noch nicht für Abfragen bereit. Das Ergebnis können zahlreiche Fehler sein. Außerdem wird in der Anwendung möglicherweise eine Ausnahme angezeigt, wenn sie versucht, den Container zu verwenden.

Diese Art von Fehler kann auch beim Start angezeigt werden, wenn die Anwendung in der Cloud bereitgestellt wird. In diesem Fall können Orchestratoren einen Container zwischen Knoten oder virtuellen Computern hin- und herschieben (was dem Start neuer Instanzen entspricht), wenn die Anzahl der Container für Clusterknoten ausgeglichen wird.

eShopOnContainers löst dieses Problem mithilfe des Wiederholungsmusters, das bereits beschrieben wurde. Dies ist auch der Grund dafür, warum beim Start der Lösung möglicherweise Protokollablaufverfolgungen oder -warnungen wie die Folgende angezeigt werden:

> **Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request. ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\]. (Wiederholung 1 wurde mit Pollys Wiederholungsrichtlinie aus folgendem Grund implementiert: System.Net.Http.HttpRequestException: Beim Senden der Anforderung ist ein Fehler aufgetreten. System.Net.Http.CurlException: Mit dem Server\n bei System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\n konnte keine Verbindung bei [...] hergestellt werden.)

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Testen eines Trennschalters in eShopOnContainers

Es gibt mehrere Möglichkeiten, den Trennschalter zu öffnen und ihn auf diese Weise mit eShopOnContainers zu testen.

Eine Option besteht darin, die zulässige Anzahl von Wiederholungen in der Trennschalterrichtlinie auf eins zu reduzieren und die gesamte Lösung erneut in Docker bereitzustellen. Bei einem einzelnen Neuversuch ist die Wahrscheinlichkeit hoch, dass die HTTP-Anforderung bei der Bereitstellung fehlschlägt, der Trennschalter geöffnet und eine Fehlermeldung angezeigt wird.

Eine weitere Option besteht in der Verwendung benutzerdefinierter Middleware, die im `Basket`-Microservice implementiert wird. Wenn diese Middleware aktiviert ist, fängt sie alle HTTP-Anforderungen ab und gibt den Statuscode 500 zurück. Sie können die Middleware aktivieren, indem Sie eine GET-Anforderung an den URI stellen, der den Fehler auslöst. Dabei können Sie z.B. folgende Anforderungen verwenden:

-   GET /failing

Diese Anforderung gibt den aktuellen Status der Middleware zurück. Wenn die Middleware aktiviert ist, gibt die Anforderung den Statuscode 500 zurück. Wenn die Middleware deaktiviert ist, wird keine Antwort zurückgegeben.

-   GET /failing?enable

Diese Anforderung aktiviert die Middleware.

-   GET /failing?disable

Diese Anforderung deaktiviert die Middleware.

Sobald die Anwendung ausgeführt wird, können Sie z.B. die Middleware aktivieren, indem Sie mit dem unten aufgeführten URI in einem Browser eine Anforderung stellen. Beachten Sie, dass der Microservice für Bestellungen den Port 5103 verwendet.

http://localhost:5103/failing?enable

Mit dem URI [http://localhost:5103/failing](http://localhost:5103/failing) können Sie anschließend wie in Abbildung 10-4 dargestellt den Status überprüfen.

![](./media/image4.png)

**Abbildung 10-4.** Überprüfung des „Fehlerstatus“ der ASP.NET-Middleware (hier deaktiviert) 

Der Warenkorbmicroservice antwortet bei Aufruf immer mit dem Statuscode 500.

Sobald die Middleware ausgeführt wird, können Sie versuchen, über die MVC-Webanwendung eine Bestellung aufzugeben. Da die Anforderungen fehlschlagen, wird der Trennschalter geöffnet.

Wie im folgenden Beispiel zu sehen ist, befindet sich in der MVC-Webanwendung ein catch-Block in der Logik zum Aufgeben einer Bestellung. Wenn im Code eine durch den offenen Trennschalter ausgelöste Ausnahme abgefangen wird, erhält der Benutzer eine Wartebenachrichtigung.

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

Die durch den Code ausgelösten Schritte werden im Folgenden kurz zusammengefasst. Die Wiederholungsrichtlinie versucht mehrmals, HTTP-Anforderungen zu stellen, was zu HTTP-Fehlern führt. Wenn die maximale Anzahl der Versuche erreicht wird, die für die Trennschalterrichtlinie festgelegt wurde (in diesem Fall 5), löst die Anwendung eine BrokenCircuitException aus. Das Ergebnis ist eine Benutzerbenachrichtigung (s. Abbildung 10-5).

![](./media/image5.png)

**Abbildung 10-5.** Trennschalter, der einen Fehler zurückgibt, der auf der Benutzeroberfläche angezeigt wird

Sie können unterschiedliche Logiken für das Öffnen des Trennschalters festlegen. Alternativ können Sie auch eine HTTP-Anforderung an einen anderen Back-End-Microservice stellen, falls ein Fallbackdatencenter oder ein redundantes Back-End-System vorliegt.

Eine weitere Möglichkeit für die Implementierung von CircuitBreakerPolicy ist die Verwendung der Isolate-Methode (die die Öffnung des Trennschalters erzwingt und dafür sorgt, dass er geöffnet bleibt) und der Reset-Methode (die den Trennschalter wieder schließt). Diese können für die Erstellung eines Hilfs-HTTP-Endpunkts verwendet werden, der Isolate und Reset direkt in der Richtlinie aufruft. Ein derartiger HTTP-Endpunkt kann auch, falls er entsprechend gesichert ist, in einer Produktionsumgebung verwendet werden, um ein Downstreamsystem beispielsweise bei einem Upgrade vorübergehend zu isolieren. Alternativ könnte er den Trennschalter manuell auslösen, um ein Downstreamsystem zu schützen, das möglicherweise fehlerhaft ist.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Hinzufügen einer Jitterstrategie zur Wiederholungsrichtlinie

Eine reguläre Wiederholungsrichtlinie kann ein System negativ beeinflussen, falls hohe Parallelität, hohe Skalierbarkeit und ein hohes Konfliktpotenzial vorhanden sind. Um mit Spitzenlasten umgehen zu können, die bei ähnlichen Wiederholungsanforderungen von vielen Clients bei einem Teilausfall auftreten, empfiehlt es sich als Notlösung, den Wiederholungsalgorithmus oder die Wiederholungsrichtlinie um eine Jitterstrategie zu ergänzen. Wenn für den exponentiellen Backoff der Jitter zufällig festgelegt wird, kann dies die Gesamtleistung des End-to-End-Systems verbessern. Dadurch lassen sich beim Auftreten von Problemen Lastspitzen verteilen. Wenn Sie Polly verwenden, könnte der Code zum Implementieren des Jitters wie folgt aussehen:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Wiederholungsmuster**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Verbindungsresilienz** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung vorübergehender Fehler) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Trennschaltermuster**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker. Jitter: Making Things Better With Randomness** (Jitter: Optimierung durch Zufälligkeit) https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Zurück] (implement-http-call-retries-exponential-backoff-polly.md) [Weiter] (monitor-app-health.md)
