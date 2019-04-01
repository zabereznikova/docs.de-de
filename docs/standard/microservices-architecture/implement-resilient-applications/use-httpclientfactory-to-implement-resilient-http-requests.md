---
title: Verwenden von HttpClientFactory zur Implementierung robuster HTTP-Anforderungen
description: Erfahren Sie, wie Sie HttpClientFactory, verfügbar seit .NET Core 2.1, zum Erstellen von `HttpClient`-Instanzen verwenden, damit Sie HttpClientFactory mühelos in Ihren Anwendungen verwenden können.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: a55181e787b5c94e13d3945a5d97a12fed61e927
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465931"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="5ba70-103">Verwenden von HttpClientFactory zur Implementierung robuster HTTP-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ba70-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="5ba70-104">`HttpClientFactory` ist eine Factory, die seit .NET Core 2.1 für das Erstellen von <xref:System.Net.Http.HttpClient>-Instanzen verfügbar ist, die in Ihren Anwendungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5ba70-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="5ba70-105">Probleme mit den ursprünglichen HttpClient-Klassen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="5ba70-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="5ba70-106">Die ursprüngliche und bekannte [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0)-Klasse kann einfach verwendet werden, allerdings wird sie von vielen Entwicklern in einigen Fällen nicht richtig verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ba70-106">The original and well-known [HttpClient](/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span> 

<span data-ttu-id="5ba70-107">Die Klasse ist zwar verwerfbar, sollte jedoch nicht mit der `using`-Anweisung verwendet werden. Selbst wenn Sie das `HttpClient`-Objekt verwerfen, wird der zugrunde liegende Socket nicht sofort freigegeben und kann zu einem schwerwiegenden Problem namens „sockets exhaustion“ (Socketauslastung) führen.</span><span class="sxs-lookup"><span data-stu-id="5ba70-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="5ba70-108">Weitere Informationen zu diesem Problem finden Sie im Blogbeitrag [You're using HttpClient wrong and it is destabilizing your software (Sie verwenden HttpClient falsch und destabilisieren dadurch Ihre Software)](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="5ba70-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="5ba70-109">Deshalb sollte `HttpClient` einmal instanziiert und während der Lebensdauer einer Anwendung wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ba70-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="5ba70-110">Das Instanziieren einer `HttpClient`-Klasse für jede Anforderung erschöpft die Anzahl der verfügbaren Sockets und führt zu hoher Auslastung.</span><span class="sxs-lookup"><span data-stu-id="5ba70-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="5ba70-111">Dieses Problem führt zu `SocketException`-Fehlern.</span><span class="sxs-lookup"><span data-stu-id="5ba70-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="5ba70-112">Mögliche Ansätze zur Lösung dieses Problems basieren auf der Erstellung des `HttpClient`-Objekts als Singleton-Objekt oder statisches Objekt. Dies wird in diesem [Microsoft-Artikel zur Verwendung von HttpClient](/dotnet/csharp/tutorials/console-webapiclient) erläutert.</span><span class="sxs-lookup"><span data-stu-id="5ba70-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](/dotnet/csharp/tutorials/console-webapiclient).</span></span> 

<span data-ttu-id="5ba70-113">Es gibt jedoch noch ein weiteres Problem mit `HttpClient`, das auftreten kann, wenn Sie HttpClient als Singleton-Objekt oder statisches Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ba70-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="5ba70-114">In diesem Fall berücksichtigt ein `HttpClient`-Singleton-Objekt bzw. ein statisches HttpClient-Objekt keine DNS-Änderungen. Dies wird in diesem [Issue im .NET Core-Repository auf GitHub](https://github.com/dotnet/corefx/issues/11224) erläutert.</span><span class="sxs-lookup"><span data-stu-id="5ba70-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue at the .NET Core GitHub repo](https://github.com/dotnet/corefx/issues/11224).</span></span> 

<span data-ttu-id="5ba70-115">Um diese Probleme zu beheben und die Verwaltung von `HttpClient`-Instanzen zu erleichtern, stellt .NET Core 2.1 ein neues `HttpClientFactory`-Objekt zur Verfügung, das zur Implementierung von robusten HTTP-Aufrufen verwendet werden kann, indem Polly integriert wird.</span><span class="sxs-lookup"><span data-stu-id="5ba70-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>   

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="5ba70-116">Über HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="5ba70-116">What is HttpClientFactory</span></span>

<span data-ttu-id="5ba70-117">`HttpClientFactory` wurde für Folgendes entwickelt:</span><span class="sxs-lookup"><span data-stu-id="5ba70-117">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="5ba70-118">Als zentraler Ort für das Benennen und Konfigurieren logischer HttpClient-Objekte.</span><span class="sxs-lookup"><span data-stu-id="5ba70-118">Provide a central location for naming and configuring logical HttpClients.</span></span> <span data-ttu-id="5ba70-119">Sie können beispielsweise einen Client (Dienst-Agent) konfigurieren, der für das Zugreifen auf einen bestimmten Microservice vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="5ba70-119">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="5ba70-120">Für das Umsetzen des Konzepts der ausgehenden Middleware über delegierende Handler in `HttpClient` in Code sowie für das Implementieren von Polly-basierter Middleware, um die Polly-Richtlinien für die Resilienz zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="5ba70-120">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="5ba70-121">`HttpClient` enthält bereits das Konzept, Handler zu delegieren, die für ausgehende HTTP-Anforderungen miteinander verknüpft werden könnten.</span><span class="sxs-lookup"><span data-stu-id="5ba70-121">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="5ba70-122">Sie registrieren HTTP-Clients in der Factory und können einen Polly-Handler verwenden, um Polly-Richtlinien für Wiederholungen, Circuit Breakers usw. verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="5ba70-122">You register http clients into the factory plus you can use a Polly handler that allows Polly policies to be used for Retry, CircuitBreakers, etc.</span></span>
- <span data-ttu-id="5ba70-123">Für das Verwalten der Lebensdauer von HttpClient-Meldungshandlern, um die erwähnten Probleme zu vermeiden, die auftreten können, wenn Sie die `HttpClient`-Lebensdauer selbst verwalten.</span><span class="sxs-lookup"><span data-stu-id="5ba70-123">Manage the lifetime of HttpClientMessageHandlers to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span> 

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="5ba70-124">Mehrere Verwendungsmöglichkeiten für HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="5ba70-124">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="5ba70-125">Es gibt mehrere Methoden, um `HttpClientFactory` in Ihrer Anwendung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="5ba70-125">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="5ba70-126">Verwenden Sie `HttpClientFactory` direkt.</span><span class="sxs-lookup"><span data-stu-id="5ba70-126">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="5ba70-127">Verwenden Sie benannte Clients.</span><span class="sxs-lookup"><span data-stu-id="5ba70-127">Use Named Clients</span></span>
- <span data-ttu-id="5ba70-128">Verwenden Sie typisierte Clients.</span><span class="sxs-lookup"><span data-stu-id="5ba70-128">Use Typed Clients</span></span>
- <span data-ttu-id="5ba70-129">Verwenden Sie generierte Clients.</span><span class="sxs-lookup"><span data-stu-id="5ba70-129">Use Generated Clients</span></span>

<span data-ttu-id="5ba70-130">Aus Gründen der Übersichtlichkeit veranschaulicht diese Anleitung die am besten strukturierte Möglichkeit, um `HttpClientFactory` zu verwenden. Diese besteht im Verwenden von typisierten Clients (Dienst-Agent-Muster). Alle Optionen werden dokumentiert und derzeit in diesem [Artikel über die Verwendung von HttpClientFactory](/aspnet/core/fundamentals/http-requests?#consumption-patterns) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ba70-130">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory` that's to use Typed Clients (Service Agent pattern), but all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span></span>  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="5ba70-131">Verwenden von typisierten Clients mit HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="5ba70-131">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="5ba70-132">Was ist ein „typisierter Client“?</span><span class="sxs-lookup"><span data-stu-id="5ba70-132">So, what's a "Typed Client"?</span></span> <span data-ttu-id="5ba70-133">Es ist einfach ein `HttpClient`, der konfiguriert wird, nachdem er von `DefaultHttpClientFactory` injiziert worden ist.</span><span class="sxs-lookup"><span data-stu-id="5ba70-133">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="5ba70-134">Im folgenden Diagramm wird veranschaulicht, wie typisierte Clients mit `HttpClientFactory` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5ba70-134">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![Ein (von einem Controller oder Clientcode verwendeter) ClientService verwendet einen HttpClient, der von der registrierten IHttpClientFactory erstellt wird.](./media/image3.5.png)

<span data-ttu-id="5ba70-138">**Abbildung 8-4.**</span><span class="sxs-lookup"><span data-stu-id="5ba70-138">**Figure 8-4**.</span></span> <span data-ttu-id="5ba70-139">Verwenden von HttpClientFactory mit Klassen typisierter Clients.</span><span class="sxs-lookup"><span data-stu-id="5ba70-139">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="5ba70-140">Richten Sie zunächst `HttpClientFactory` in Ihrer Anwendung ein, wobei Sie einen Verweises auf das `Microsoft.Extensions.Http`-Paket hinzufügen, das die `AddHttpClient()`-Erweiterungsmethode für `IServiceCollection` beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="5ba70-140">First, setup `HttpClientFactory` in your application, adding a reference to the `Microsoft.Extensions.Http` package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="5ba70-141">Diese Erweiterungsmethode registriert `DefaultHttpClientFactory` für die Verwendung als Singleton für die Schnittstelle `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="5ba70-141">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="5ba70-142">Dadurch wird eine temporäre Konfiguration für `HttpMessageHandlerBuilder` definiert.</span><span class="sxs-lookup"><span data-stu-id="5ba70-142">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="5ba70-143">Dieser Meldungshandler (`HttpMessageHandler`-Objekt), der aus einem Pool abgerufen wurde, wird von dem `HttpClient`-Objekt verwendet, das von der Factory zurückgegebenen wird.</span><span class="sxs-lookup"><span data-stu-id="5ba70-143">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="5ba70-144">Im nächsten Codeausschnitt wird veranschaulicht, wie `AddHttpClient()` verwendet werden kann, um typisierte Clients (Dienst-Agents) zu registrieren, die `HttpClient` verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="5ba70-144">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="5ba70-145">Bei Registrierung der Clientdienste wie im vorherigen Code gezeigt erstellt `DefaultClientFactory` einen `HttpClient`, der speziell für jeden Dienst konfiguriert wird. Dies wird im nächsten Absatz erläutert.</span><span class="sxs-lookup"><span data-stu-id="5ba70-145">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create an `HttpClient` configured specifically for each service, as we'll explain in the next paragraph.</span></span>

<span data-ttu-id="5ba70-146">Nur durch das Registrieren Ihrer Clientdienstklasse mit `AddHttpClient()` verwendet das `HttpClient`-Objekt, das in Ihre Klasse eingefügt wird, Konfiguration und Richtlinien, die bei der Registrierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5ba70-146">Just by registering your client service class with `AddHttpClient()`, the `HttpClient` object that will be injected into your class will use the configuration and policies provided upon registration.</span></span> <span data-ttu-id="5ba70-147">In den nächsten Abschnitten werden Richtlinien wie Polly-Wiederholungen oder Circuit Breakers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5ba70-147">In the next sections, you'll see those policies like Polly’s retries or circuit-breakers.</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="5ba70-148">HTTPClient-Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="5ba70-148">HttpClient lifetimes</span></span>

<span data-ttu-id="5ba70-149">Jedes Mal, wenn Sie ein `HttpClient`-Objekt von der `IHttpClientFactory` abrufen, wird eine neue Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ba70-149">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="5ba70-150">Aber jeder `HttpClient` verwendet einen `HttpMessageHandler`, der zu einem Pool gehört und von der `IHttpClientFactory` wiederverwendet wird, um den Ressourcenverbrauch zu reduzieren, solange die Lebensdauer des `HttpMessageHandler` nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="5ba70-150">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="5ba70-151">Das Zusammenlegen von Handlern ist wünschenswert, da jeder Handler in der Regel über seine eigenen HTTP-Verbindungen verfügt. Das Erstellen von mehr Handlern als notwendig kann zu Verzögerungen bei der Verbindung führen.</span><span class="sxs-lookup"><span data-stu-id="5ba70-151">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="5ba70-152">Einige Handler halten Verbindungen auch unbegrenzt offen, was verhindert, dass der Handler auf DNS-Änderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="5ba70-152">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="5ba70-153">Die `HttpMessageHandler`-Objekte im Pool haben eine Lebensdauer, die der Zeitspanne entspricht, in der eine `HttpMessageHandler`-Instanz im Pool wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ba70-153">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="5ba70-154">Der Standardwert beträgt zwei Minuten, kann jedoch für jeden typisierten Client überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5ba70-154">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="5ba70-155">Rufen Sie `SetHandlerLifetime()` auf dem bei der Erstellung des Clients zurückgegebenen `IHttpClientBuilder` auf, um den Wert zu überschreiben, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5ba70-155">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

<span data-ttu-id="5ba70-156">Für jeden typisierten Client kann ein eigener Wert für die Lebensdauer des Handlers konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5ba70-156">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="5ba70-157">Legen Sie die Lebensdauer auf `InfiniteTimeSpan` fest, um das Ablaufen des Handlers zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ba70-157">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="5ba70-158">Implementieren von typisierten Clientklassen, die das injizierte und konfigurierte HttpClient-Objekt verwenden</span><span class="sxs-lookup"><span data-stu-id="5ba70-158">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="5ba70-159">Zuvor müssen Sie Ihre typisierten Clientklassen definieren, z.B. die Klassen im Beispielcode („BasketService“, „CatalogService“, „OrderingService“ usw.). Bei einem typisierten Client handelt es sich um eine Klasse, die ein `HttpClient`-Objekt akzeptiert (das über deren Konstruktor injiziert wird) und dieses verwendet, um HTTP-Remotedienste aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5ba70-159">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="5ba70-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ba70-160">For example:</span></span>

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

<span data-ttu-id="5ba70-161">Der typisierte Client (im Beispiel „CatalogService“) wird von Dependency Injection (DI) aktiviert. Das bedeutet, dass dieser alle registrierten Dienste (zusätzlich zu HttpClient) im Konstruktor akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="5ba70-161">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="5ba70-162">Ein typisierter Client ist im Prinzip ein temporäres Objekt. Das bedeutet, dass eine neue Instanz immer bei Bedarf erstellt wird und dass der Client immer eine neue `HttpClient`-Instanz erhält, wenn er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5ba70-162">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="5ba70-163">Bei den HttpMessageHandler-Objekten im Pool handelt es sich um Objekte, die von mehreren HTTP-Anforderungen wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ba70-163">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="5ba70-164">Verwenden von typisierten Clientklassen</span><span class="sxs-lookup"><span data-stu-id="5ba70-164">Use your Typed Client classes</span></span>

<span data-ttu-id="5ba70-165">Sobald Sie Ihre typisierten Klassen implementiert und mit AddHttpClient() registriert haben, können Sie diese schließlich überall dort verwenden, wo Dienste mit Dependency Injection injiziert werden, z.B. in Razor Pages-Code oder in einem Controller einer MVC-Web-App. Ein Beispiel hierfür finden Sie im folgenden Code von eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="5ba70-165">Finally, once you have your type classes implemented and have them registered with AddHttpClient(), you can use it anywhere you can have services injected by DI, for example in any Razor page code or any controller of an MVC web app, like in the following code from eShopOnContainers.</span></span>

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

<span data-ttu-id="5ba70-166">Bis zu diesem Punkt führt der Code nur reguläre HTTP-Anforderungen aus. In den folgenden Abschnitten wird jedoch nur durch das Hinzufügen von Richtlinien und das Delegieren von Handlern an Ihre registrierten typisierten Clients erreicht, dass alle von `HttpClient` durchgeführten HTTP-Anforderungen ihr Verhalten unter Berücksichtigung von Stabilitätsrichtlinien anpassen, z.B. Wiederholungen mit exponentiellem Backoff, Circuit Breakers oder andere benutzerdefinierte delegierende Handler für die Implementierung zusätzlicher Sicherheitsfeatures (z.B. Authentifizierungstokens) oder anderer benutzerdefinierter Features.</span><span class="sxs-lookup"><span data-stu-id="5ba70-166">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="5ba70-167">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5ba70-167">Additional resources</span></span>

- <span data-ttu-id="5ba70-168">**Verwenden von HttpClientFactory in .NET Core**\\</span><span class="sxs-lookup"><span data-stu-id="5ba70-168">**Using HttpClientFactory in .NET Core**\\</span></span>
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1](/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)

- <span data-ttu-id="5ba70-169">**GitHub-Repository zu HttpClientFactory**\\</span><span class="sxs-lookup"><span data-stu-id="5ba70-169">**HttpClientFactory GitHub repo**\\</span></span>
  <https://github.com/aspnet/Extensions/tree/master/src/HttpClientFactory>

>[!div class="step-by-step"]
><span data-ttu-id="5ba70-170">[Zurück](explore-custom-http-call-retries-exponential-backoff.md)
>[Weiter](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="5ba70-170">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
