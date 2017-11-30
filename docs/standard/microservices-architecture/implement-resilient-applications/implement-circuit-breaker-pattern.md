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
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="e1b6f-104">Implementieren einen Trennschalter</span><span class="sxs-lookup"><span data-stu-id="e1b6f-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="e1b6f-105">Wie bereits erwähnt, sollten Sie Fehler behandeln, die in Anspruch eine Variable Menge an Zeit nehmen können aus, der wiederhergestellt werden soll, wie möglicherweise auftreten, wenn Sie versuchen, eine Verbindung mit einer remote-Dienst oder eine Ressource.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="e1b6f-106">Diese Art von Fehler zu behandeln, kann die Stabilität und Stabilität von einer Anwendung verbessern.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="e1b6f-107">In einer verteilten Umgebung können Aufrufe von remote-Ressourcen und Dienste zu einem Fehler aufgrund von vorübergehenden Fehlern, z. B. langsame Verbindungen und Timeouts verursacht, oder wenn Ressourcen werden langsam oder vorübergehend nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="e1b6f-108">Diese Fehler korrigieren selbst in der Regel nach kurzer Zeit ein, und eine robusten Cloud-Anwendung zu deren Behandlung durch eine Strategie wie die Wiederholung (Muster) vorbereitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="e1b6f-109">Allerdings möglich gibt es auch Situationen, in denen Fehler aufgrund unerwarteter Ereignisse sind, die beheben wesentlich länger dauern.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="e1b6f-110">Diese Fehler können in Schweregrad aus einem teilweise Verlust der Verbindung abgeschlossen bei Ausfall eines Diensts im Bereich.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="e1b6f-111">In diesen Situationen ist es möglicherweise nicht sinnvoll, damit eine Anwendung ständig einen Vorgang zu wiederholen, der wahrscheinlich nicht erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="e1b6f-112">Stattdessen sollte die Anwendung codiert werden, um annehmen, dass der Vorgang fehlgeschlagen ist und den Fehler entsprechend zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="e1b6f-113">Einen Trennschalter wurde einen anderen Zweck als die Wiederholung (Muster).</span><span class="sxs-lookup"><span data-stu-id="e1b6f-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="e1b6f-114">Die Wiederholung (Muster) kann eine Anwendung einen Vorgang in der Annahme zu wiederholen, die der Vorgang schließlich erfolgreich sein wird.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="e1b6f-115">Einen Trennschalter verhindert, dass eine Anwendung eine Operation aus, die vermutlich fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="e1b6f-116">Eine Anwendung kann diese beiden Muster mithilfe des Wiederholungsmusters, das zum Aufrufen eines Vorgangs über ein Trennschalter kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="e1b6f-117">Allerdings sollte die Wiederholungslogik für alle Ausnahmen, die von der Trennschalter zurückgegeben werden, und es sollte Wiederholungsversuche verwerfen, wenn der Trennschalter gibt an, dass ein Problem nicht vorübergehend ist.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="e1b6f-118">Implementieren eine einen Trennschalter mit Polly</span><span class="sxs-lookup"><span data-stu-id="e1b6f-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="e1b6f-119">Wie bei der Implementierung von Wiederholungen die empfohlene Vorgehensweise für Trennschalter ist bewährte .NET Bibliotheken wie Polly nutzen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="e1b6f-120">Die eShopOnContainers-Anwendung verwendet die Polly Circuit-Breaker-Richtlinie aus, bei der Implementierung von HTTP-Wiederholungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="e1b6f-121">In der Tat gilt die Anwendung beide Richtlinien für die ResilientHttpClient Utility-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="e1b6f-122">Wenn Sie ein Objekt des Typs ResilientHttpClient für HTTP-Anforderungen (von eShopOnContainers) verwenden, Sie werden sowohl diese Richtlinien anwenden, jedoch zusätzliche Richtlinien konnte zu hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="e1b6f-123">Die einzige zusätzliche auf den Code für Wiederholungen für HTTP-Aufrufs verwendet ist der Code, in dem Sie das Circuit-Breaker Richtlinie hinzufügen zur Liste der Richtlinien zu verwenden, wie am Ende den folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e1b6f-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="e1b6f-124">Der Code Fügt eine Richtlinie an den HTTP-Wrapper.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="e1b6f-125">Übergeben, dass die Richtlinie definiert ein Trennschalter, das geöffnet wird, wenn der Code die angegebene Anzahl von aufeinander folgenden Ausnahmen (Ausnahmen in einer Zeile), erkennt als im Parameters ExceptionsAllowedBeforeBreaking (5 in diesem Fall).</span><span class="sxs-lookup"><span data-stu-id="e1b6f-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="e1b6f-126">Wenn die Verbindung geöffnet ist, HTTP-Anforderungen nicht funktionsfähig, aber eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="e1b6f-127">Trennschalter sollte auch verwendet werden, um Anforderungen zu einer fallback-Infrastruktur umzuleiten, haben möglicherweise Probleme in eine bestimmte Ressource, die in einer anderen Umgebung als der Clientanwendung bereitgestellt wird oder einen Dienst, der den HTTP-Aufruf ausführt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="e1b6f-128">Auf diese Weise ist es ein Ausfall im Datencenter, der nur die Back-End-Microservices jedoch nicht Ihre Clientanwendungen angewendet, wirkt sich auf die können die Clientanwendungen fallback Dienste umleiten.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="e1b6f-129">Plant eine neue Richtlinie aus, um dies zu automatisieren Polly [Failoverrichtlinie](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) Szenario.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="e1b6f-130">Alle diese Funktionen sind natürlich für Fälle, in dem Sie das Failover aus, in der .NET Code, anstatt sie automatisch für Sie von Azure verwaltet wird, mit Speicherorttransparenz verwalten.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="e1b6f-131">Verwenden die Hilfsprogrammklasse ResilientHttpClient aus eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e1b6f-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="e1b6f-132">Sie verwenden die Hilfsprogrammklasse ResilientHttpClient, ähnlich wie die .NET HttpClient-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="e1b6f-133">Im folgenden Beispiel von der eShopOnContainers MVC-Webanwendung (OrderingService Agent-Klasse von OrderController verwendet) wird das Objekt ResilientHttpClient über den "HttpClient"-Parameter des Konstruktors eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="e1b6f-134">Anschließend wird das Objekt zum Ausführen von HTTP-Anforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-134">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="e1b6f-135">Wenn die \_ApiClient Member-Objekt verwendet wird, verwendet intern die Wrapperklasse mit Polly Policiesؙ – die wiederholungsrichtlinie der Trennschalter-Richtlinie und alle anderen Richtlinien, die aus der Auflistung der Polly-Richtlinien angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="e1b6f-136">Testen von Wiederholungen in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e1b6f-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="e1b6f-137">Sobald Sie die eShopOnContainers-Lösung in einem Docker-Host starten, muss er mehrere Container zu starten.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="e1b6f-138">Einige der Container werden langsamer starten und zu initialisieren, wie die SQL Server-Container.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="e1b6f-139">Dies gilt insbesondere, beim ersten der Anwendung eShopOnContainers in Docker bereitstellen, da er die Images und die Datenbank einrichten muss.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="e1b6f-140">Die Tatsache, dass die einige Container langsamer als die andere den Rest der Dienste für anfänglich HTTP-Ausnahmen auslösen, verursachen können, selbst wenn Sie festlegen, dass Abhängigkeiten zwischen Containern am start der Docker-verfassen Ebene, wie in vorherigen Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="e1b6f-141">Die Docker-verfassen Abhängigkeiten zwischen Containern sind nur auf der Prozessebene.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="e1b6f-142">Des Containers Eintrag Punkt Prozess gestartet werden kann, aber SQL Server möglicherweise nicht für Abfragen bereit.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="e1b6f-143">Das Ergebnis einer Cascade von Fehlern werden kann, und die Anwendung kann eine Ausnahme abgerufen, beim Versuch, diesen Container nutzen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="e1b6f-144">Diese Art von Fehlern beim Start möglicherweise auch angezeigt werden, wenn die Anwendung in der Cloud bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="e1b6f-145">In diesem Fall Orchestrators möglicherweise werden Container von einem Knoten oder virtuellen Computer in einen anderen verschieben (die neue Instanzen gestartet wird,), wenn die Anzahl der Container über die Cluster-Knoten hinweg Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="e1b6f-146">Die Möglichkeit, die eShopOnContainers dieses Problem gelöst ist mithilfe des Wiederholungsmusters, das die wir zuvor veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="e1b6f-147">Es ist auch an, warum, wenn Sie die Projektmappe zu starten, ablaufverfolgungen oder Warnungen wie folgt auftreten können:</span><span class="sxs-lookup"><span data-stu-id="e1b6f-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="e1b6f-148">"**Wiederholung 1 implementiert, mit Pollys RetryPolicy**, da: System.Net.Http.HttpRequestException: beim Senden der Anforderung ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="e1b6f-149"> ---&gt;System.Net.Http.CurlException: Konnte keine Verbindung mit Server herstellen\\am System.Net.Http.CurlHandler.ThrowIfCURLEError (CURLcode Fehler) n\\am n \[... \].</span><span class="sxs-lookup"><span data-stu-id="e1b6f-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="e1b6f-150">Testen der Trennschalter in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e1b6f-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="e1b6f-151">Es gibt mehrere Möglichkeiten, Sie können die Verbindung zu öffnen und mit eShopOnContainers zu testen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="e1b6f-152">Eine Möglichkeit besteht darin senken Sie die zulässige Anzahl von Wiederholungen auf 1 in der Trennschalter Richtlinie und stellen Sie die gesamte Lösung in Docker.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="e1b6f-153">Klicken Sie mit einem einzelnen Neuversuch besteht eine hohe Wahrscheinlichkeit, die eine HTTP-Anforderung während der Bereitstellung fehl, der Trennschalter wird geöffnet, und Sie erhalten eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="e1b6f-154">Eine andere Möglichkeit ist die Verwendung von benutzerdefinierten Middleware, die in der Reihenfolge Microservice implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-154">Another option is to use custom middleware that is implemented in the ordering microservice.</span></span> <span data-ttu-id="e1b6f-155">Wenn diese Middleware aktiviert ist, fängt Sie alle HTTP-Anforderungen ab und gibt den Statuscode 500 zurück.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="e1b6f-156">Sie können die Middleware aktivieren, indem Sie eine GET-Anforderung an der fehlerhaften URI wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e1b6f-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="e1b6f-157">GET/fehlschlagen</span><span class="sxs-lookup"><span data-stu-id="e1b6f-157">GET /failing</span></span>

<span data-ttu-id="e1b6f-158">Diese Anforderung gibt den aktuellen Status der Middleware zurück.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="e1b6f-159">Wenn die Middleware aktiviert ist, die Anforderung den Statuscode 500 zurück.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="e1b6f-160">Wenn die Middleware deaktiviert ist, ist es jedoch keine Antwort.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="e1b6f-161">GET/fehlschlägt? aktivieren</span><span class="sxs-lookup"><span data-stu-id="e1b6f-161">GET /failing?enable</span></span>

<span data-ttu-id="e1b6f-162">Diese Anforderung aktiviert die Middleware.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="e1b6f-163">GET/fehlschlägt? deaktivieren</span><span class="sxs-lookup"><span data-stu-id="e1b6f-163">GET /failing?disable</span></span>

<span data-ttu-id="e1b6f-164">Diese Anforderung wird die Middleware deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-164">This request disables the middleware.</span></span>

<span data-ttu-id="e1b6f-165">Sobald die Anwendung ausgeführt wird, können Sie die Middleware aktivieren, indem Sie eine Anforderung mit den folgenden URI in einen beliebigen Browser.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="e1b6f-166">Beachten Sie, dass die Sortierung Microservice Port 5102 verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-166">Note that the ordering microservice uses port 5102.</span></span>

<span data-ttu-id="e1b6f-167">Http://localhost:5102 / fehlschlägt? aktivieren</span><span class="sxs-lookup"><span data-stu-id="e1b6f-167">http://localhost:5102/failing?enable</span></span>

<span data-ttu-id="e1b6f-168">Sie können dann überprüfen Sie den Status mit dem URI [Http://localhost:5102 / fehlschlagen](http://localhost:5100/failing), wie in Abbildung 10 – 4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-168">You can then check the status using the URI [http://localhost:5102/failing](http://localhost:5100/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="e1b6f-169">**Abbildung 10 – 4**.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-169">**Figure 10-4**.</span></span> <span data-ttu-id="e1b6f-170">Einen Fehler mit ASP.NET Middleware simulieren</span><span class="sxs-lookup"><span data-stu-id="e1b6f-170">Simulating a failure with ASP.NET middleware</span></span>

<span data-ttu-id="e1b6f-171">An diesem Punkt Aufrufen der Reihenfolge Microservice antwortet mit dem Statuscode 500 bei jedem Aufruf sie.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-171">At this point, the ordering microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="e1b6f-172">Sobald die Middleware ausgeführt wird, können Sie versuchen, eine Bestellung von der MVC-Webanwendung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="e1b6f-173">Da die Anforderungen ein Fehler auftritt, wird die Verbindung geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="e1b6f-174">Im folgenden Beispiel sehen Sie, dass die MVC-Webanwendung einen Catch weist in der Logik zum Platzieren einer Bestellung zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="e1b6f-175">Wenn der Code eine Open-Circuit-Ausnahme abfängt, wird dem Benutzer eine benutzerfreundliche Meldung informiert wird gewartet.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

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

<span data-ttu-id="e1b6f-176">Hier ist eine Zusammenfassung.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-176">Here’s a summary.</span></span> <span data-ttu-id="e1b6f-177">Die wiederholungsrichtlinie versucht, mehrere Male die HTTP-Anforderung und ruft HTTP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="e1b6f-178">Wenn die Anzahl der Versuche, die maximale Anzahl Satz für die Richtlinie "Circuit-Breaker" (in diesem Fall 5) erreicht, löst die Anwendung eine BrokenCircuitException an.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="e1b6f-179">Das Ergebnis ist eine benutzerfreundliche Meldung an, wie in Abbildung 10 – 5 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="e1b6f-180">**Abbildung 10 – 5**.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-180">**Figure 10-5**.</span></span> <span data-ttu-id="e1b6f-181">Trennschalter ein Fehler zurückgegeben, in die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="e1b6f-182">Sie können eine unterschiedliche Logik für den Fall, öffnen Sie die Verbindung implementieren.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="e1b6f-183">Oder Sie können eine HTTP-Anforderung für einen anderen Back-End-Microservice versuchen, ob ein fallback Datacenter oder redundante Back-End-System vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="e1b6f-184">Schließlich ist eine weitere Möglichkeit für die CircuitBreakerPolicy isolieren (der erzwingt öffnen und die Verbindung geöffnet hält) und zurückgesetzt (Dies schließt erneut) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="e1b6f-185">Diese können verwendet werden, einen Hilfsprogramm HTTP-Endpunkt zu erstellen, der isoliert und Zurücksetzen der direkt auf die Richtlinie aufruft.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="e1b6f-186">Solche ein HTTP-Endpunkt kann auch verwendet werden entsprechend geschützt werden, in der Produktion vorübergehend isolieren ein downstreamsystem, z. B. wenn das Upgrade ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="e1b6f-187">Oder es konnte die Verbindung manuell, um ein downstreamsystem schützen Sie vermuten, werden fehlgeschlagene auslöst.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="e1b6f-188">Die wiederholungsrichtlinie für hinzugefügt eine Strategie jitter</span><span class="sxs-lookup"><span data-stu-id="e1b6f-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="e1b6f-189">Eine reguläre wiederholungsrichtlinie kann Ihr System in Fällen hoher Parallelität und Skalierbarkeit und unter hohes konfliktpotenzial auswirken.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="e1b6f-190">Um Spitzen ähnliche Wiederholungen, die von vielen Clients bei einem teilweise Ausfälle zu vermeiden, ist eine gute Lösung eine Strategie für die Jitter an die wiederholungsrichtlinie/Algorithmus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="e1b6f-191">Dies kann die gesamtleistung des Systems End-to-End-verbessern, indem Exponentielles Backoff hinsichtlich Ihrer Zufälligkeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="e1b6f-192">Dies ausbreitet die Spitzen beim Auftreten von Problemen.</span><span class="sxs-lookup"><span data-stu-id="e1b6f-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="e1b6f-193">Wenn Sie Polly verwenden, kann Code zum Implementieren von Jitter wie im folgenden Beispiel aussehen:</span><span class="sxs-lookup"><span data-stu-id="e1b6f-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="e1b6f-194">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e1b6f-194">Additional resources</span></span>

-   <span data-ttu-id="e1b6f-195">**Wiederholen Sie die Muster**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="e1b6f-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="e1b6f-196">**Verbindungsresilienz** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="e1b6f-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="e1b6f-197">**Polly** (.NET Stabilität und vorübergehend fehlerverarbeitung Bibliothek) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="e1b6f-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="e1b6f-198">**Einen Trennschalter**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="e1b6f-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="e1b6f-199">**Marc Brooker. Jitter: Macht es besser mit Zufälligkeit** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="e1b6f-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e1b6f-200">[Vorherigen] (Implement-http-call-retries-exponential-backoff-polly.md) [weiter] (Monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="e1b6f-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
