---
title: Verwenden von IHttpClientFactory zur Implementierung robuster HTTP-Anforderungen
description: Erfahren Sie, wie Sie IHttpClientFactory, verfügbar seit .NET Core 2.1, zum Erstellen von `HttpClient`-Instanzen verwenden, damit Sie es mühelos in Ihren Anwendungen verwenden können.
ms.date: 03/03/2020
ms.openlocfilehash: 088fb6c7e10ad656247ee4065da5c13d383b2cf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847218"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a>Verwenden von IHttpClientFactory zur Implementierung robuster HTTP-Anforderungen

<xref:System.Net.Http.IHttpClientFactory> ist ein Vertrag, der von `DefaultHttpClientFactory`, einer Factory, die seit .NET Core 2.1 für das Erstellen von <xref:System.Net.Http.HttpClient>-Instanzen verfügbar ist, die in Ihren Anwendungen verwendet werden sollen.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Probleme mit den ursprünglichen HttpClient-Klassen von .NET Core

Die ursprüngliche und bekannte <xref:System.Net.Http.HttpClient>-Klasse kann problemlos verwendet werden, allerdings wird sie von vielen Entwicklern in einigen Fällen nicht richtig verwendet.

Während diese Klasse `IDisposable` implementiert, wird die Deklaration und Instanziierung innerhalb einer `using`-Anweisung nicht bevorzugt, da beim Verwerfen des `HttpClient`-Objekts der zugrunde liegende Socket nicht sofort freigegeben wird, was zur _Erschöpfung von Sockets_ führen kann. Weitere Informationen zu diesem Problem finden Sie im Blogbeitrag [You're using HttpClient wrong and it is destabilizing your software (Sie verwenden HttpClient falsch und destabilisieren dadurch Ihre Software)](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

Deshalb sollte `HttpClient` einmal instanziiert und während der Lebensdauer einer Anwendung wiederverwendet werden. Das Instanziieren einer `HttpClient`-Klasse für jede Anforderung erschöpft die Anzahl der verfügbaren Sockets und führt zu hoher Auslastung. Dieses Problem führt zu `SocketException`-Fehlern. Mögliche Ansätze zur Lösung dieses Problems basieren auf der Erstellung des `HttpClient`-Objekts als Singleton-Objekt oder statisches Objekt. Dies wird in diesem [Microsoft-Artikel zur Verwendung von HttpClient](../../../csharp/tutorials/console-webapiclient.md) erläutert. Dies kann eine gute Lösung für kurzlebige Konsolen-Apps o. ä. sein, die einige Male am Tag ausgeführt werden.

Ein weiteres Problem, auf das Entwickler stoßen, ist die Verwendung einer gemeinsam genutzten Instanz von `HttpClient` in zeitintensiven Prozessen. In einer Situation, in der der HttpClient als Singleton oder statisches Objekt instanziiert wird, kann er die DNS-Änderungen nicht wie in dieser [Ausgabe](https://github.com/dotnet/corefx/issues/11224) des GitHub-Repositorys „dotnet/corefx“ beschrieben behandeln.

Es geht jedoch nicht wirklich um `HttpClient` an sich, sondern um den [Standardkonstruktor für HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), da er eine neue konkrete Instanz von <xref:System.Net.Http.HttpMessageHandler> erstellt, die die oben erwähnten Probleme mit der *Erschöpfung der Sockets* und den DNS-Änderungen aufweist.

Um die oben genannten Probleme zu lösen und `HttpClient`-Instanzen verwaltbar zu gestalten, wurde in .NET Core 2.1 die <xref:System.Net.Http.IHttpClientFactory>-Schnittstelle eingeführt, die zur Konfiguration und Erstellung von `HttpClient`-Instanzen in einer App durch Abhängigkeitsinjektion verwendet werden kann. Sie bietet auch Erweiterungen für auf Polly basierende Middleware, um die Vorteile der delegierenden Handler in HttpClient zu nutzen.

[Polly](http://www.thepollyproject.org/) ist eine Bibliothek zur Behandlung vorübergehender Fehler, mit der Entwickler ihren Anwendungen Resilienz hinzufügen können, indem sie einige vordefinierte Richtlinien auf fließende und threadsichere Weise verwenden.

## <a name="benefits-of-using-ihttpclientfactory"></a>Vorteile der Verwendung von IHttpClientFactory

Die derzeitige Implementierung von <xref:System.Net.Http.IHttpClientFactory>, die auch <xref:System.Net.Http.IHttpMessageHandlerFactory> implementiert, bietet die folgenden Vorteile:

- Bereitstellen eines zentralen Orts für das Benennen und Konfigurieren logischer `HttpClient`-Objekte. Sie können beispielsweise einen Client (Dienst-Agent) konfigurieren, der für das Zugreifen auf einen bestimmten Microservice vorkonfiguriert ist.
- Für das Umsetzen des Konzepts der ausgehenden Middleware über delegierende Handler in `HttpClient` in Code sowie für das Implementieren von Polly-basierter Middleware, um die Polly-Richtlinien für die Resilienz zu nutzen.
- `HttpClient` enthält bereits das Konzept, Handler zu delegieren, die für ausgehende HTTP-Anforderungen miteinander verknüpft werden könnten. Sie können HTTP-Clients in der Factory registrieren und einen Polly-Handler verwenden, um Polly-Richtlinien für Wiederholungen, CircuitBreakers usw. verwenden zu können.
- Für das Verwalten der Lebensdauer von <xref:System.Net.Http.HttpMessageHandler>-Meldungshandlern, um die erwähnten Probleme zu vermeiden, die auftreten können, wenn Sie die `HttpClient`-Lebensdauer selbst verwalten.

> [!TIP]
> Die von der Abhängigkeitsinjektion eingefügten `HttpClient`-Instanzen können sicher verworfen werden, da das zugehörige `HttpMessageHandler` von der Factory verwaltet wird. Tatsächlich werden eingefügte `HttpClient`-Instanzen aus Sicht der Abhängigkeitsinjektion auf einen *Bereich bezogen*.

> [!NOTE]
> Die Implementierung von `IHttpClientFactory` (`DefaultHttpClientFactory`) ist eng an die Implementierung der Abhängigkeitsinjektion im NuGet-Paket `Microsoft.Extensions.DependencyInjection` gebunden. Weitere Informationen zur Verwendung anderer Container für die Abhängigkeitsinjektion finden Sie in dieser [GitHub-Diskussion](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-ihttpclientfactory"></a>Mehrere Verwendungsmöglichkeiten für IHttpClientFactory

Es gibt mehrere Methoden, um `IHttpClientFactory` in Ihrer Anwendung zu verwenden:

- Grundlegende Verwendung
- Verwenden Sie benannte Clients.
- Verwenden Sie typisierte Clients.
- Verwenden Sie generierte Clients.

Aus Gründen der Übersichtlichkeit zeigt diese Anleitung die strukturierteste Art der Verwendung von `IHttpClientFactory`, also die Verwendung von typisierten Clients (Dienst-Agent-Muster). Allerdings sind alle Optionen dokumentiert und werden zurzeit in diesem [Artikel zur Verwendung von `IHttpClientFactory`](/aspnet/core/fundamentals/http-requests#consumption-patterns) aufgeführt.

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a>Verwenden von typisierten Clients mit IHttpClientFactory

Was ist ein „typisierter Client“? Es ist nur ein `HttpClient`, der für eine bestimmte Verwendung vorkonfiguriert ist. Diese Konfiguration kann bestimmte Werte wie den Basisserver, HTTP-Header oder Timeouts enthalten.

Im folgenden Diagramm wird veranschaulicht, wie typisierte Clients mit `IHttpClientFactory` verwendet werden:

![Diagramm, das zeigt, wie typisierte Clients mit IHttpClientFactory verwendet werden.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Abbildung 8-4.** Verwenden von `IHttpClientFactory` mit typisierten Clientklassen.

In der obigen Abbildung verwendet ein (von einem Controller oder Clientcode verwendeter) `ClientService` einen `HttpClient`, der von der registrierten `IHttpClientFactory` erstellt wird. Diese Factory weist einen `HttpMessageHandler` aus einem Pool dem `HttpClient` zu. Der `HttpClient` kann bei Registrierung der `IHttpClientFactory` im DI-Container mit der Erweiterungsmethode <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*> mit Pollys Richtlinien konfiguriert werden.

Um die obige Struktur zu konfigurieren, fügen Sie <xref:System.Net.Http.IHttpClientFactory> in Ihrer Anwendung hinzu, indem Sie das NuGet-Paket `Microsoft.Extensions.Http` installieren, das die <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*>-Erweiterungsmethode für <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> beinhaltet. Diese Erweiterungsmethode registriert die interne `DefaultHttpClientFactory`-Klasse für die Verwendung als Singleton für die Schnittstelle `IHttpClientFactory`. Dadurch wird eine temporäre Konfiguration für <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder> definiert. Dieser Meldungshandler (<xref:System.Net.Http.HttpMessageHandler>-Objekt), der aus einem Pool abgerufen wurde, wird von dem `HttpClient`-Objekt verwendet, das von der Factory zurückgegebenen wird.

Im nächsten Codeausschnitt wird veranschaulicht, wie `AddHttpClient()` verwendet werden kann, um typisierte Clients (Dienst-Agents) zu registrieren, die `HttpClient` verwenden müssen.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

Wenn Sie die Clientdienste wie im vorherigen Code gezeigt registrieren, erstellt `DefaultClientFactory` einen Standard-`HttpClient` für jeden Dienst.

Sie können auch eine instanzspezifische Konfiguration in der Registrierung hinzufügen (beispielsweise die Basisadresse konfigurieren und einige Resilienzrichtlinien hinzufügen). Der folgende Code zeigt dies:

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

Als Beispiel wird eine der oben aufgeführten Richtlinien im nächsten Code gezeigt:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

Weitere Informationen zum Verwenden von Polly finden Sie im [nächsten Artikel](implement-http-call-retries-exponential-backoff-polly.md).

### <a name="httpclient-lifetimes"></a>HTTPClient-Lebensdauer

Jedes Mal, wenn Sie ein `HttpClient`-Objekt von der `IHttpClientFactory` abrufen, wird eine neue Instanz zurückgegeben. Aber jeder `HttpClient` verwendet einen `HttpMessageHandler`, der zu einem Pool gehört und von der `IHttpClientFactory` wiederverwendet wird, um den Ressourcenverbrauch zu reduzieren, solange die Lebensdauer des `HttpMessageHandler` nicht abgelaufen ist.

Das Zusammenlegen von Handlern ist wünschenswert, da jeder Handler in der Regel über seine eigenen HTTP-Verbindungen verfügt. Das Erstellen von mehr Handlern als notwendig kann zu Verzögerungen bei der Verbindung führen. Einige Handler halten Verbindungen auch unbegrenzt offen, was verhindert, dass der Handler auf DNS-Änderungen reagiert.

Die `HttpMessageHandler`-Objekte im Pool haben eine Lebensdauer, die der Zeitspanne entspricht, in der eine `HttpMessageHandler`-Instanz im Pool wiederverwendet werden kann. Der Standardwert beträgt zwei Minuten, kann jedoch für jeden typisierten Client überschrieben werden. Rufen Sie `SetHandlerLifetime()` auf dem bei der Erstellung des Clients zurückgegebenen <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> auf, um den Wert zu überschreiben, wie im folgenden Code gezeigt:

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

Für jeden typisierten Client kann ein eigener Wert für die Lebensdauer des Handlers konfiguriert werden. Legen Sie die Lebensdauer auf `InfiniteTimeSpan` fest, um das Ablaufen des Handlers zu deaktivieren.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Implementieren von typisierten Clientklassen, die das injizierte und konfigurierte HttpClient-Objekt verwenden

Zuvor müssen Sie Ihre typisierten Clientklassen definieren, z. B. die Klassen im Beispielcode („BasketService“, „CatalogService“, „OrderingService“ usw.). Bei einem typisierten Client handelt es sich um eine Klasse, die ein `HttpClient`-Objekt akzeptiert (das über deren Konstruktor injiziert wird) und dieses verwendet, um HTTP-Remotedienste aufzurufen. Zum Beispiel:

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take,
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl,
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

Der typisierte Client (`CatalogService` im Beispiel) wird von der Abhängigkeitsinjektion aktiviert. Das bedeutet, dass dieser alle registrierten Dienste (zusätzlich zu `HttpClient`) im Konstruktor akzeptieren kann.

Ein typisierter Client ist im Prinzip ein temporäres Objekt. Das bedeutet, dass eine neue Instanz immer bei Bedarf erstellt wird und dass der Client immer eine neue `HttpClient`-Instanz erhält, wenn er erstellt wird. Die `HttpMessageHandler`-Objekte im Pool sind jedoch die Objekte, die von mehreren `HttpClient`-Instanzen wiederverwendet werden.

### <a name="use-your-typed-client-classes"></a>Verwenden von typisierten Clientklassen

Nachdem Sie Ihre typisierten Klassen implementiert und bei `AddHttpClient()` registriert und konfiguriert haben, können Sie sie überall dort verwenden, wo Dienste durch die Abhängigkeitsinjektion eingeschleust werden können. Beispielsweise in Code einer Razor Page-App oder Controllern einer MVC-Web-App, wie im folgenden Code aus eShopOnContainers:

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) =>
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied,
                                               int? TypesFilterApplied,
                                               int? page,
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0,
                                                            itemsPage,
                                                            BrandFilterApplied,
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

Bis zu diesem Punkt führt der Code nur reguläre HTTP-Anforderungen aus. In den folgenden Abschnitten wird jedoch nur durch das Hinzufügen von Richtlinien und das Delegieren von Handlern an Ihre registrierten typisierten Clients erreicht, dass alle von `HttpClient` durchgeführten HTTP-Anforderungen ihr Verhalten unter Berücksichtigung von Stabilitätsrichtlinien anpassen, z. B. Wiederholungen mit exponentiellem Backoff, Circuit Breakers oder andere benutzerdefinierte delegierende Handler für die Implementierung zusätzlicher Sicherheitsfeatures (z. B. Authentifizierungstokens) oder anderer benutzerdefinierter Features.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Verwenden von HttpClientFactory in .NET Core**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **HttpClientFactory-Quellcode im `dotnet/extensions`-GitHub-Repository**  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- **Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**  
  <http://www.thepollyproject.org/>
  
- **Verwenden von IHttpClientFactory ohne Abhängigkeitsinjektion (GitHub-Problem)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Zurück](implement-resilient-entity-framework-core-sql-connections.md)
>[Weiter](implement-http-call-retries-exponential-backoff-polly.md)
