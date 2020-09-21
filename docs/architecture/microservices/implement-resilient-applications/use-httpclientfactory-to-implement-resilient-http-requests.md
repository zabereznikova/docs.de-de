---
title: Verwenden von IHttpClientFactory zur Implementierung robuster HTTP-Anforderungen
description: Erfahren Sie, wie Sie IHttpClientFactory, verfügbar seit .NET Core 2.1, zum Erstellen von `HttpClient`-Instanzen verwenden, damit Sie es mühelos in Ihren Anwendungen verwenden können.
ms.date: 08/31/2020
ms.openlocfilehash: c54965a9bbb700cfb1f14150773c2df45d109c39
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678815"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="0ebe1-103">Verwenden von IHttpClientFactory zur Implementierung robuster HTTP-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ebe1-103">Use IHttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="0ebe1-104"><xref:System.Net.Http.IHttpClientFactory> ist ein Vertrag, der von `DefaultHttpClientFactory`, einer Factory, die seit .NET Core 2.1 für das Erstellen von <xref:System.Net.Http.HttpClient>-Instanzen verfügbar ist, die in Ihren Anwendungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-104"><xref:System.Net.Http.IHttpClientFactory> is a contract implemented by `DefaultHttpClientFactory`, an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="0ebe1-105">Probleme mit den ursprünglichen HttpClient-Klassen von .NET Core</span><span class="sxs-lookup"><span data-stu-id="0ebe1-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="0ebe1-106">Die ursprüngliche und bekannte <xref:System.Net.Http.HttpClient>-Klasse kann problemlos verwendet werden, allerdings wird sie von vielen Entwicklern in einigen Fällen nicht richtig verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="0ebe1-107">Obwohl diese Klasse `IDisposable` implementiert, wird die Deklaration und Instanziierung innerhalb einer `using`-Anweisung nicht bevorzugt, da beim Verwerfen des `HttpClient`-Objekts der zugrunde liegende Socket nicht sofort freigegeben wird, was zur _Erschöpfung von Sockets_ führen kann.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-107">Though this class implements `IDisposable`, declaring and instantiating it within a `using` statement is not preferred because when the `HttpClient` object gets disposed of, the underlying socket is not immediately released, which can lead to a _socket exhaustion_ problem.</span></span> <span data-ttu-id="0ebe1-108">Weitere Informationen zu diesem Problem finden Sie im Blogbeitrag [You're using HttpClient wrong and it is destabilizing your software (Sie verwenden HttpClient falsch und destabilisieren dadurch Ihre Software)](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="0ebe1-108">For more information about this issue, see the blog post [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span></span>

<span data-ttu-id="0ebe1-109">Deshalb sollte `HttpClient` einmal instanziiert und während der Lebensdauer einer Anwendung wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="0ebe1-110">Das Instanziieren einer `HttpClient`-Klasse für jede Anforderung erschöpft die Anzahl der verfügbaren Sockets und führt zu hoher Auslastung.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="0ebe1-111">Dieses Problem führt zu `SocketException`-Fehlern.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="0ebe1-112">Mögliche Ansätze zur Lösung dieses Problems basieren auf der Erstellung des `HttpClient`-Objekts als Singleton-Objekt oder statisches Objekt. Dies wird in diesem [Microsoft-Artikel zur Verwendung von HttpClient](../../../csharp/tutorials/console-webapiclient.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span> <span data-ttu-id="0ebe1-113">Das kann eine gute Lösung für kurzlebige Konsolen-Apps o. ä. sein, die mehrmals am Tag ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-113">This can be a good solution for short-lived console apps or similar, that run a few times a day.</span></span>

<span data-ttu-id="0ebe1-114">Ein weiteres Problem, auf das Entwickler stoßen, ist die Verwendung einer gemeinsam genutzten Instanz von `HttpClient` in zeitintensiven Prozessen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-114">Another issue that developers run into is when using a shared instance of `HttpClient` in long-running processes.</span></span> <span data-ttu-id="0ebe1-115">In einer Situation, in der der HttpClient als Singleton oder statisches Objekt instanziiert wird, kann er die DNS-Änderungen nicht wie in dieser [Ausgabe](https://github.com/dotnet/runtime/issues/18348) des GitHub-Repositorys „dotnet/runtime“ beschrieben behandeln.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-115">In a situation where the HttpClient is instantiated as a singleton or a static object, it fails to handle the DNS changes as described in this [issue](https://github.com/dotnet/runtime/issues/18348) of the dotnet/runtime GitHub repository.</span></span>

<span data-ttu-id="0ebe1-116">Es geht jedoch nicht wirklich um `HttpClient` an sich, sondern um den [Standardkonstruktor für HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), da er eine neue konkrete Instanz von <xref:System.Net.Http.HttpMessageHandler> erstellt, die die oben erwähnten Probleme mit der *Erschöpfung der Sockets* und den DNS-Änderungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-116">However, the issue isn't really with `HttpClient` per se, but with the [default constructor for HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), because it creates a new concrete instance of <xref:System.Net.Http.HttpMessageHandler>, which is the one that has *sockets exhaustion* and DNS changes issues mentioned above.</span></span>

<span data-ttu-id="0ebe1-117">Um die oben genannten Probleme zu lösen und `HttpClient`-Instanzen verwaltbar zu gestalten, wurde in .NET Core 2.1 die <xref:System.Net.Http.IHttpClientFactory>-Schnittstelle eingeführt, die zur Konfiguration und Erstellung von `HttpClient`-Instanzen in einer App durch Abhängigkeitsinjektion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-117">To address the issues mentioned above and to make `HttpClient` instances manageable, .NET Core 2.1 introduced the <xref:System.Net.Http.IHttpClientFactory> interface which can be used to configure and create `HttpClient` instances in an app through Dependency Injection (DI).</span></span> <span data-ttu-id="0ebe1-118">Sie bietet auch Erweiterungen für auf Polly basierende Middleware, um die Vorteile der delegierenden Handler in HttpClient zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-118">It also provides extensions for Polly-based middleware to take advantage of delegating handlers in HttpClient.</span></span>

<span data-ttu-id="0ebe1-119">[Polly](http://www.thepollyproject.org/) ist eine Bibliothek zur Behandlung vorübergehender Fehler, mit der Entwickler ihren Anwendungen Resilienz hinzufügen können, indem sie einige vordefinierte Richtlinien auf fließende und threadsichere Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-119">[Polly](http://www.thepollyproject.org/) is a transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="benefits-of-using-ihttpclientfactory"></a><span data-ttu-id="0ebe1-120">Vorteile der Verwendung von IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="0ebe1-120">Benefits of using IHttpClientFactory</span></span>

<span data-ttu-id="0ebe1-121">Die derzeitige Implementierung von <xref:System.Net.Http.IHttpClientFactory>, die auch <xref:System.Net.Http.IHttpMessageHandlerFactory> implementiert, bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-121">The current implementation of <xref:System.Net.Http.IHttpClientFactory>, that also implements <xref:System.Net.Http.IHttpMessageHandlerFactory>, offers the following benefits:</span></span>

- <span data-ttu-id="0ebe1-122">Bereitstellen eines zentralen Orts für das Benennen und Konfigurieren logischer `HttpClient`-Objekte.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-122">Provides a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="0ebe1-123">Sie können beispielsweise einen Client (Dienst-Agent) konfigurieren, der für das Zugreifen auf einen bestimmten Microservice vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-123">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="0ebe1-124">Für das Umsetzen des Konzepts der ausgehenden Middleware über delegierende Handler in `HttpClient` in Code sowie für das Implementieren von Polly-basierter Middleware, um die Polly-Richtlinien für die Resilienz zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-124">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly's policies for resiliency.</span></span>
- <span data-ttu-id="0ebe1-125">`HttpClient` enthält bereits das Konzept, Handler zu delegieren, die für ausgehende HTTP-Anforderungen miteinander verknüpft werden könnten.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-125">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="0ebe1-126">Sie können HTTP-Clients in der Factory registrieren und einen Polly-Handler verwenden, um Polly-Richtlinien für Wiederholungen, CircuitBreakers usw. verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-126">You can register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="0ebe1-127">Für das Verwalten der Lebensdauer von <xref:System.Net.Http.HttpMessageHandler>-Meldungshandlern, um die erwähnten Probleme zu vermeiden, die auftreten können, wenn Sie die `HttpClient`-Lebensdauer selbst verwalten.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-127">Manage the lifetime of <xref:System.Net.Http.HttpMessageHandler> to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!TIP]
> <span data-ttu-id="0ebe1-128">Die von der Abhängigkeitsinjektion eingefügten `HttpClient`-Instanzen können sicher verworfen werden, da das zugehörige `HttpMessageHandler` von der Factory verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-128">The `HttpClient` instances injected by DI, can be disposed of safely, because the associated `HttpMessageHandler` is managed by the factory.</span></span> <span data-ttu-id="0ebe1-129">Tatsächlich werden eingefügte `HttpClient`-Instanzen aus Sicht der Abhängigkeitsinjektion auf einen *Bereich bezogen*.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-129">As a matter of fact, injected `HttpClient` instances are *Scoped* from a DI perspective.</span></span>

> [!NOTE]
> <span data-ttu-id="0ebe1-130">Die Implementierung von `IHttpClientFactory` (`DefaultHttpClientFactory`) ist eng an die Implementierung der Abhängigkeitsinjektion im NuGet-Paket `Microsoft.Extensions.DependencyInjection` gebunden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-130">The implementation of `IHttpClientFactory` (`DefaultHttpClientFactory`) is tightly tied to the DI implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="0ebe1-131">Weitere Informationen zur Verwendung anderer Container für die Abhängigkeitsinjektion finden Sie in dieser [GitHub-Diskussion](https://github.com/dotnet/extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="0ebe1-131">For more information about using other DI containers, see this [GitHub discussion](https://github.com/dotnet/extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-ihttpclientfactory"></a><span data-ttu-id="0ebe1-132">Mehrere Verwendungsmöglichkeiten für IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="0ebe1-132">Multiple ways to use IHttpClientFactory</span></span>

<span data-ttu-id="0ebe1-133">Es gibt mehrere Methoden, um `IHttpClientFactory` in Ihrer Anwendung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-133">There are several ways that you can use `IHttpClientFactory` in your application:</span></span>

- <span data-ttu-id="0ebe1-134">Grundlegende Verwendung</span><span class="sxs-lookup"><span data-stu-id="0ebe1-134">Basic usage</span></span>
- <span data-ttu-id="0ebe1-135">Verwenden Sie benannte Clients.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-135">Use Named Clients</span></span>
- <span data-ttu-id="0ebe1-136">Verwenden Sie typisierte Clients.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-136">Use Typed Clients</span></span>
- <span data-ttu-id="0ebe1-137">Verwenden Sie generierte Clients.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-137">Use Generated Clients</span></span>

<span data-ttu-id="0ebe1-138">Aus Gründen der Übersichtlichkeit zeigt diese Anleitung die strukturierteste Art der Verwendung von `IHttpClientFactory`, also die Verwendung von typisierten Clients (Dienst-Agent-Muster).</span><span class="sxs-lookup"><span data-stu-id="0ebe1-138">For the sake of brevity, this guidance shows the most structured way to use `IHttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="0ebe1-139">Allerdings sind alle Optionen dokumentiert und werden zurzeit in diesem [Artikel zur Verwendung von `IHttpClientFactory`](/aspnet/core/fundamentals/http-requests#consumption-patterns) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-139">However, all options are documented and are currently listed in this [article covering the `IHttpClientFactory` usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a><span data-ttu-id="0ebe1-140">Verwenden von typisierten Clients mit IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="0ebe1-140">How to use Typed Clients with IHttpClientFactory</span></span>

<span data-ttu-id="0ebe1-141">Was ist ein „typisierter Client“?</span><span class="sxs-lookup"><span data-stu-id="0ebe1-141">So, what's a "Typed Client"?</span></span> <span data-ttu-id="0ebe1-142">Es ist nur ein `HttpClient`, der für eine bestimmte Verwendung vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-142">It's just an `HttpClient` that's pre-configured for some specific use.</span></span> <span data-ttu-id="0ebe1-143">Diese Konfiguration kann bestimmte Werte wie den Basisserver, HTTP-Header oder Timeouts enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-143">This configuration can include specific values such as the base server, HTTP headers or time outs.</span></span>

<span data-ttu-id="0ebe1-144">Im folgenden Diagramm wird veranschaulicht, wie typisierte Clients mit `IHttpClientFactory` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-144">The following diagram shows how Typed Clients are used with `IHttpClientFactory`:</span></span>

![Diagramm, das zeigt, wie typisierte Clients mit IHttpClientFactory verwendet werden.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="0ebe1-146">**Abbildung 8-4.**</span><span class="sxs-lookup"><span data-stu-id="0ebe1-146">**Figure 8-4**.</span></span> <span data-ttu-id="0ebe1-147">Verwenden von `IHttpClientFactory` mit typisierten Clientklassen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-147">Using `IHttpClientFactory` with Typed Client classes.</span></span>

<span data-ttu-id="0ebe1-148">In der obigen Abbildung verwendet ein (von einem Controller oder Clientcode verwendeter) `ClientService` einen `HttpClient`, der von der registrierten `IHttpClientFactory` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-148">In the above image, a `ClientService` (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="0ebe1-149">Diese Factory weist einen `HttpMessageHandler` aus einem Pool dem `HttpClient` zu.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-149">This factory assigns an `HttpMessageHandler` from a pool to the `HttpClient`.</span></span> <span data-ttu-id="0ebe1-150">Der `HttpClient` kann bei Registrierung der `IHttpClientFactory` im DI-Container mit der Erweiterungsmethode <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> mit Pollys Richtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-150">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>.</span></span>

<span data-ttu-id="0ebe1-151">Um die obige Struktur zu konfigurieren, fügen Sie <xref:System.Net.Http.IHttpClientFactory> in Ihrer Anwendung hinzu, indem Sie das NuGet-Paket `Microsoft.Extensions.Http` installieren, das die <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A>-Erweiterungsmethode für <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-151">To configure the above structure, add <xref:System.Net.Http.IHttpClientFactory> in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient%2A> extension method for <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="0ebe1-152">Diese Erweiterungsmethode registriert die interne `DefaultHttpClientFactory`-Klasse für die Verwendung als Singleton für die Schnittstelle `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-152">This extension method registers the internal `DefaultHttpClientFactory` class to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="0ebe1-153">Dadurch wird eine temporäre Konfiguration für <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder> definiert.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-153">It defines a transient configuration for the <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>.</span></span> <span data-ttu-id="0ebe1-154">Dieser Meldungshandler (<xref:System.Net.Http.HttpMessageHandler>-Objekt), der aus einem Pool abgerufen wurde, wird von dem `HttpClient`-Objekt verwendet, das von der Factory zurückgegebenen wird.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-154">This message handler (<xref:System.Net.Http.HttpMessageHandler> object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="0ebe1-155">Im nächsten Codeausschnitt wird veranschaulicht, wie `AddHttpClient()` verwendet werden kann, um typisierte Clients (Dienst-Agents) zu registrieren, die `HttpClient` verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-155">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="0ebe1-156">Wenn Sie die Clientdienste wie im vorherigen Code gezeigt registrieren, erstellt `DefaultClientFactory` einen Standard-`HttpClient` für jeden Dienst.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-156">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="0ebe1-157">Sie können auch eine instanzspezifische Konfiguration in der Registrierung hinzufügen (beispielsweise die Basisadresse konfigurieren und einige Resilienzrichtlinien hinzufügen). Der folgende Code zeigt dies:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-157">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="0ebe1-158">Als Beispiel wird eine der oben aufgeführten Richtlinien im nächsten Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-158">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="0ebe1-159">Weitere Informationen zum Verwenden von Polly finden Sie im [nächsten Artikel](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="0ebe1-159">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="0ebe1-160">HTTPClient-Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="0ebe1-160">HttpClient lifetimes</span></span>

<span data-ttu-id="0ebe1-161">Jedes Mal, wenn Sie ein `HttpClient`-Objekt von der `IHttpClientFactory` abrufen, wird eine neue Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-161">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="0ebe1-162">Aber jeder `HttpClient` verwendet einen `HttpMessageHandler`, der zu einem Pool gehört und von der `IHttpClientFactory` wiederverwendet wird, um den Ressourcenverbrauch zu reduzieren, solange die Lebensdauer des `HttpMessageHandler` nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-162">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="0ebe1-163">Das Zusammenlegen von Handlern ist wünschenswert, da jeder Handler in der Regel über seine eigenen HTTP-Verbindungen verfügt. Das Erstellen von mehr Handlern als notwendig kann zu Verzögerungen bei der Verbindung führen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-163">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="0ebe1-164">Einige Handler halten Verbindungen auch unbegrenzt offen, was verhindert, dass der Handler auf DNS-Änderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-164">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="0ebe1-165">Die `HttpMessageHandler`-Objekte im Pool haben eine Lebensdauer, die der Zeitspanne entspricht, in der eine `HttpMessageHandler`-Instanz im Pool wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-165">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="0ebe1-166">Der Standardwert beträgt zwei Minuten, kann jedoch für jeden typisierten Client überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-166">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="0ebe1-167">Rufen Sie `SetHandlerLifetime()` auf dem bei der Erstellung des Clients zurückgegebenen <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> auf, um den Wert zu überschreiben, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-167">To override it, call `SetHandlerLifetime()` on the <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder> that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="0ebe1-168">Für jeden typisierten Client kann ein eigener Wert für die Lebensdauer des Handlers konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-168">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="0ebe1-169">Legen Sie die Lebensdauer auf `InfiniteTimeSpan` fest, um das Ablaufen des Handlers zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-169">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="0ebe1-170">Implementieren von typisierten Clientklassen, die das injizierte und konfigurierte HttpClient-Objekt verwenden</span><span class="sxs-lookup"><span data-stu-id="0ebe1-170">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="0ebe1-171">Zuvor müssen Sie Ihre typisierten Clientklassen definieren, z. B. die Klassen im Beispielcode („BasketService“, „CatalogService“, „OrderingService“ usw.). Bei einem typisierten Client handelt es sich um eine Klasse, die ein `HttpClient`-Objekt akzeptiert (das über deren Konstruktor injiziert wird) und dieses verwendet, um HTTP-Remotedienste aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-171">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like 'BasketService', 'CatalogService', 'OrderingService', etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="0ebe1-172">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-172">For example:</span></span>

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

<span data-ttu-id="0ebe1-173">Der typisierte Client (`CatalogService` im Beispiel) wird von der Abhängigkeitsinjektion aktiviert. Das bedeutet, dass dieser alle registrierten Dienste (zusätzlich zu `HttpClient`) im Konstruktor akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-173">The Typed Client (`CatalogService` in the example) is activated by DI (Dependency Injection), that means it can accept any registered service in its constructor, in addition to `HttpClient`.</span></span>

<span data-ttu-id="0ebe1-174">Ein typisierter Client ist ein temporäres Objekt. Das bedeutet, dass immer dann eine neue Instanz erstellt wird, wenn eine benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-174">A Typed Client is effectively a transient object, that means a new instance is created each time one is needed.</span></span> <span data-ttu-id="0ebe1-175">Bei jeder Konstruktion wird also eine neue `HttpClient`-Instanz empfangen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-175">It receives a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="0ebe1-176">Die `HttpMessageHandler`-Objekte im Pool sind jedoch die Objekte, die von mehreren `HttpClient`-Instanzen wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-176">However, the `HttpMessageHandler` objects in the pool are the objects that are reused by multiple `HttpClient` instances.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="0ebe1-177">Verwenden von typisierten Clientklassen</span><span class="sxs-lookup"><span data-stu-id="0ebe1-177">Use your Typed Client classes</span></span>

<span data-ttu-id="0ebe1-178">Nachdem Sie Ihre typisierten Klassen implementiert haben, können Sie sie registrieren und mit `AddHttpClient()` konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-178">Finally, once you have your typed classes implemented, you can have them registered and configured with `AddHttpClient()`.</span></span> <span data-ttu-id="0ebe1-179">Anschließend können Sie sie überall dort verwenden, wo Dienste mithilfe von DI eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-179">After that you can use them wherever have services injected by DI.</span></span> <span data-ttu-id="0ebe1-180">Beispielsweise in Code einer Razor Page-App oder Controllern einer MVC-Web-App, wie im folgenden Code aus eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="0ebe1-180">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="0ebe1-181">Bis zu diesem Punkt hat der obige Codeausschnitt nur das Beispiel zum Ausführen regulärer HTTP-Anforderungen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-181">Up to this point, the above code snippet has only shown the example of performing regular HTTP requests.</span></span> <span data-ttu-id="0ebe1-182">In den folgenden Abschnitten wird jedoch gezeigt, wie alle HTTP-Anforderungen von `HttpClient` mit resilienten Richtlinien wie Wiederholungen mit exponentiellem Backoff, Circuit Breakern, Sicherheitsfeatures mit Authentifizierungstokens oder beliebigen benutzerdefinierten Features kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-182">But the 'magic' comes in the following sections where it shows how all the HTTP requests made by `HttpClient`, can have resilient policies such as retries with exponential backoff, circuit breakers, security features using auth tokens, or even any other custom feature.</span></span> <span data-ttu-id="0ebe1-183">Hierfür müssen Sie nur Richtlinien hinzufügen und den registrierten typisierten Clients Handler zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0ebe1-183">And all of these can be done just by adding policies and delegating handlers to your registered Typed Clients.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ebe1-184">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0ebe1-184">Additional resources</span></span>

- <span data-ttu-id="0ebe1-185">**Verwenden von HttpClientFactory in .NET Core**</span><span class="sxs-lookup"><span data-stu-id="0ebe1-185">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="0ebe1-186">**HttpClientFactory-Quellcode im `dotnet/extensions`-GitHub-Repository**</span><span class="sxs-lookup"><span data-stu-id="0ebe1-186">**HttpClientFactory source code in the `dotnet/extensions` GitHub repository**</span></span>  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="0ebe1-187">**Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**</span><span class="sxs-lookup"><span data-stu-id="0ebe1-187">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="0ebe1-188">**Verwenden von IHttpClientFactory ohne Abhängigkeitsinjektion (GitHub-Problem)**</span><span class="sxs-lookup"><span data-stu-id="0ebe1-188">**Using IHttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="0ebe1-189">[Zurück](implement-resilient-entity-framework-core-sql-connections.md)
>[Weiter](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="0ebe1-189">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
