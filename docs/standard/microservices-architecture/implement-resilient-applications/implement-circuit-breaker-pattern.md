---
title: Implementieren des Trennschaltermusters
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren des Trennschaltermusters
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: 2c89992c4c60ca7f1085050e6fed4922ecd4d8cc
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106127"
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="f921e-103">Implementieren des Trennschaltermusters</span><span class="sxs-lookup"><span data-stu-id="f921e-103">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="f921e-104">Wie bereits in einem vorherigen Artikel erwähnt wurde, sollten Sie Fehler behandeln, deren Behebung unterschiedlich lange dauern kann. Dies kann beispielsweise der Fall sein, wenn Sie versuchen, sich mit einem Remote-Dienst oder einer Remote-Ressource zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="f921e-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="f921e-105">Die Behandlung derartiger Fehler kann die Stabilität und Robustheit einer Anwendung erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f921e-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="f921e-106">In einer verteilten Umgebung können Aufrufe von Remote-Ressourcen und -Diensten fehlschlagen, wenn vorübergehende Fehler wie langsame Netzwerkverbindungen und Timeouts auftreten oder wenn Ressourcen zu langsam oder vorübergehend nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f921e-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="f921e-107">Diese Fehler werden in der Regel nach kurzer Zeit korrigiert, und eine robuste Cloudanwendung sollte diese durch eine Strategie wie das Wiederholungsmuster behandeln können.</span><span class="sxs-lookup"><span data-stu-id="f921e-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="f921e-108">Es gibt jedoch auch Situationen, in denen Fehler aufgrund unerwarteter Ereignisse auftreten. Die Behebung dieser Fehler kann deutlich mehr Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="f921e-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="f921e-109">Zu unterscheiden sind unterschiedliche Schweregrade, die von einem Teilverlust der Konnektivität bis hin zum vollständigen Ausfall des Diensts reichen können.</span><span class="sxs-lookup"><span data-stu-id="f921e-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="f921e-110">In diesen Situationen ist es möglicherweise nicht sinnvoll, wenn eine Anwendung einen Vorgang mehrfach wiederholt, der wahrscheinlich nicht erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f921e-110">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="f921e-111">Stattdessen sollte die Anwendung so programmiert sein, dass ein fehlgeschlagener Vorgang akzeptiert und der Fehler entsprechend behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="f921e-112">Das Wiederholungsmuster hat einen anderen Zweck als das Trennschaltermuster.</span><span class="sxs-lookup"><span data-stu-id="f921e-112">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="f921e-113">Ersteres ermöglicht es einer Anwendung, einen Vorgang erneut auszuführen, wobei davon ausgegangen wird, dass dieser irgendwann erfolgreich sein wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-113">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="f921e-114">Letzteres hindert eine Anwendung daran, einen Vorgang auszuführen, der vermutlich fehlschlagen wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-114">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="f921e-115">Eine Anwendung kann beide Muster kombinieren, wenn sie das Wiederholungsmuster nutzt, um einen Vorgang über das Trennschaltermuster aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f921e-115">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="f921e-116">Die Wiederholungslogik sollte jedoch Ausnahmen behandeln können, die eventuell von dem Trennschalter zurückgegeben werden, und auf Wiederholungsversuche verzichten, wenn durch den Trennschalter darauf hingewiesen wird, dass ein Fehler nicht vorübergehend ist.</span><span class="sxs-lookup"><span data-stu-id="f921e-116">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="f921e-117">Implementieren eines Trennschaltermusters mit Polly</span><span class="sxs-lookup"><span data-stu-id="f921e-117">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="f921e-118">Ebenso wie für die Implementierung von Wiederholungen wird auch für Trennschalter empfohlen, auf bewährte .NET-Bibliotheken wie Polly zurückzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f921e-118">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="f921e-119">Die eShopOnContainers-Anwendung verwendet die Polly-Richtlinie für Trennschalter bei der Implementierung von HTTP-Wiederholungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="f921e-119">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="f921e-120">Tatsächlich verwendet die Anwendung sogar beide Richtlinien für die Hilfsklasse ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="f921e-120">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="f921e-121">Wenn Sie ein Objekt des Typs ResilientHttpClient für HTTP-Anforderungen (von eShopOnContainers) nutzen, wenden Sie beide Richtlinien an. Sie könnten jedoch auch zusätzliche Richtlinien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f921e-121">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="f921e-122">Der nachfolgende Code für Wiederholungen von HTTP-Aufrufen wird nur insofern geändert, als die Trennschalterrichtlinie der zu verwendenden Richtlinienliste hinzugefügt wird. Dies wird am Ende des folgenden Codeausschnitts gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f921e-122">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="f921e-123">Durch den Code wird dem HTTP-Wrapper eine Richtlinie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f921e-123">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="f921e-124">In der Richtlinie wird ein Trennschalter definiert, der sich „öffnet“, wenn der Code die vorgegebene Anzahl aufeinander folgender Ausnahmen erkennt. Die Anzahl der Ausnahmen (in diesem Fall fünf) wird als der Parameter exceptionsAllowedBeforeBreaking übergeben.</span><span class="sxs-lookup"><span data-stu-id="f921e-124">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="f921e-125">Wenn der Trennschalter geöffnet ist, können keine HTTP-Anforderungen gestellt werden, und eine Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f921e-125">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="f921e-126">Trennschalter sollten auch verwendet werden, um Anforderungen an eine Fallbackinfrastruktur umzuleiten, wenn möglicherweise Probleme bei einer bestimmten Ressource auftreten, die in einer anderen Umgebung als die Clientanwendung oder der Dienst bereitgestellt wird, die/der den HTTP-Aufruf ausführt.</span><span class="sxs-lookup"><span data-stu-id="f921e-126">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="f921e-127">Auf diese Weise kann die Clientanwendung bei einem Ausfall im Datencenter, der nur Back-End-Microservices, nicht aber Clientanwendungen betrifft, Anforderungen an Fallbackdienste umleiten.</span><span class="sxs-lookup"><span data-stu-id="f921e-127">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="f921e-128">Für Polly wird aktuell eine Richtlinie zur Automatisierung dieses [Failoverrichtlinienszenarios](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) geplant.</span><span class="sxs-lookup"><span data-stu-id="f921e-128">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="f921e-129">Anzumerken ist, dass die erwähnten Features nur für Fälle geeignet sind, in denen das Failover mit .NET Code und nicht automatisch von Azure unter Berücksichtigung von Speicherorttransparenz verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-129">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="f921e-130">Verwenden der Hilfsklasse ResilientHttpClient aus eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f921e-130">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="f921e-131">Die Hilfsklasse ResilientHttpClient wird ähnlich verwendet wie die .NET-Klasse HttpClient.</span><span class="sxs-lookup"><span data-stu-id="f921e-131">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="f921e-132">Im folgenden Beispiel aus der eShopOnContainers-MVC-Webanwendung (der OrderingService-Agent-Klasse, die von OrderController verwendet wird) wird das ResilientHttpClient-Objekt über den httpClient-Parameter des Konstruktors eingefügt.</span><span class="sxs-lookup"><span data-stu-id="f921e-132">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="f921e-133">Anschließend werden mit dem Objekt HTTP-Anforderungen gestellt.</span><span class="sxs-lookup"><span data-stu-id="f921e-133">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="f921e-134">Wenn das \_apiClient-Memberobjekt verwendet wird, nutzt es intern die Wrapperklasse mit der Polly-Wiederholungsrichtlinie und der Polly-Trennschalterrichtlinie. Außerdem können alle weiteren gewünschten Richtlinien der Polly-Richtlinienauflistung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f921e-134">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="f921e-135">Testen von Wiederholungen in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f921e-135">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="f921e-136">Sobald Sie die eShopOnContainers-Lösung in einem Docker-Host starten, müssen mehrere Container gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="f921e-136">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="f921e-137">Einige Container wie der SQL Server-Container werden langsamer gestartet und initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f921e-137">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="f921e-138">Dies ist v.a. dann der Fall, wenn Sie die eShopOnContainers-Anwendung zum ersten Mal in Docker bereitstellen, da die Images und die Datenbank eingerichtet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f921e-138">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="f921e-139">Der langsamere Start einiger Container kann dazu führen, dass die anderen Dienste auch dann anfänglich HTTP-Ausnahmen auslösen, wenn Sie, wie in den vorherigen Abschnitten beschrieben, Abhängigkeiten zwischen Containern auf der docker-compose-Ebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="f921e-139">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="f921e-140">Diese docker-compose-Abhängigkeiten zwischen Containern befinden sich nur auf der Prozessebene.</span><span class="sxs-lookup"><span data-stu-id="f921e-140">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="f921e-141">Auch wenn der Einstiegspunktprozess des Containers bereits gestartet wurde, ist SQL Server möglicherweise noch nicht für Abfragen bereit.</span><span class="sxs-lookup"><span data-stu-id="f921e-141">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="f921e-142">Das Ergebnis können zahlreiche Fehler sein. Außerdem wird in der Anwendung möglicherweise eine Ausnahme angezeigt, wenn sie versucht, den Container zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f921e-142">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="f921e-143">Diese Art von Fehler kann auch beim Start angezeigt werden, wenn die Anwendung in der Cloud bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-143">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="f921e-144">In diesem Fall können Orchestratoren einen Container zwischen Knoten oder virtuellen Computern hin- und herschieben (was dem Start neuer Instanzen entspricht), wenn die Anzahl der Container für Clusterknoten ausgeglichen wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-144">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="f921e-145">eShopOnContainers löst dieses Problem mithilfe des Wiederholungsmusters, das bereits beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="f921e-145">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="f921e-146">Dies ist auch der Grund dafür, warum beim Start der Lösung möglicherweise Protokollablaufverfolgungen oder -warnungen wie die Folgende angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="f921e-146">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="f921e-147">**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span><span class="sxs-lookup"><span data-stu-id="f921e-147">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="f921e-148"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\]. (Wiederholung 1 wurde mit Pollys Wiederholungsrichtlinie aus folgendem Grund implementiert: System.Net.Http.HttpRequestException: Beim Senden der Anforderung ist ein Fehler aufgetreten. System.Net.Http.CurlException: Mit dem Server\n bei System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\n konnte keine Verbindung bei [...] hergestellt werden.)</span><span class="sxs-lookup"><span data-stu-id="f921e-148"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="f921e-149">Testen eines Trennschalters in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f921e-149">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="f921e-150">Es gibt mehrere Möglichkeiten, den Trennschalter zu öffnen und ihn auf diese Weise mit eShopOnContainers zu testen.</span><span class="sxs-lookup"><span data-stu-id="f921e-150">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="f921e-151">Eine Option besteht darin, die zulässige Anzahl von Wiederholungen in der Trennschalterrichtlinie auf eins zu reduzieren und die gesamte Lösung erneut in Docker bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f921e-151">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="f921e-152">Bei einem einzelnen Neuversuch ist die Wahrscheinlichkeit hoch, dass die HTTP-Anforderung bei der Bereitstellung fehlschlägt, der Trennschalter geöffnet und eine Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-152">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="f921e-153">Eine weitere Option besteht in der Verwendung benutzerdefinierter Middleware, die im `Basket`-Microservice implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f921e-153">Another option is to use custom middleware that is implemented in the `Basket` microservice.</span></span> <span data-ttu-id="f921e-154">Wenn diese Middleware aktiviert ist, fängt sie alle HTTP-Anforderungen ab und gibt den Statuscode 500 zurück.</span><span class="sxs-lookup"><span data-stu-id="f921e-154">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="f921e-155">Sie können die Middleware aktivieren, indem Sie eine GET-Anforderung an den URI stellen, der den Fehler auslöst. Dabei können Sie z.B. folgende Anforderungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="f921e-155">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="f921e-156">GET /failing</span><span class="sxs-lookup"><span data-stu-id="f921e-156">GET /failing</span></span>

<span data-ttu-id="f921e-157">Diese Anforderung gibt den aktuellen Status der Middleware zurück.</span><span class="sxs-lookup"><span data-stu-id="f921e-157">This request returns the current state of the middleware.</span></span> <span data-ttu-id="f921e-158">Wenn die Middleware aktiviert ist, gibt die Anforderung den Statuscode 500 zurück.</span><span class="sxs-lookup"><span data-stu-id="f921e-158">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="f921e-159">Wenn die Middleware deaktiviert ist, wird keine Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f921e-159">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="f921e-160">GET /failing?enable</span><span class="sxs-lookup"><span data-stu-id="f921e-160">GET /failing?enable</span></span>

<span data-ttu-id="f921e-161">Diese Anforderung aktiviert die Middleware.</span><span class="sxs-lookup"><span data-stu-id="f921e-161">This request enables the middleware.</span></span>

-   <span data-ttu-id="f921e-162">GET /failing?disable</span><span class="sxs-lookup"><span data-stu-id="f921e-162">GET /failing?disable</span></span>

<span data-ttu-id="f921e-163">Diese Anforderung deaktiviert die Middleware.</span><span class="sxs-lookup"><span data-stu-id="f921e-163">This request disables the middleware.</span></span>

<span data-ttu-id="f921e-164">Sobald die Anwendung ausgeführt wird, können Sie z.B. die Middleware aktivieren, indem Sie mit dem unten aufgeführten URI in einem Browser eine Anforderung stellen.</span><span class="sxs-lookup"><span data-stu-id="f921e-164">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="f921e-165">Beachten Sie, dass der Microservice für Bestellungen den Port 5103 verwendet.</span><span class="sxs-lookup"><span data-stu-id="f921e-165">Note that the ordering microservice uses port 5103.</span></span>

http://localhost:5103/failing?enable

<span data-ttu-id="f921e-166">Mit dem URI [http://localhost:5103/failing](http://localhost:5103/failing) können Sie anschließend wie in Abbildung 10-4 dargestellt den Status überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f921e-166">You can then check the status using the URI [http://localhost:5103/failing](http://localhost:5103/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="f921e-167">**Abbildung 10-4.**</span><span class="sxs-lookup"><span data-stu-id="f921e-167">**Figure 10-4**.</span></span> <span data-ttu-id="f921e-168">Überprüfung des „Fehlerstatus“ der ASP.NET-Middleware (hier deaktiviert)</span><span class="sxs-lookup"><span data-stu-id="f921e-168">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="f921e-169">Der Warenkorbmicroservice antwortet bei Aufruf immer mit dem Statuscode 500.</span><span class="sxs-lookup"><span data-stu-id="f921e-169">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="f921e-170">Sobald die Middleware ausgeführt wird, können Sie versuchen, über die MVC-Webanwendung eine Bestellung aufzugeben.</span><span class="sxs-lookup"><span data-stu-id="f921e-170">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="f921e-171">Da die Anforderungen fehlschlagen, wird der Trennschalter geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f921e-171">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="f921e-172">Wie im folgenden Beispiel zu sehen ist, befindet sich in der MVC-Webanwendung ein catch-Block in der Logik zum Aufgeben einer Bestellung.</span><span class="sxs-lookup"><span data-stu-id="f921e-172">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="f921e-173">Wenn im Code eine durch den offenen Trennschalter ausgelöste Ausnahme abgefangen wird, erhält der Benutzer eine Wartebenachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="f921e-173">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

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

<span data-ttu-id="f921e-174">Die durch den Code ausgelösten Schritte werden im Folgenden kurz zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="f921e-174">Here’s a summary.</span></span> <span data-ttu-id="f921e-175">Die Wiederholungsrichtlinie versucht mehrmals, HTTP-Anforderungen zu stellen, was zu HTTP-Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="f921e-175">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="f921e-176">Wenn die maximale Anzahl der Versuche erreicht wird, die für die Trennschalterrichtlinie festgelegt wurde (in diesem Fall 5), löst die Anwendung eine BrokenCircuitException aus.</span><span class="sxs-lookup"><span data-stu-id="f921e-176">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="f921e-177">Das Ergebnis ist eine Benutzerbenachrichtigung (s. Abbildung 10-5).</span><span class="sxs-lookup"><span data-stu-id="f921e-177">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="f921e-178">**Abbildung 10-5.**</span><span class="sxs-lookup"><span data-stu-id="f921e-178">**Figure 10-5**.</span></span> <span data-ttu-id="f921e-179">Trennschalter, der einen Fehler zurückgibt, der auf der Benutzeroberfläche angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="f921e-179">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="f921e-180">Sie können unterschiedliche Logiken für das Öffnen des Trennschalters festlegen.</span><span class="sxs-lookup"><span data-stu-id="f921e-180">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="f921e-181">Alternativ können Sie auch eine HTTP-Anforderung an einen anderen Back-End-Microservice stellen, falls ein Fallbackdatencenter oder ein redundantes Back-End-System vorliegt.</span><span class="sxs-lookup"><span data-stu-id="f921e-181">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="f921e-182">Eine weitere Möglichkeit für die Implementierung von CircuitBreakerPolicy ist die Verwendung der Isolate-Methode (die die Öffnung des Trennschalters erzwingt und dafür sorgt, dass er geöffnet bleibt) und der Reset-Methode (die den Trennschalter wieder schließt).</span><span class="sxs-lookup"><span data-stu-id="f921e-182">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="f921e-183">Diese können für die Erstellung eines Hilfs-HTTP-Endpunkts verwendet werden, der Isolate und Reset direkt in der Richtlinie aufruft.</span><span class="sxs-lookup"><span data-stu-id="f921e-183">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="f921e-184">Ein derartiger HTTP-Endpunkt kann auch, falls er entsprechend gesichert ist, in einer Produktionsumgebung verwendet werden, um ein Downstreamsystem beispielsweise bei einem Upgrade vorübergehend zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="f921e-184">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="f921e-185">Alternativ könnte er den Trennschalter manuell auslösen, um ein Downstreamsystem zu schützen, das möglicherweise fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="f921e-185">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="f921e-186">Hinzufügen einer Jitterstrategie zur Wiederholungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f921e-186">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="f921e-187">Eine reguläre Wiederholungsrichtlinie kann ein System negativ beeinflussen, falls hohe Parallelität, hohe Skalierbarkeit und ein hohes Konfliktpotenzial vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f921e-187">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="f921e-188">Um mit Spitzenlasten umgehen zu können, die bei ähnlichen Wiederholungsanforderungen von vielen Clients bei einem Teilausfall auftreten, empfiehlt es sich als Notlösung, den Wiederholungsalgorithmus oder die Wiederholungsrichtlinie um eine Jitterstrategie zu ergänzen.</span><span class="sxs-lookup"><span data-stu-id="f921e-188">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="f921e-189">Wenn für den exponentiellen Backoff der Jitter zufällig festgelegt wird, kann dies die Gesamtleistung des End-to-End-Systems verbessern.</span><span class="sxs-lookup"><span data-stu-id="f921e-189">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="f921e-190">Dadurch lassen sich beim Auftreten von Problemen Lastspitzen verteilen.</span><span class="sxs-lookup"><span data-stu-id="f921e-190">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="f921e-191">Wenn Sie Polly verwenden, könnte der Code zum Implementieren des Jitters wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f921e-191">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="f921e-192">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f921e-192">Additional resources</span></span>

-   <span data-ttu-id="f921e-193">**Retry pattern (Wiederholungsmuster)**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="f921e-193">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="f921e-194">**Connection Resiliency (Verbindungsresilienz)** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="f921e-194">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="f921e-195">**Polly** (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung vorübergehender Fehler) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="f921e-195">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="f921e-196">**Circuit Breaker pattern (Muster „Trennschalter“)**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="f921e-196">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="f921e-197">**Marc Brooker. Jitter: Making Things Better With Randomness (Jitter: Dinge durch Zufall verbessern)** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="f921e-197">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f921e-198">[Zurück](implement-http-call-retries-exponential-backoff-polly.md)
[Weiter](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="f921e-198">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
