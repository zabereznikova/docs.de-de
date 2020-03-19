---
title: Implementieren des Trennschaltermusters
description: Erfahren Sie, wie das Circuit-Breaker-Muster als ergänzendes System zu HTTP-Wiederholungsversuchen implementieren können.
ms.date: 03/03/2020
ms.openlocfilehash: a79c6fcca1e29f3c30d697cb369060d59a72c121
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847244"
---
# <a name="implement-the-circuit-breaker-pattern"></a>Implementieren des Circuit Breaker-Musters

Wie bereits in einem vorherigen Artikel erwähnt wurde, sollten Sie Fehler behandeln, deren Behebung unterschiedlich lange dauern kann. Dies kann beispielsweise der Fall sein, wenn Sie versuchen, sich mit einem Remote-Dienst oder einer Remote-Ressource zu verbinden. Die Behandlung derartiger Fehler kann die Stabilität und Robustheit einer Anwendung erhöhen.

In einer verteilten Umgebung können Aufrufe von Remote-Ressourcen und -Diensten fehlschlagen, wenn vorübergehende Fehler wie langsame Netzwerkverbindungen und Timeouts auftreten oder wenn Ressourcen zu langsam reagieren oder vorübergehend nicht verfügbar sind. Diese Fehler werden in der Regel nach kurzer Zeit korrigiert, und eine robuste Cloudanwendung sollte diese durch eine Strategie wie das Wiederholungsmuster behandeln können.

Es gibt jedoch auch Situationen, in denen Fehler aufgrund unerwarteter Ereignisse auftreten. Die Behebung dieser Fehler kann deutlich mehr Zeit in Anspruch nehmen. Zu unterscheiden sind unterschiedliche Schweregrade, die von einem Teilverlust der Konnektivität bis hin zum vollständigen Ausfall des Diensts reichen können. In diesen Situationen ist es möglicherweise nicht sinnvoll, wenn eine Anwendung einen Vorgang mehrfach wiederholt, der wahrscheinlich nicht erfolgreich ausgeführt werden kann.

Stattdessen sollte die Anwendung so programmiert sein, dass ein fehlgeschlagener Vorgang akzeptiert und der Fehler entsprechend behandelt wird.

Wenn Sie HTTP-Wiederholungen nicht sorgfältig verwenden, kann dies zu einem Denial-of-Service-Angriff ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) innerhalb Ihrer eigenen Software führen. Wenn ein Microservice fehlschlägt oder langsam ausgeführt wird, wiederholen möglicherweise mehrere Clients fehlgeschlagene Anforderungen. Dadurch entsteht das Risiko, exponentiell ansteigenden Datenverkehr zu erzeugen, den fehlgeschlagenen Dienst anzielt.

Deshalb benötigen Sie eine „Sicherung“, damit übermäßige Anforderungen beendet werden, wenn weitere Versuche überflüssig sind. Bei dieser Sicherung handelt es sich um den Circuit Breaker.

Das Circuit Breaker-Muster hat einen anderen Zweck als das Wiederholungsmuster. Das Wiederholungsmuster ermöglicht es einer Anwendung, einen Vorgang erneut auszuführen, wobei davon ausgegangen wird, dass dieser irgendwann erfolgreich ist. Das Circuit Breaker-Muster hindert eine Anwendung daran, einen Vorgang auszuführen, bei dem vermutlich ein Fehler auftreten wird. Eine Anwendung kann diese beiden Muster kombinieren. Die Wiederholungslogik sollte jedoch Ausnahmen behandeln können, die vom Circuit Breaker zurückgegeben werden, und auf Wiederholungsversuche verzichten, wenn der Circuit Breaker anzeigt, dass ein Fehler nicht temporär ist.

## <a name="implement-circuit-breaker-pattern-with-ihttpclientfactory-and-polly"></a>Implementieren eines Circuit Breaker-Musters mit `IHttpClientFactory` und Polly

Ebenso wie für die Implementierung von Wiederholungen wird auch für Circuit Breakers empfohlen, auf bewährte .NET-Bibliotheken wie Polly und die native Integration in `IHttpClientFactory` zurückzugreifen.

Eine Circuit Breaker-Richtlinie kann zu Ihrer ausgehenden `IHttpClientFactory`-Middlewarepipeline hinzugefügt werden, indem Sie einfach einen einzelnen inkrementellen Codeabschnitt zu dem Code hinzufügen, der bei der Verwendung von `IHttpClientFactory` bereits vorhanden ist.

Der nachfolgende Code für Wiederholungen von HTTP-Aufrufen wird nur insofern geändert, als die Circuit Breaker-Richtlinie der zu verwendenden Richtlinienliste hinzugefügt wird. Dies wird in folgendem inkrementellen Code veranschaulicht, der Teil der ConfigureServices()-Methode ist.

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Sample. Default lifetime is 2 minutes
        .AddHttpMessageHandler<HttpClientAuthorizationDelegatingHandler>()
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

Durch die Methode `AddPolicyHandler()` werden dem `HttpClient`-Objekt, das Sie verwenden, Richtlinien hinzugefügt. In diesem Fall wird eine Polly-Richtlinie für einen Circuit Breaker hinzugefügt.

Für einen modulareren Ansatz wird die Circuit Breaker-Richtlinie in einer separaten Methode namens `GetCircuitBreakerPolicy()` definiert, wie in folgendem Code veranschaulicht:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

Im obigen Codebeispiel wird die Circuit Breaker-Richtlinie dafür konfiguriert, die Kommunikation zu unterbrechen oder fortzusetzen, wenn beim Wiederholen der HTTP-Anforderungen fünf aufeinanderfolgende Fehler aufgetreten sind. In diesem Fall wird der Schaltkreis 30 Sekunden lang unterbrochen: In diesem Zeitraum schlagen Aufrufe durch den Circuit Breaker sofort fehl, statt tatsächlich durchgeführt zu werden.  Die Richtlinie interpretiert [relevante Ausnahmen und HTTP-Statuscodes](/aspnet/core/fundamentals/http-requests#handle-transient-faults) automatisch als Fehler.  

Circuit Breakers sollten auch verwendet werden, um Anforderungen an eine Fallbackinfrastruktur umzuleiten, wenn Probleme bei einer bestimmten Ressource aufgetreten sind, die in einer anderen Umgebung als die Clientanwendung oder der Dienst bereitgestellt wird, die bzw. der den HTTP-Aufruf ausführt. Auf diese Weise kann die Clientanwendung bei einem Ausfall im Rechenzentrum, der nur Back-End-Microservices, nicht aber Clientanwendungen betrifft, Anforderungen an Fallbackdienste umleiten. Für Polly wird aktuell eine Richtlinie zur Automatisierung dieses [Failoverrichtlinienszenarios](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) geplant.

Die erwähnten Features sind nur für Fälle geeignet, in denen das Failover mit .NET Code und nicht automatisch von Azure unter Berücksichtigung von Speicherorttransparenz verwaltet wird.

Bei der Verwendung von HttpClient besteht aus Benutzerperspektive keine Notwendigkeit, neue Elemente hinzuzufügen, da der Code wie in den vorherigen Abschnitten dargestellt identisch mit dem ist, der bei `HttpClient` mit `IHttpClientFactory` verwendet wird.

## <a name="test-http-retries-and-circuit-breakers-in-eshoponcontainers"></a>Testen von HTTP-Wiederholungen und Circuit Breakern in eShopOnContainers

Sobald Sie die eShopOnContainers-Lösung in einem Docker-Host starten, müssen mehrere Container gestartet werden. Einige Container wie der SQL Server-Container werden langsamer gestartet und initialisiert. Dies ist v.a. dann der Fall, wenn Sie die eShopOnContainers-Anwendung zum ersten Mal in Docker bereitstellen, da die Images und die Datenbank eingerichtet werden müssen. Der langsamere Start einiger Container kann dazu führen, dass die anderen Dienste auch dann anfänglich HTTP-Ausnahmen auslösen, wenn Sie, wie in den vorherigen Abschnitten beschrieben, Abhängigkeiten zwischen Containern auf der docker-compose-Ebene festlegen. Diese docker-compose-Abhängigkeiten zwischen Containern befinden sich nur auf der Prozessebene. Auch wenn der Einstiegspunktprozess des Containers bereits gestartet wurde, ist SQL Server möglicherweise noch nicht für Abfragen bereit. Das Ergebnis können zahlreiche Fehler sein. Außerdem wird in der Anwendung möglicherweise eine Ausnahme angezeigt, wenn sie versucht, den Container zu verwenden.

Diese Art von Fehler kann auch beim Start angezeigt werden, wenn die Anwendung in der Cloud bereitgestellt wird. In diesem Fall können Orchestratoren einen Container zwischen Knoten oder virtuellen Computern hin- und herschieben (was dem Start neuer Instanzen entspricht), wenn die Anzahl der Container für Clusterknoten ausgeglichen wird.

eShopOnContainers behebt diese Probleme beim Starten aller Container, indem das zuvor veranschaulichte Wiederholungsmuster verwendet wird.

### <a name="test-the-circuit-breaker-in-eshoponcontainers"></a>Testen des Circuit Breakers in eShopOnContainers

Es gibt mehrere Möglichkeiten, die Kommunikation zu unterbrechen oder fortzusetzen und ihn auf diese Weise mit eShopOnContainers zu testen.

Eine Option besteht darin, die zulässige Anzahl von Wiederholungen in der Trennschalterrichtlinie auf eins zu reduzieren und die gesamte Lösung erneut in Docker bereitzustellen. Bei einem einzelnen Neuversuch ist die Wahrscheinlichkeit hoch, dass die HTTP-Anforderung bei der Bereitstellung fehlschlägt, der Circuit Breaker geöffnet und eine Fehlermeldung angezeigt wird.

Eine weitere Option besteht in der Verwendung benutzerdefinierter Middleware, die im **Basket**-Microservice implementiert wird. Wenn diese Middleware aktiviert ist, fängt sie alle HTTP-Anforderungen ab und gibt den Statuscode 500 zurück. Sie können die Middleware aktivieren, indem Sie eine GET-Anforderung an den URI stellen, der den Fehler auslöst. Dabei können Sie z.B. folgende Anforderungen verwenden:

- `GET http://localhost:5103/failing`\
  Diese Anforderung gibt den aktuellen Status der Middleware zurück. Wenn die Middleware aktiviert ist, gibt die Anforderung den Statuscode 500 zurück. Wenn die Middleware deaktiviert ist, wird keine Antwort zurückgegeben.

- `GET http://localhost:5103/failing?enable`\
  Diese Anforderung aktiviert die Middleware.

- `GET http://localhost:5103/failing?disable`\
  Diese Anforderung deaktiviert die Middleware.

Sobald die Anwendung ausgeführt wird, können Sie z.B. die Middleware aktivieren, indem Sie mit dem unten aufgeführten URI in einem Browser eine Anforderung stellen. Beachten Sie, dass der Microservice für Bestellungen den Port 5103 verwendet.

`http://localhost:5103/failing?enable`

Mit dem URI `http://localhost:5103/failing` können Sie anschließend wie in Abbildung 8–5 dargestellt den Status überprüfen.

![Screenshot der Überprüfung des Status einer fehlschlagenden Middlewaresimulation.](./media/implement-circuit-breaker-pattern/failing-middleware-simulation.png)

**Abbildung 8-5.** Überprüfung des „Fehlerstatus“ der ASP.NET-Middleware (hier deaktiviert)

Der Warenkorbmicroservice antwortet bei Aufruf immer mit dem Statuscode 500.

Sobald die Middleware ausgeführt wird, können Sie versuchen, über die MVC-Webanwendung eine Bestellung aufzugeben. Da die Anforderungen fehlschlagen, wird die Kommunikation fortgesetzt.

Wie im folgenden Beispiel zu sehen ist, befindet sich in der MVC-Webanwendung ein catch-Block in der Logik zum Aufgeben einer Bestellung.  Wenn im Code eine durch den offenen Trennschalter ausgelöste Ausnahme abgefangen wird, erhält der Benutzer eine Wartebenachrichtigung.

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
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

Die durch den Code ausgelösten Schritte werden im Folgenden kurz zusammengefasst. Die Wiederholungsrichtlinie versucht mehrmals, HTTP-Anforderungen zu stellen, was zu HTTP-Fehlern führt. Wenn die maximale Anzahl der Wiederholungen erreicht wird, die für die Circuit Breaker-Richtlinie festgelegt wurde (in diesem Fall 5), löst die Anwendung die Ausnahme „BrokenCircuitException“ aus. Das Ergebnis ist eine Benutzerbenachrichtigung (siehe Abbildung 8-6).

![Screenshot der MVC-Web-App mit einem Fehler wegen nicht funktionierendem Warenkorbdienst.](./media/implement-circuit-breaker-pattern/basket-service-inoperative.png)

**Abbildung 8-6.** Trennschalter, der einen Fehler zurückgibt, der auf der Benutzeroberfläche angezeigt wird

Sie können unterschiedliche Logiken für das Fortsetzen oder Unterbrechen der Kommunikation festlegen. Alternativ können Sie auch eine HTTP-Anforderung an einen anderen Back-End-Microservice stellen, falls ein Fallbackrechenzentrum oder ein redundantes Back-End-System vorliegt.

Eine weitere Möglichkeit für `CircuitBreakerPolicy` ist die Verwendung von `Isolate` (dadurch wird das Fortsetzen der Kommunikation erzwungen und dafür gesorgt, dass diese bestehen bleibt) und `Reset` (dadurch wird die Kommunikation wieder unterbrochen). Diese können für die Erstellung eines Hilfs-HTTP-Endpunkts verwendet werden, der Isolate und Reset direkt in der Richtlinie aufruft.  Ein derartiger HTTP-Endpunkt kann auch, falls er entsprechend gesichert ist, in einer Produktionsumgebung verwendet werden, um ein Downstreamsystem beispielsweise bei einem Upgrade vorübergehend zu isolieren. Alternativ könnte er den Trennschalter manuell auslösen, um ein Downstreamsystem zu schützen, das möglicherweise fehlerhaft ist.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Circuit Breaker-Muster**\
  [https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker](/azure/architecture/patterns/circuit-breaker)

>[!div class="step-by-step"]
>[Zurück](implement-http-call-retries-exponential-backoff-polly.md)
>[Weiter](monitor-app-health.md)
