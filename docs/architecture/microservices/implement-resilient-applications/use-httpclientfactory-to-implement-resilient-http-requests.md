---
title: Verwenden von HttpClientFactory zur Implementierung robuster HTTP-Anforderungen
description: Erfahren Sie, wie Sie HttpClientFactory, verfügbar seit .NET Core 2.1, zum Erstellen von `HttpClient`-Instanzen verwenden, damit Sie HttpClientFactory mühelos in Ihren Anwendungen verwenden können.
ms.date: 08/08/2019
ms.openlocfilehash: 1a6d65509d669166e73ad907b506bae7fa26536d
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900326"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="21996-103">Verwenden von HttpClientFactory zur Implementierung robuster HTTP-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21996-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="21996-104">`HttpClientFactory` ist eine Factory, die seit .NET Core 2.1 für das Erstellen von <xref:System.Net.Http.HttpClient>-Instanzen verfügbar ist, die in Ihren Anwendungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="21996-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="21996-105">Probleme mit den ursprünglichen HttpClient-Klassen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="21996-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="21996-106">Die ursprüngliche und bekannte <xref:System.Net.Http.HttpClient>-Klasse kann problemlos verwendet werden, allerdings wird sie von vielen Entwicklern in einigen Fällen nicht richtig verwendet.</span><span class="sxs-lookup"><span data-stu-id="21996-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="21996-107">Die Klasse ist zwar verwerfbar, sollte jedoch nicht mit der `using`-Anweisung verwendet werden. Selbst wenn Sie das `HttpClient`-Objekt verwerfen, wird der zugrunde liegende Socket nicht sofort freigegeben und kann zu einem schwerwiegenden Problem namens „sockets exhaustion“ (Socketauslastung) führen.</span><span class="sxs-lookup"><span data-stu-id="21996-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="21996-108">Weitere Informationen zu diesem Problem finden Sie im Blogbeitrag [You're using HttpClient wrong and it is destabilizing your software (Sie verwenden HttpClient falsch und destabilisieren dadurch Ihre Software)](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="21996-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="21996-109">Deshalb sollte `HttpClient` einmal instanziiert und während der Lebensdauer einer Anwendung wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21996-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="21996-110">Das Instanziieren einer `HttpClient`-Klasse für jede Anforderung erschöpft die Anzahl der verfügbaren Sockets und führt zu hoher Auslastung.</span><span class="sxs-lookup"><span data-stu-id="21996-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="21996-111">Dieses Problem führt zu `SocketException`-Fehlern.</span><span class="sxs-lookup"><span data-stu-id="21996-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="21996-112">Mögliche Ansätze zur Lösung dieses Problems basieren auf der Erstellung des `HttpClient`-Objekts als Singleton-Objekt oder statisches Objekt. Dies wird in diesem [Microsoft-Artikel zur Verwendung von HttpClient](../../../csharp/tutorials/console-webapiclient.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="21996-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span>

<span data-ttu-id="21996-113">Es gibt jedoch noch ein weiteres Problem mit `HttpClient`, das auftreten kann, wenn Sie HttpClient als Singleton-Objekt oder statisches Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="21996-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="21996-114">In diesem Fall berücksichtigt ein `HttpClient`-Singleton-Objekt bzw. ein statisches HttpClient-Objekt keine DNS-Änderungen. Dies wird in diesem [Issue](https://github.com/dotnet/corefx/issues/11224) im GitHub-Repository unter „dotnet/corefx“ erläutert.</span><span class="sxs-lookup"><span data-stu-id="21996-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue](https://github.com/dotnet/corefx/issues/11224) at the dotnet/corefx GitHub repository.</span></span>

<span data-ttu-id="21996-115">Um diese Probleme zu beheben und die Verwaltung von `HttpClient`-Instanzen zu erleichtern, stellt .NET Core 2.1 ein neues `HttpClientFactory`-Objekt zur Verfügung, das zur Implementierung von robusten HTTP-Aufrufen verwendet werden kann, indem Polly integriert wird.</span><span class="sxs-lookup"><span data-stu-id="21996-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>

<span data-ttu-id="21996-116">[Polly](http://www.thepollyproject.org/) ist eine Bibliothek zur Behandlung vorübergehender Fehler, mit der Entwickler ihren Anwendungen Resilienz hinzufügen können, indem sie einige vordefinierte Richtlinien auf fließende und threadsichere Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="21996-116">[Polly](http://www.thepollyproject.org/) is transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="21996-117">Über HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="21996-117">What is HttpClientFactory</span></span>

<span data-ttu-id="21996-118">`HttpClientFactory` wurde für Folgendes entwickelt:</span><span class="sxs-lookup"><span data-stu-id="21996-118">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="21996-119">Bereitstellen eines zentralen Orts für das Benennen und Konfigurieren logischer `HttpClient`-Objekte.</span><span class="sxs-lookup"><span data-stu-id="21996-119">Provide a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="21996-120">Sie können beispielsweise einen Client (Dienst-Agent) konfigurieren, der für das Zugreifen auf einen bestimmten Microservice vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="21996-120">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="21996-121">Für das Umsetzen des Konzepts der ausgehenden Middleware über delegierende Handler in `HttpClient` in Code sowie für das Implementieren von Polly-basierter Middleware, um die Polly-Richtlinien für die Resilienz zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="21996-121">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="21996-122">`HttpClient` enthält bereits das Konzept, Handler zu delegieren, die für ausgehende HTTP-Anforderungen miteinander verknüpft werden könnten.</span><span class="sxs-lookup"><span data-stu-id="21996-122">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="21996-123">Sie registrieren HTTP-Clients in der Factory und können einen Polly-Handler verwenden, um Polly-Richtlinien für Wiederholungen, CircuitBreakers usw. verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="21996-123">You register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="21996-124">Für das Verwalten der Lebensdauer von `HttpClientMessageHandlers`-Meldungshandlern, um die erwähnten Probleme zu vermeiden, die auftreten können, wenn Sie die `HttpClient`-Lebensdauer selbst verwalten.</span><span class="sxs-lookup"><span data-stu-id="21996-124">Manage the lifetime of `HttpClientMessageHandlers` to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="21996-125">`HttpClientFactory` ist eng an die Implementierung der Abhängigkeitseinschleusung im NuGet-Paket `Microsoft.Extensions.DependencyInjection` gebunden.</span><span class="sxs-lookup"><span data-stu-id="21996-125">`HttpClientFactory` is tightly tied to the dependency injection (DI) implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="21996-126">Weitere Informationen zur Verwendung anderer Abhängigkeitseinschleusungscontainer finden Sie in dieser [GitHub-Diskussion](https://github.com/dotnet/extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="21996-126">For more information about using other dependency injection containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="21996-127">Mehrere Verwendungsmöglichkeiten für HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="21996-127">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="21996-128">Es gibt mehrere Methoden, um `HttpClientFactory` in Ihrer Anwendung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="21996-128">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="21996-129">Verwenden Sie `HttpClientFactory` direkt.</span><span class="sxs-lookup"><span data-stu-id="21996-129">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="21996-130">Verwenden Sie benannte Clients.</span><span class="sxs-lookup"><span data-stu-id="21996-130">Use Named Clients</span></span>
- <span data-ttu-id="21996-131">Verwenden Sie typisierte Clients.</span><span class="sxs-lookup"><span data-stu-id="21996-131">Use Typed Clients</span></span>
- <span data-ttu-id="21996-132">Verwenden Sie generierte Clients.</span><span class="sxs-lookup"><span data-stu-id="21996-132">Use Generated Clients</span></span>

<span data-ttu-id="21996-133">Aus Gründen der Übersichtlichkeit zeigt diese Anleitung die strukturierteste Art der Verwendung von `HttpClientFactory`, also die Verwendung von typisierten Clients (Dienst-Agent-Muster).</span><span class="sxs-lookup"><span data-stu-id="21996-133">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="21996-134">Allerdings sind alle Optionen dokumentiert und werden zurzeit in diesem [Artikel zur Verwendung von HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="21996-134">However, all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="21996-135">Verwenden von typisierten Clients mit HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="21996-135">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="21996-136">Was ist ein „typisierter Client“?</span><span class="sxs-lookup"><span data-stu-id="21996-136">So, what's a "Typed Client"?</span></span> <span data-ttu-id="21996-137">Es ist einfach ein `HttpClient`, der konfiguriert wird, nachdem er von `DefaultHttpClientFactory` injiziert worden ist.</span><span class="sxs-lookup"><span data-stu-id="21996-137">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="21996-138">Im folgenden Diagramm wird veranschaulicht, wie typisierte Clients mit `HttpClientFactory` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="21996-138">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![Diagramm, das zeigt, wie typisierte Clients mit HttpClientFactory verwendet werden.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="21996-140">**Abbildung 8-4.**</span><span class="sxs-lookup"><span data-stu-id="21996-140">**Figure 8-4**.</span></span> <span data-ttu-id="21996-141">Verwenden von HttpClientFactory mit Klassen typisierter Clients.</span><span class="sxs-lookup"><span data-stu-id="21996-141">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="21996-142">In der obigen Abbildung verwendet ein (von einem Controller oder Clientcode verwendeter) ClientService einen `HttpClient`, der von der registrierten `IHttpClientFactory` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="21996-142">In the above image, a ClientService (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="21996-143">Diese Factory weist den `HttpClient` einem `HttpMessageHandler` aus einem Pool zu, den sie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="21996-143">This factory assigns the `HttpClient` an `HttpMessageHandler` from a pool it manages.</span></span> <span data-ttu-id="21996-144">Der `HttpClient` kann bei Registrierung der `IHttpClientFactory` im DI-Container mit der Erweiterungsmethode `AddHttpClient` mit Pollys Richtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="21996-144">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method `AddHttpClient`.</span></span>

<span data-ttu-id="21996-145">Um die obige Struktur zu konfigurieren, fügen Sie `HttpClientFactory` in Ihrer Anwendung hinzu, indem Sie das NuGet-Paket `Microsoft.Extensions.Http` installieren, das die `AddHttpClient()`-Erweiterungsmethode für `IServiceCollection` beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="21996-145">To configure the above structure, add `HttpClientFactory` in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="21996-146">Diese Erweiterungsmethode registriert `DefaultHttpClientFactory` für die Verwendung als Singleton für die Schnittstelle `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="21996-146">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="21996-147">Dadurch wird eine temporäre Konfiguration für `HttpMessageHandlerBuilder` definiert.</span><span class="sxs-lookup"><span data-stu-id="21996-147">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="21996-148">Dieser Meldungshandler (`HttpMessageHandler`-Objekt), der aus einem Pool abgerufen wurde, wird von dem `HttpClient`-Objekt verwendet, das von der Factory zurückgegebenen wird.</span><span class="sxs-lookup"><span data-stu-id="21996-148">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="21996-149">Im nächsten Codeausschnitt wird veranschaulicht, wie `AddHttpClient()` verwendet werden kann, um typisierte Clients (Dienst-Agents) zu registrieren, die `HttpClient` verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="21996-149">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="21996-150">Wenn Sie die Clientdienste wie im vorherigen Code gezeigt registrieren, erstellt `DefaultClientFactory` einen Standard-`HttpClient` für jeden Dienst.</span><span class="sxs-lookup"><span data-stu-id="21996-150">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="21996-151">Sie können auch eine instanzspezifische Konfiguration in der Registrierung hinzufügen (beispielsweise die Basisadresse konfigurieren und einige Resilienzrichtlinien hinzufügen). Der folgende Code zeigt dies:</span><span class="sxs-lookup"><span data-stu-id="21996-151">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="21996-152">Als Beispiel wird eine der oben aufgeführten Richtlinien im nächsten Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="21996-152">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="21996-153">Weitere Informationen zum Verwenden von Polly finden Sie im [nächsten Artikel](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="21996-153">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="21996-154">HTTPClient-Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="21996-154">HttpClient lifetimes</span></span>

<span data-ttu-id="21996-155">Jedes Mal, wenn Sie ein `HttpClient`-Objekt von der `IHttpClientFactory` abrufen, wird eine neue Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="21996-155">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="21996-156">Aber jeder `HttpClient` verwendet einen `HttpMessageHandler`, der zu einem Pool gehört und von der `IHttpClientFactory` wiederverwendet wird, um den Ressourcenverbrauch zu reduzieren, solange die Lebensdauer des `HttpMessageHandler` nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="21996-156">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="21996-157">Das Zusammenlegen von Handlern ist wünschenswert, da jeder Handler in der Regel über seine eigenen HTTP-Verbindungen verfügt. Das Erstellen von mehr Handlern als notwendig kann zu Verzögerungen bei der Verbindung führen.</span><span class="sxs-lookup"><span data-stu-id="21996-157">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="21996-158">Einige Handler halten Verbindungen auch unbegrenzt offen, was verhindert, dass der Handler auf DNS-Änderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="21996-158">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="21996-159">Die `HttpMessageHandler`-Objekte im Pool haben eine Lebensdauer, die der Zeitspanne entspricht, in der eine `HttpMessageHandler`-Instanz im Pool wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="21996-159">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="21996-160">Der Standardwert beträgt zwei Minuten, kann jedoch für jeden typisierten Client überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="21996-160">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="21996-161">Rufen Sie `SetHandlerLifetime()` auf dem bei der Erstellung des Clients zurückgegebenen `IHttpClientBuilder` auf, um den Wert zu überschreiben, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="21996-161">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="21996-162">Für jeden typisierten Client kann ein eigener Wert für die Lebensdauer des Handlers konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="21996-162">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="21996-163">Legen Sie die Lebensdauer auf `InfiniteTimeSpan` fest, um das Ablaufen des Handlers zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="21996-163">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="21996-164">Implementieren von typisierten Clientklassen, die das injizierte und konfigurierte HttpClient-Objekt verwenden</span><span class="sxs-lookup"><span data-stu-id="21996-164">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="21996-165">Zuvor müssen Sie Ihre typisierten Clientklassen definieren, z.B. die Klassen im Beispielcode („BasketService“, „CatalogService“, „OrderingService“ usw.). Bei einem typisierten Client handelt es sich um eine Klasse, die ein `HttpClient`-Objekt akzeptiert (das über deren Konstruktor injiziert wird) und dieses verwendet, um HTTP-Remotedienste aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="21996-165">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="21996-166">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21996-166">For example:</span></span>

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

<span data-ttu-id="21996-167">Der typisierte Client (im Beispiel „CatalogService“) wird von Dependency Injection (DI) aktiviert. Das bedeutet, dass dieser alle registrierten Dienste (zusätzlich zu HttpClient) im Konstruktor akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="21996-167">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="21996-168">Ein typisierter Client ist im Prinzip ein temporäres Objekt. Das bedeutet, dass eine neue Instanz immer bei Bedarf erstellt wird und dass der Client immer eine neue `HttpClient`-Instanz erhält, wenn er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="21996-168">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="21996-169">Bei den HttpMessageHandler-Objekten im Pool handelt es sich um Objekte, die von mehreren HTTP-Anforderungen wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21996-169">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="21996-170">Verwenden von typisierten Clientklassen</span><span class="sxs-lookup"><span data-stu-id="21996-170">Use your Typed Client classes</span></span>

<span data-ttu-id="21996-171">Nachdem Sie Ihre typisierten Klassen implementiert und bei `AddHttpClient()` registriert haben, können Sie sie überall dort verwenden, wo Dienste durch DI eingeschleust werden können.</span><span class="sxs-lookup"><span data-stu-id="21996-171">Finally, once you have your typed classes implemented and have them registered with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="21996-172">Beispielsweise in Code einer Razor Page-App oder Controllern einer MVC-Web-App, wie im folgenden Code aus eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="21996-172">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="21996-173">Bis zu diesem Punkt führt der Code nur reguläre HTTP-Anforderungen aus. In den folgenden Abschnitten wird jedoch nur durch das Hinzufügen von Richtlinien und das Delegieren von Handlern an Ihre registrierten typisierten Clients erreicht, dass alle von `HttpClient` durchgeführten HTTP-Anforderungen ihr Verhalten unter Berücksichtigung von Stabilitätsrichtlinien anpassen, z.B. Wiederholungen mit exponentiellem Backoff, Circuit Breakers oder andere benutzerdefinierte delegierende Handler für die Implementierung zusätzlicher Sicherheitsfeatures (z.B. Authentifizierungstokens) oder anderer benutzerdefinierter Features.</span><span class="sxs-lookup"><span data-stu-id="21996-173">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21996-174">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="21996-174">Additional resources</span></span>

- <span data-ttu-id="21996-175">**Verwenden von HttpClientFactory in .NET Core**</span><span class="sxs-lookup"><span data-stu-id="21996-175">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="21996-176">**HttpClientFactory-Quellcode im `dotnet/extensions`-GitHub-Repository**</span><span class="sxs-lookup"><span data-stu-id="21996-176">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="21996-177">**Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**</span><span class="sxs-lookup"><span data-stu-id="21996-177">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="21996-178">**Verwenden von HttpClientFactory ohne Abhängigkeitseinschleusung (GitHub-Problem)**</span><span class="sxs-lookup"><span data-stu-id="21996-178">**Using HttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="21996-179">[Zurück](explore-custom-http-call-retries-exponential-backoff.md)
>[Weiter](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="21996-179">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
