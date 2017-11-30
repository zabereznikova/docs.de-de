---
title: Abonnieren von Ereignissen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Abonnieren von Ereignissen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: fe17b53a39ff2964cd60183e291e2936d3ba28df
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="subscribing-to-events"></a><span data-ttu-id="f944d-104">Abonnieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="f944d-104">Subscribing to events</span></span>

<span data-ttu-id="f944d-105">Der erste Schritt für die Verwendung der Ereignisbus werden die Microservices auf die Ereignisse zu abonnieren, die empfangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f944d-105">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="f944d-106">Sollte der Empfänger Microservices erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f944d-106">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="f944d-107">Im folgende einfachen Code zeigt jeden Empfänger Microservice herrscht implementieren beim Starten des Diensts (d. h. Start class), damit es auf die Ereignisse benötigt abonniert.</span><span class="sxs-lookup"><span data-stu-id="f944d-107">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the Startup class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="f944d-108">Beispielsweise muss der basket.api Microservice ProductPriceChangedIntegrationEvent Nachrichten abonnieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-108">For instance, the basket.api microservice needs to subscribe to ProductPriceChangedIntegrationEvent messages.</span></span> <span data-ttu-id="f944d-109">Dadurch sind die Microservice Änderungen beachten, der Produktpreis und ermöglicht es das Warnen des Benutzers über die Änderung des Produkts im Warenkorb eines Benutzers ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-109">This makes the microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

<span data-ttu-id="f944d-110">Nachdem dieser Code ausgeführt wird, wird der Abonnent Microservice über RabbitMQ Kanäle überwacht.</span><span class="sxs-lookup"><span data-stu-id="f944d-110">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="f944d-111">Wenn jede Nachricht vom Typ ProductPriceChangedIntegrationEvent eingeht, ruft der Code den Ereignishandler, der an Sie übergeben wird und das Ereignis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f944d-111">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="f944d-112">Veröffentlichen von Ereignissen über den-Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="f944d-112">Publishing events through the event bus</span></span>

<span data-ttu-id="f944d-113">Der Absender der Nachricht (Ursprung Microservice) veröffentlicht schließlich die integrationsereignisse mit Code wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f944d-113">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="f944d-114">(Dies ist ein vereinfachtes Beispiel, der keinen Unteilbarkeit berücksichtigt.) Wenn ein Ereignis über mehrere Microservices, in der Regel nach dem Commit der Daten oder Transaktionen aus der Ursprung Microservice rechten weitergeleitet werden muss, würden Sie ähnlichen Code implementieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-114">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="f944d-115">Das Ereignis Bus Implementierung-Objekt (basierend auf RabbitMQ oder basierend auf einer Servicebus) würde zunächst an den Konstruktor Controller wie im folgenden Code eingegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f944d-115">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

<span data-ttu-id="f944d-116">Klicken Sie dann verwenden Sie die Klasse des Controllers-Methoden, wie in der UpdateProduct-Methode:</span><span class="sxs-lookup"><span data-stu-id="f944d-116">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

```csharp
[Route("update")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

<span data-ttu-id="f944d-117">In diesem Fall, da der Ursprung Microservice eine einfache CRUD-Microservice ist, wird dieser Code rechts in einem Web-API-Controller platziert.</span><span class="sxs-lookup"><span data-stu-id="f944d-117">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> <span data-ttu-id="f944d-118">In komplexeren Microservices könnte es in der richtigen CommandHandler-Klasse implementiert werden, nachdem die ursprünglichen Daten übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-118">In more advanced microservices, it could be implemented in the CommandHandler class, right after the original data is committed.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="f944d-119">Entwerfen von Unteilbarkeit und Flexibilität bei der Veröffentlichung in den-Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="f944d-119">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="f944d-120">Wenn Sie über ein verteiltes messaging-integrationsereignisse veröffentlichen System wie Ihr Ereignisbus, müssen Sie das Problem der atomar Aktualisieren der ursprünglichen Datenbank und Veröffentlichen eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="f944d-120">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="f944d-121">Z. B. ein Commit ausgeführt wird in der vereinfachte weiter oben gezeigten Beispiel wird der Code Daten an die Datenbank der Produktpreis wird geändert, und klicken Sie dann veröffentlicht eine Nachricht ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="f944d-121">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="f944d-122">Es könnte zu Beginn wichtige aussehen, dass diese beiden Vorgänge automatisch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-122">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="f944d-123">Allerdings bei Verwendung eine verteilte Transaktion, die im Zusammenhang mit der Datenbank und der Meldung broker, wie bei älteren Systemen wie [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), dies wird nicht empfohlen, die durch die beschriebenenGründen[CAP Theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="f944d-123">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="f944d-124">Verwenden Sie im Grunde Microservices, skalierbar und hoch verfügbaren Systeme erstellen.</span><span class="sxs-lookup"><span data-stu-id="f944d-124">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="f944d-125">Vereinfachen in einem gewissen, die CAP Pythagoras gibt an, dass eine Datenbank (oder ein Microservice, der das Modell besitzt) erstellt werden kann, die ständig verfügbar ist, werden hoch konsistent, *und* fehlertoleranten jeder Partition.</span><span class="sxs-lookup"><span data-stu-id="f944d-125">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="f944d-126">Sie müssen zwei dieser drei Eigenschaften auswählen.</span><span class="sxs-lookup"><span data-stu-id="f944d-126">You must choose two of these three properties.</span></span>

<span data-ttu-id="f944d-127">Microservices-basierten Architekturen empfiehlt, Verfügbarkeit und Fehlertoleranz zu gewährleisten, und sollten Sie starken Konsistenz vervielfachung.</span><span class="sxs-lookup"><span data-stu-id="f944d-127">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="f944d-128">Aus diesem Grund in die meisten modernen Microservice-basierten Anwendungen, in der Regel nicht möchten verteilte Transaktionen in messaging verwenden wie bei der Implementierung [verteilte Transaktionen](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) basierend auf der Windows-verteilten Transaktion Coordinator (DTC) mit [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="f944d-128">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="f944d-129">Gehen Sie an das erste Problem und dessen Beispiel wir noch.</span><span class="sxs-lookup"><span data-stu-id="f944d-129">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="f944d-130">Wenn es sich bei einem Absturz des Diensts, nachdem die Datenbank aktualisiert wird (in diesem Fall mit der rechten Maustaste nach der Zeile des Codes mit \_Kontext. SaveChangesAsync()), aber vor der Integration-Ereignis veröffentlicht wird, kann das Gesamtsystem inkonsistent werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-130">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="f944d-131">Dies könnte unternehmenswichtig ist, abhängig vom Vorgang entsprechend den geschäftlichen sein, die mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f944d-131">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="f944d-132">Wie bereits im Architektur-Abschnitt erwähnt, können Sie mehrere Ansätze für den Umgang mit diesem Problem haben:</span><span class="sxs-lookup"><span data-stu-id="f944d-132">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="f944d-133">Verwenden Sie die vollständige [Ereignis Sourcing Muster](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span><span class="sxs-lookup"><span data-stu-id="f944d-133">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="f944d-134">Mit [Transaktionsprotokoll Mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="f944d-134">Using [transaction log mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="f944d-135">Mithilfe der [Postausgang Muster](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="f944d-135">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="f944d-136">Dies ist eine transaktionale Tabelle zum Speichern der integrationsereignisse (erweitern die lokale Transaktion).</span><span class="sxs-lookup"><span data-stu-id="f944d-136">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="f944d-137">In diesem Szenario der vollständigen Ereignis Quellentnahme (ES) Muster ist eine der besten Vorgehensweisen ist dies nicht der *der* best.</span><span class="sxs-lookup"><span data-stu-id="f944d-137">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="f944d-138">Allerdings in vielen Anwendungsszenarios Sie zum Implementieren eines vollständigen Systems für die ES möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="f944d-138">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="f944d-139">ES bedeutet nur Domäne Ereignisse in die Transaktionsdatenbank aktuellen Zustandsdaten speichern, statt gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f944d-139">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="f944d-140">Speichern nur die Ereignisse Domäne möglich Vorteile, z. B. den Verlauf Ihres Systems zur Verfügung und können den Status Ihres Systems jederzeit in der Vergangenheit zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f944d-140">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="f944d-141">Allerdings Implementierung eines vollständigen Systems für die ES erfordert, dass Sie die meisten Ihres Systems neu entwerfe und führt viele andere Komplexität und Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f944d-141">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="f944d-142">Beispielsweise soll, verwenden Sie eine Datenbank, die speziell für diese Aufgabe für das Ereignis als Quelle, z. B. [Ereignisspeicher](https://geteventstore.com/), oder einer Datenbank dokumentorientiert, z. B. Azure-Cosmos-DB, MongoDB, Cassandra, CouchDB oder RavenDB.</span><span class="sxs-lookup"><span data-stu-id="f944d-142">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="f944d-143">ES ist eine hervorragende Ansatz für dieses Problem, jedoch nicht die einfachste Lösung, wenn Sie bereits mit Ereignis sourcing vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="f944d-143">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="f944d-144">Die Option zum Verwenden des Transaktionsprotokolls anfänglich mining sucht sehr transparent.</span><span class="sxs-lookup"><span data-stu-id="f944d-144">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="f944d-145">Um diesen Ansatz verwenden, hat der Microservice, an das RDBMS-Transaktionsprotokoll, z. B. das SQL Server-Transaktionsprotokoll gekoppelt werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-145">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="f944d-146">Dies ist wahrscheinlich nicht wünschenswert.</span><span class="sxs-lookup"><span data-stu-id="f944d-146">This is probably not desirable.</span></span> <span data-ttu-id="f944d-147">Ein weiterer Nachteil ist, dass auf der gleichen Ebene wie Ihre allgemeinen-integrationsereignisse kann möglicherweise nicht die Low-Level-Updates im Transaktionsprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-147">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="f944d-148">Wenn dies der Fall ist, können der Prozess der Reverse Engineering diese Transaktion Protokollvorgänge schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="f944d-148">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="f944d-149">Ein Ansatz mit Lastenausgleich ist eine Mischung aus einer transaktionalen Datenbank-Tabelle und eine vereinfachte Vorangestellten Muster.</span><span class="sxs-lookup"><span data-stu-id="f944d-149">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="f944d-150">Sie können einen Status, z. B. "kann jetzt so veröffentlichen Sie das Ereignis" die Sie in der ursprünglichen Ereignis aus, wenn Sie es an die Ereignistabelle Integration verbindlich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f944d-150">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="f944d-151">Sie versuchen dann das Ereignis in den-Ereignisbus zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f944d-151">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="f944d-152">Wenn die Veröffentlichung Ereignisaktion erfolgreich ist, Sie eine andere Transaktion in der "Origin"-Dienst gestartet und verschieben den Status von "zum Veröffentlichen des Ereignisses bereit" zu "Ereignis bereits veröffentlicht."</span><span class="sxs-lookup"><span data-stu-id="f944d-152">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="f944d-153">Wenn die veröffentlichen Ereignisaktion im Ereignis fehlschlägt bus, die Daten immer noch nicht mehr innerhalb der Ursprung Microservice inkonsistent – weiterhin als "bereit zum Veröffentlichen des Ereignisses" gekennzeichnet und im Hinblick auf den Rest der Dienste, es schließlich konsistent sein werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-153">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="f944d-154">Sie können stets Überprüfen des Zustands der Transaktionen oder integrationsereignisse Hintergrundaufträge verfügen.</span><span class="sxs-lookup"><span data-stu-id="f944d-154">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="f944d-155">Falls der Auftrag ein Ereignis in dem Zustand "bereit zum Veröffentlichen des Ereignisses" findet, kann versucht, dieses Ereignis an den-Ereignisbus nur erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f944d-155">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="f944d-156">Beachten Sie, dass bei diesem Ansatz Sie beibehalten werden, nur die integrationsereignisse für jede Microservice Ursprung und nur die Ereignisse, die für die Kommunikation mit anderen Microservices oder externen Systemen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f944d-156">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="f944d-157">Im Gegensatz dazu speichern in einem vollständigen Vorangestellten-System auch alle Domain-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="f944d-157">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="f944d-158">Dieser Ansatz mit Lastenausgleich ist daher eine vereinfachte Vorangestellten-System.</span><span class="sxs-lookup"><span data-stu-id="f944d-158">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="f944d-159">Benötigen Sie eine Liste der Integration von Ereignissen mit ihren aktuellen Status ("bereit zum Veröffentlichen" im Vergleich zu "veröffentlicht").</span><span class="sxs-lookup"><span data-stu-id="f944d-159">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="f944d-160">Jedoch müssen Sie nur diese Zustände für die integrationsereignisse zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-160">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="f944d-161">Und bei dieser Vorgehensweise Sie müssen nicht alle Domänendaten als Ereignisse in die Transaktionsdatenbank speichern wie in einem vollständigen Vorangestellten System aus.</span><span class="sxs-lookup"><span data-stu-id="f944d-161">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="f944d-162">Wenn Sie bereits eine relationale Datenbank verwenden, können Sie eine transaktionale Tabelle, zum Speichern von Ereignissen für Integration.</span><span class="sxs-lookup"><span data-stu-id="f944d-162">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="f944d-163">Um die Unteilbarkeit von Transaktionen in der Anwendung zu erzielen, verwenden Sie einen zweistufiger Prozess basierend auf lokale Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f944d-163">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="f944d-164">Im Wesentlichen müssen Sie eine IntegrationEvent-Tabelle in derselben Datenbank, in dem die Domänenentitäten haben.</span><span class="sxs-lookup"><span data-stu-id="f944d-164">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="f944d-165">Diese Tabelle funktioniert wie ein Insurance Unteilbarkeit erreichen Sie, sodass Sie enthalten integrationsereignisse in die gleichen Transaktionen beibehalten, die Ihre Daten ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f944d-165">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="f944d-166">Schritt für Schritt, der Prozess ist wie folgt: die Anwendung beginnt eine Transaktion für die lokale Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f944d-166">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="f944d-167">Anschließend wird der Status Ihrer Domäne Entitäten aktualisiert und ein Ereignis in der Ereignistabelle Integration eingefügt.</span><span class="sxs-lookup"><span data-stu-id="f944d-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="f944d-168">Schließlich wird die Transaktion bestätigt.</span><span class="sxs-lookup"><span data-stu-id="f944d-168">Finally, it commits the transaction.</span></span> <span data-ttu-id="f944d-169">Sie erhalten die gewünschte Unteilbarkeit.</span><span class="sxs-lookup"><span data-stu-id="f944d-169">You get the desired atomicity.</span></span>

<span data-ttu-id="f944d-170">Wenn Sie die Schritte zum Veröffentlichen der Ereignisse zu implementieren, müssen Sie diese Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f944d-170">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="f944d-171">Veröffentlichen Sie das Ereignis Integration direkt nach dem Commit der Transaktion, und verwenden Sie eine andere lokale Transaktion, um die Ereignisse in der Tabelle als die zu veröffentlichenden zu markieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="f944d-172">Anschließend verwenden Sie die Tabelle nur als ein Element im Falle von Problemen in remote Microservices-integrationsereignisse verfolgen und Aktionen Sie Ausgleich basierend auf den gespeicherten integrationsereignisse.</span><span class="sxs-lookup"><span data-stu-id="f944d-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="f944d-173">Verwenden Sie diese Tabelle als eine Art der Warteschlange an.</span><span class="sxs-lookup"><span data-stu-id="f944d-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="f944d-174">Eine separate Anwendungsthread oder ein Prozess fragt die Ereignistabelle Integration, die Ereignisse in den-Ereignisbus veröffentlicht und anschließend eine lokale Transaktion verwendet, um die Ereignisse zu markieren, die veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f944d-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="f944d-175">Abbildung 8-22 zeigt die Architektur für die erste der folgenden Ansätze.</span><span class="sxs-lookup"><span data-stu-id="f944d-175">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="f944d-176">**Abbildung 8-22**.</span><span class="sxs-lookup"><span data-stu-id="f944d-176">**Figure 8-22**.</span></span> <span data-ttu-id="f944d-177">Unteilbarkeit von Transaktionen beim Veröffentlichen von Ereignissen in den-Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="f944d-177">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="f944d-178">Der Ansatz dargestellt in Abbildung 8-22 fehlt ein Microservice zusätzlichen Worker, die für das Überprüfen und bestätigen den Erfolg der veröffentlichten-integrationsereignisse ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-178">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="f944d-179">Falls ein Fehler auftritt kann diese zusätzlichen Checker Worker Microservice Ereignisse aus der Tabelle gelesen und veröffentlichen Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="f944d-179">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="f944d-180">Über die zweite Vorgehensweise: Verwenden Sie die EventLog-Tabelle als eine Warteschlange und immer einen Worker-Microservice verwenden, um die Nachrichten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f944d-180">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="f944d-181">In diesem Fall wird der Prozess wie in Abbildung 8-23 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f944d-181">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="f944d-182">Dies zeigt, dass eine zusätzliche Microservice, und die Tabelle ist die einzige Quelle beim Veröffentlichen von Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="f944d-182">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="f944d-183">**Abbildung 8-23**.</span><span class="sxs-lookup"><span data-stu-id="f944d-183">**Figure 8-23**.</span></span> <span data-ttu-id="f944d-184">Unteilbarkeit von Transaktionen beim Veröffentlichen von Ereignissen in den-Ereignisbus mit einem Worker microservice</span><span class="sxs-lookup"><span data-stu-id="f944d-184">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="f944d-185">Zur Vereinfachung verwendet das Beispiel eShopOnContainers beim ersten Ansatz (mit ohne zusätzliche Prozesse oder Checker Microservices) sowie den-Ereignisbus.</span><span class="sxs-lookup"><span data-stu-id="f944d-185">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="f944d-186">Die eShopOnContainers ist jedoch nicht alle möglichen Schwachstellen behandeln.</span><span class="sxs-lookup"><span data-stu-id="f944d-186">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="f944d-187">In einer realen Anwendung, die in der Cloud bereitgestellt wird müssen Sie die Tatsache, die dass die Probleme werden schließlich auftreten, und Sie müssen implementieren, das Überprüfen und senden Logik zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f944d-187">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="f944d-188">Anhand der Tabelle als eine Warteschlange kann effektiver ist als die erste Methode sein, wenn stehen Ihnen diese Tabelle als einzelne Quelle der Ereignisse aus, wenn sie über den-Ereignisbus zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f944d-188">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="f944d-189">Implementieren Unteilbarkeit von Transaktionen beim Veröffentlichen von integrationsereignisse über den-Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="f944d-189">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="f944d-190">Der folgende Code zeigt, wie Sie eine einzelne Transaktion, die im Zusammenhang mit mehreren DbContext-Objekten erstellen können – ein Kontext, die im Zusammenhang mit der ursprünglichen Daten aktualisiert wird und die zweite Kontext im Zusammenhang mit der IntegrationEventLog-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f944d-190">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="f944d-191">Beachten Sie, dass die Transaktion in den folgenden Beispielcode nicht stabil, wenn Verbindungen mit der Datenbank Probleme zum Zeitpunkt verfügen, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f944d-191">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="f944d-192">Dies kann geschehen in Cloud-basierten Systemen wie Azure SQL-Datenbank, die Datenbanken auf Servern verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="f944d-192">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="f944d-193">Implementieren robuste Transaktionen in mehreren Kontexten, finden Sie unter der [implementieren robuste Entity Framework Core-SQL-Verbindungen](#implementing_resilient_EFCore_SQL_conns) Abschnitt weiter unten in diesem Handbuch.</span><span class="sxs-lookup"><span data-stu-id="f944d-193">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](#implementing_resilient_EFCore_SQL_conns) section later in this guide.</span></span>

<span data-ttu-id="f944d-194">Das folgende Beispiel zeigt den gesamten Prozess in ein einzelnes Stück Code, aus Gründen der Klarheit.</span><span class="sxs-lookup"><span data-stu-id="f944d-194">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="f944d-195">Allerdings wird die eShopOnContainers-Implementierung wird tatsächlich umgestaltet und teilen Sie diese Logik in mehrere Klassen, daher ist es einfacher zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f944d-195">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult>
    UpdateProduct([FromBody]CatalogItem productToUpdate)
{
    var catalogItem = await _catalogContext.CatalogItems
        .SingleOrDefaultAsync(i => i.Id == productToUpdate.Id);

    if (catalogItem == null) return NotFound();

    bool raiseProductPriceChangedEvent = false;

    IntegrationEvent priceChangedEvent = null;

    if (catalogItem.Price != productToUpdate.Price)
        raiseProductPriceChangedEvent = true;

    if (raiseProductPriceChangedEvent) // Create event if price has changed
    {
        var oldPrice = catalogItem.Price;
        priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
            productToUpdate.Price,
            oldPrice);
    }

    // Update current product
    catalogItem = productToUpdate;
    // Achieving atomicity between original DB and the IntegrationEventLog
    // with a local transaction

    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);

        await _catalogContext.SaveChangesAsync();

        // Save to EventLog only if product price changed
        if(raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
   }

   // Publish to event bus only if product price changed

   if (raiseProductPriceChangedEvent)
   {
       _eventBus.Publish(priceChangedEvent);
       integrationEventLogService.MarkEventAsPublishedAsync(
           priceChangedEvent);
   }

   return Ok();
}
```

<span data-ttu-id="f944d-196">Nachdem das ProductPriceChangedIntegrationEvent Integration-Ereignis erstellt wurde, enthält die Transaktion, die der ursprünglichen domänenvorgang (Update Katalogelements) speichert auch die Dauerhaftigkeit des Ereignisses in der EventLog-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f944d-196">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="f944d-197">Dies erleichtert eine einzelne Transaktion, und Sie werden immer in der Lage sind, überprüfen Sie, ob die ereignismeldungen gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f944d-197">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="f944d-198">Die Ereignisprotokoll-Tabelle wird mit der ursprünglichen Datenbankvorgang mit einer lokalen Transaktion für dieselbe Datenbank automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f944d-198">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="f944d-199">Wenn einer der Vorgänge fehlschlägt, wird eine Ausnahme ausgelöst und ein Rollback der Transaktions alle abgeschlossenen Vorgang, daher Wahrung der Konsistenz zwischen der Domäne und die ereignismeldungen gesendet.</span><span class="sxs-lookup"><span data-stu-id="f944d-199">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="f944d-200">Empfangen von Nachrichten aus Abonnements:-Ereignishandler in Empfänger Microservices</span><span class="sxs-lookup"><span data-stu-id="f944d-200">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="f944d-201">Zusätzlich zu der Logik für den Ereignis-Abonnement müssen Sie den internen Code für die Integration Ereignishandler (z. B. eine Rückrufmethode) zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-201">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="f944d-202">Der Ereignishandler wird in dem Sie angeben, in dem die Nachrichten eines bestimmten Typs empfangen und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f944d-202">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="f944d-203">Ein Ereignishandler-den-Ereignisbus zunächst eine Ereignisinstanz Empfangsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="f944d-203">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="f944d-204">Klicken Sie dann sucht er die Komponente zu verarbeitenden im Zusammenhang mit dieses Ereignisses Integration, weitergeben und das Ereignis als eine Änderung in der Empfänger Microservice Zustand beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f944d-204">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="f944d-205">Z. B. wenn ein ProductPriceChanged-Ereignis in den Katalog Microservice stammt, er wird in den Warenkorb Microservice behandelt, und ändert sich der Status in dieser Empfänger Warenkorb Microservice sowie, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f944d-205">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

<span data-ttu-id="f944d-206">Der Ereignishandler muss überprüfen, ob das Produkt im Warenkorb-Instanzen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-206">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="f944d-207">Es wird auch der Artikelpreis für jedes Zeilenelement verwandte Warenkorb aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f944d-207">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="f944d-208">Schließlich erstellt eine Warnung, die dem Benutzer zur Preisänderung angezeigt werden, wie in Abbildung 8-24 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f944d-208">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="f944d-209">**Abbildung 8-24**.</span><span class="sxs-lookup"><span data-stu-id="f944d-209">**Figure 8-24**.</span></span> <span data-ttu-id="f944d-210">Während der Integration Ereignisse übermittelt eine Preisänderung Element in einen Warenkorb angezeigt</span><span class="sxs-lookup"><span data-stu-id="f944d-210">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="f944d-211">Idempotenz in Update nachrichtenereignisse</span><span class="sxs-lookup"><span data-stu-id="f944d-211">Idempotency in update message events</span></span>

<span data-ttu-id="f944d-212">Ein wichtiger Aspekt der Update-nachrichtenereignisse ist, dass ein Fehler auf einem beliebigen Punkt in der Kommunikation bewirken, dass die Nachricht wiederholt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="f944d-212">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="f944d-213">Andernfalls könnten eine Hintergrundtask versuchen, ein Ereignis zu veröffentlichen, die bereits veröffentlicht wurde, erstellen eine Racebedingung.</span><span class="sxs-lookup"><span data-stu-id="f944d-213">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="f944d-214">Sie müssen sicherstellen, dass die Updates sind Idempotent oder, dass genügend Informationen, um sicherzustellen, dass Sie, ein Duplikat erkennen können angebotenen verwerfen und Back nur eine Antwort zu senden.</span><span class="sxs-lookup"><span data-stu-id="f944d-214">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="f944d-215">Wie bereits erwähnt, also Idempotenz ein Vorgang mehrere Male ausgeführt werden kann ohne das Ergebnis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f944d-215">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="f944d-216">In einer Umgebung mit messaging wie bei der Kommunikation von Ereignissen ein Ereignis Idempotent ist, wenn es mehrere Male übermittelt werden kann ohne das Ergebnis für den Empfänger Microservice zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f944d-216">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="f944d-217">Dies aufgrund der Natur des Ereignisses kann erforderlich sein, oder aufgrund der Art und Weise das System das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="f944d-217">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="f944d-218">Nachricht Idempotenz ist wichtig, in jeder Anwendung, die Messaging verwendet, nicht nur Anwendungen, die das Ereignis Bus Muster zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-218">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="f944d-219">Ein Beispiel eines Vorgangs Idempotent ist eine SQL­Anweisung, die Daten in eine Tabelle einfügt, nur dann, wenn diese Daten nicht bereits in der Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-219">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="f944d-220">Es spielt keine wie oft ausführen, mit dem SQL-Anweisung eingefügt; Das Ergebnis wird gleich sein – in der Tabelle werden diese Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f944d-220">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="f944d-221">Idempotenz wie folgt kann auch erforderlich, die beim Umgang mit Nachrichten, wenn die Nachrichten möglicherweise gesendet werden konnte und daher verarbeiteten mehr als einmal.</span><span class="sxs-lookup"><span data-stu-id="f944d-221">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="f944d-222">Z. B., wenn Wiederholungslogik bewirkt, einen Absender dass auf genau die gleiche Nachricht mehrmals zu senden, müssen Sie sicherstellen, dass es Idempotent ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-222">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="f944d-223">Es ist möglich, Entwurf Idempotent Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f944d-223">It is possible to design idempotent messages.</span></span> <span data-ttu-id="f944d-224">Sie können z. B. ein Ereignis, das besagt, dass erstellen "legen Sie auf den Produktpreis \$25" anstelle von "hinzufügen \$5, um den Produktpreis."</span><span class="sxs-lookup"><span data-stu-id="f944d-224">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="f944d-225">Konnte der ersten Nachricht oft problemlos verarbeiten, und das Ergebnis wird gleich sein.</span><span class="sxs-lookup"><span data-stu-id="f944d-225">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="f944d-226">Dies ist nicht "true" für die zweite Meldung.</span><span class="sxs-lookup"><span data-stu-id="f944d-226">That is not true for the second message.</span></span> <span data-ttu-id="f944d-227">Selbst im ersten Fall, Sie möchten jedoch möglicherweise nicht das erste Ereignis zu verarbeiten, da das System auch ein neuer Preis Änderungsereignis gesendet haben konnte und Sie den neuen Preis überschrieben werden würde.</span><span class="sxs-lookup"><span data-stu-id="f944d-227">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="f944d-228">Ein weiteres Beispiel wären ein Auftrag abgeschlossen-Ereignis, das an mehrere Abonnenten weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f944d-228">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="f944d-229">Es ist wichtig, dass die Bestellinformationen in anderen Systemen nur einmal aktualisiert werden, auch wenn doppelte nachrichtenereignisse nach demselben Ereignis Auftrag abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f944d-229">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="f944d-230">Es ist sinnvoll, eine Art von pro Ereignis Identität verfügen, sodass Sie Logik erstellen können, die erzwingt, dass jedes Ereignis nur einmal pro Empfänger verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="f944d-230">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="f944d-231">Verarbeitung von Nachrichten ist grundsätzlich Idempotent.</span><span class="sxs-lookup"><span data-stu-id="f944d-231">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="f944d-232">Z. B. wenn ein System Bildminiaturansichten generiert, kann es nicht wie oft ausschlaggebend der Verarbeitung der Nachricht über die generierten Miniaturansicht; Das Ergebnis ist, dass die Miniaturansichten generiert werden, und sie identisch, jedes Mal sind an.</span><span class="sxs-lookup"><span data-stu-id="f944d-232">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="f944d-233">Andererseits, Vorgänge wie das Aufrufen einer Zahlungsgateway um eine Kreditkarte Idempotent überhaupt möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="f944d-233">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="f944d-234">In diesen Fällen müssen Sie sicherstellen, dass die Verarbeitung einer Nachricht mehrere Male, die Sie erwarten, dass die Wirkung hat.</span><span class="sxs-lookup"><span data-stu-id="f944d-234">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f944d-235">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f944d-235">Additional resources</span></span>

-   <span data-ttu-id="f944d-236">**Nachricht Idempotenz berücksichtigt** (auf dieser Seite Unterüberschrift) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="f944d-236">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="f944d-237">Deduplizieren von ereignismeldungen integration</span><span class="sxs-lookup"><span data-stu-id="f944d-237">Deduplicating integration event messages</span></span>

<span data-ttu-id="f944d-238">Sie können sicherstellen, nachrichtenereignisse gesendet und verarbeitet nur einmal pro Abonnent auf unterschiedlichen Ebenen.</span><span class="sxs-lookup"><span data-stu-id="f944d-238">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="f944d-239">Eine Möglichkeit ist die Verwendung eine von der Messaginginfrastruktur verwendeten bereitgestellten deduplizierungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="f944d-239">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="f944d-240">Eine andere besteht darin, benutzerdefinierte Logik in der Ziel-Microservice zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f944d-240">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="f944d-241">Überprüfungen ist auf der Transportebene und Anwendungsebene am besten.</span><span class="sxs-lookup"><span data-stu-id="f944d-241">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="f944d-242">Deduplizieren von nachrichtenereignissen auf der Ebene des Ereignishandlers</span><span class="sxs-lookup"><span data-stu-id="f944d-242">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="f944d-243">Eine Möglichkeit, um sicherzustellen, dass ein Ereignis nur einmal alle Empfänger verarbeitet wird, wird durch bestimmte Logik implementieren, bei der Verarbeitung der Ereignisse in den Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="f944d-243">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="f944d-244">Z. B. das Ansatz wird in der Anwendung eShopOnContainers ist, wie in der Sie sehen die [Quellcode](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) der beim Empfang eines Befehls CreateOrderCommand OrdersController-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f944d-244">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="f944d-245">(In diesem Fall verwenden wir einen HTTP-Anforderung Befehl kein nachrichtenbasierte Befehl, aber die Logik, Sie einen Befehl nachrichtenbasierte Idempotent müssen, ist ähnlich.)</span><span class="sxs-lookup"><span data-stu-id="f944d-245">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="f944d-246">Deduplizieren von Nachrichten bei Verwendung von RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="f944d-246">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="f944d-247">Wenn vorübergehende Netzwerkausfälle auftreten, Nachrichten können dupliziert werden, und der Empfänger einer Nachricht werden muss, behandeln diese doppelten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f944d-247">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="f944d-248">Wenn möglich sollte Empfänger Nachrichten auf eine Weise Idempotent verarbeiten die Behandlung dieser explizit bei der Deduplizierung besser ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-248">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="f944d-249">Gemäß der [RabbitMQ Dokumentation](https://www.rabbitmq.com/reliability.html#consumer), "Wenn eine Nachricht übermittelt, die für einen Consumer, und klicken Sie dann in die Warteschlange (da sie nicht bestätigt wurde, bevor die Consumer-Verbindung gelöscht werden, z. B.) RabbitMQ für das neu zugestellte Flag festgelegt es, wenn er erneut (ob an denselben oder einen anderen) übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="f944d-249">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="f944d-250">Wenn das Flag "neu zugestellte" festgelegt ist, muss der Empfänger, die berücksichtigen, da die Nachricht möglicherweise bereits verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="f944d-250">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="f944d-251">Aber nicht gewährleistet ist. die Nachricht möglicherweise nie den Empfänger erreicht haben, nachdem sie den nachrichtenbroker möglicherweise aufgrund von Netzwerkproblemen unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="f944d-251">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="f944d-252">Andererseits, wenn das Flag "neu zugestellte" nicht festgelegt ist, wird sichergestellt, dass die Nachricht nicht mehr als einmal gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f944d-252">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="f944d-253">Daher muss der Empfänger dedupliziert werden sollen oder Prozess Nachrichten auf eine Weise Idempotent nur, wenn das Flag "neu zugestellte" in der Nachricht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f944d-253">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f944d-254">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f944d-254">Additional resources</span></span>

-   <span data-ttu-id="f944d-255">**Ereignis Driven Messaging**
    [*http://soapatterns.org/design\_Muster-Ereignis\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="f944d-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="f944d-256">**Jimmy Bogard. Umgestaltung für Stabilität: Auswerten Kopplung**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="f944d-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="f944d-257">**Veröffentlichen / Abonnieren-Kanal**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="f944d-257">**Publish-Subscribe channel**
[*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="f944d-258">**Kommunikation zwischen Kontexten begrenzt**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="f944d-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="f944d-259">**Eventuelle Konsistenz**
    [*https://en.wikipedia.org/wiki/Eventual\_Konsistenz*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="f944d-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="f944d-260">**Philip Brown. Strategien für die Integration von begrenzt Kontexten**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="f944d-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="f944d-261">**Chris Rißling. Entwickeln von transaktionalen Microservices mit Aggregate, Sourcing-Ereignis und CQRS - Teil 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="f944d-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="f944d-262">**Chris Rißling. Sourcing-Ereignismuster**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="f944d-262">**Chris Richardson. Event Sourcing pattern**
[*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="f944d-263">**Einführung in Ereignis Sourcing**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="f944d-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="f944d-264">**Ereignis-Speicherdatenbank**.</span><span class="sxs-lookup"><span data-stu-id="f944d-264">**Event Store database**.</span></span> <span data-ttu-id="f944d-265">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="f944d-265">Official site.</span></span>
    [<span data-ttu-id="f944d-266">*https://geteventstore.com/*</span><span class="sxs-lookup"><span data-stu-id="f944d-266">*https://geteventstore.com/*</span></span>](https://geteventstore.com/)

-   <span data-ttu-id="f944d-267">**Patrick Nommensen. Ereignisgesteuerte Datenverwaltung für Microservices**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*</span><span class="sxs-lookup"><span data-stu-id="f944d-267">**Patrick Nommensen. Event-Driven Data Management for Microservices**
*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span></span>

-   <span data-ttu-id="f944d-268">**Der CAP-Theorem**
    [*https://en.wikipedia.org/wiki/CAP\_theorems*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="f944d-268">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="f944d-269">**Was ist die Obergrenze des Pythagoras? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="f944d-269">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="f944d-270">**Einführung in Data-Konsistenz**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="f944d-270">**Data Consistency Primer**
[*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="f944d-271">**Rick Saling an. Der CAP-Theorem: Warum "Alles anders mit der Cloud und dem Internet ist"**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="f944d-271">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="f944d-272">**Eric Brewer. CAP zwölf Jahren: wie die "Regeln" geändert haben**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="f944d-272">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="f944d-273">**Extern (DTC) Transaktionen beteiligt** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="f944d-273">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="f944d-274">**Azure-Servicebus. Brokermessaging: Duplikaterkennung**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="f944d-274">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="f944d-275">**Zuverlässigkeit Handbuch** (RabbitMQ-Dokumentation) [ *https://www.rabbitmq.com/reliability.html\#Consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="f944d-275">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="f944d-276">[Vorherigen] (Rabbitmq-event-bus-development-test-environment.md) [weiter] (Test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="f944d-276">[Previous] (rabbitmq-event-bus-development-test-environment.md) [Next] (test-aspnet-core-services-web-apps.md)</span></span>
