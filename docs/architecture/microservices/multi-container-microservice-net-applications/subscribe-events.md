---
title: Abonnieren von Ereignissen
description: '.NET Microservices: Architektur für .NET-Containeranwendungen | Details verstehen zum Veröffentlichen und Abonnieren von Integrationsereignissen.'
ms.date: 01/13/2021
ms.openlocfilehash: c9146ddbdfbf00e743108c07af1f74d7690a17a8
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188724"
---
# <a name="subscribing-to-events"></a><span data-ttu-id="61d65-103">Abonnieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="61d65-103">Subscribing to events</span></span>

<span data-ttu-id="61d65-104">Wenn Sie den Ereignisbus verwenden möchten, müssen Sie zunächst mit den Microservices die Ereignisse abonnieren, die sie erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="61d65-104">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="61d65-105">Diese Funktionalität sollte im empfangenden Microservice ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="61d65-105">That functionality should be done in the receiver microservices.</span></span>

<span data-ttu-id="61d65-106">Im folgenden einfachen Codebeispiel wird veranschaulicht, was in jedem empfangenden Microservice implementiert werden muss, wenn Sie den Dienst starten (in der `Startup`-Klasse), damit ein Abonnement der nötigen Ereignisse erfolgt.</span><span class="sxs-lookup"><span data-stu-id="61d65-106">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="61d65-107">In diesem Fall benötigt der `basket-api`-Microservice ein Abonnement von `ProductPriceChangedIntegrationEvent`- und `OrderStartedIntegrationEvent`-Meldungen.</span><span class="sxs-lookup"><span data-stu-id="61d65-107">In this case, the `basket-api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span>

<span data-ttu-id="61d65-108">Wenn z. B. das `ProductPriceChangedIntegrationEvent`-Ereignis abonniert wird, erkennt der Warenkorbmicroservice Änderungen am Produktpreis und warnt den Benutzer, wenn es eine Änderung an einem Produkt gab, das sich in dessen Warenkorb befindet.</span><span class="sxs-lookup"><span data-stu-id="61d65-108">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user's basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent,
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent,
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="61d65-109">Nachdem dieser Code ausgeführt wurde, lauscht der Abonnenten-Microservice über RabbitMQ-Kanäle.</span><span class="sxs-lookup"><span data-stu-id="61d65-109">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="61d65-110">Wenn eine Meldung des Typs ProductPriceChangedIntegrationEvent eingeht, ruft der Code den Ereignishandler auf, der an ihn übergeben wird, und verarbeitet das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="61d65-110">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="61d65-111">Veröffentlichen von Ereignissen mit dem Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="61d65-111">Publishing events through the event bus</span></span>

<span data-ttu-id="61d65-112">Der Sender der Meldung (der ursprüngliche Microservice) veröffentlicht das Integrationsereignis mit Code wie dem folgenden.</span><span class="sxs-lookup"><span data-stu-id="61d65-112">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="61d65-113">Bei diesem Ansatz handelt es sich um ein vereinfachtes Beispiel, das die Unteilbarkeit nicht berücksichtigt. Wenn Sie ein Ereignis an mehrere Microservices weitergeben müssen, müssen Sie ähnlichen Code implementieren, normalerweise unmittelbar nach dem Committen von Daten oder Transaktionen vom ursprünglichen Microservice.</span><span class="sxs-lookup"><span data-stu-id="61d65-113">(This approach is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="61d65-114">Zunächst wird dann das Ereignisbusimplementierungsobjekt (basierend auf RabbitMQ oder auf einem Service Bus) wie im folgenden Code in den Controllerkonstruktor eingefügt:</span><span class="sxs-lookup"><span data-stu-id="61d65-114">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="61d65-115">Danach verwenden Sie es wie in der UpdateProduct-Methode über die Methoden des Controllers:</span><span class="sxs-lookup"><span data-stu-id="61d65-115">Then you use it from your controller's methods, like in the UpdateProduct method:</span></span>

```csharp
[Route("items")]
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

<span data-ttu-id="61d65-116">In diesem Fall wird dieser Code in einen Web-API-Controller eingefügt, da der ursprüngliche Microservice ein einfacher CRUD-Microservice ist.</span><span class="sxs-lookup"><span data-stu-id="61d65-116">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span>

<span data-ttu-id="61d65-117">In komplexeren Microservices (wenn Sie z.B. CQRS-Ansätze verwenden) kann er in der `CommandHandler`-Klasse in der `Handle()`-Methode implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="61d65-117">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="61d65-118">Entwerfen von Unteilbarkeit und Stabilität beim Veröffentlichen im Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="61d65-118">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="61d65-119">Wenn Sie Integrationsereignisse über ein verteiltes Messaging-System wie Ihren Ereignisbus veröffentlichen, besteht das Problem des unteilbaren Aktualisierens der ursprünglichen Datenbank und Veröffentlichens eines Ereignisses (d.h. entweder beide Vorgänge schließen ab oder keiner von beiden).</span><span class="sxs-lookup"><span data-stu-id="61d65-119">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event (that is, either both operations complete or none of them).</span></span> <span data-ttu-id="61d65-120">Im vereinfachten Codebeispiel von oben committet der Code Daten in der Datenbank, wenn der Produktpreis geändert wird, und veröffentlicht anschließend eine ProductPriceChangedIntegrationEvent-Meldung.</span><span class="sxs-lookup"><span data-stu-id="61d65-120">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="61d65-121">Zunächst erscheint es möglicherweise so, als sei es notwendig, dass diese beiden Vorgänge unteilbar durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="61d65-121">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="61d65-122">Wenn Sie jedoch eine verteilte Transaktion mit der Datenbank und dem Meldungsbroker verwenden, wie auch in älteren Systemen wie [Microsoft Message Queuing (MSMQ)](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)), wird dieser Ansatz nicht empfohlen. Die Gründe werden im [CAP-Theorem](https://www.quora.com/What-Is-CAP-Theorem-1) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61d65-122">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)), this approach is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="61d65-123">Sie verwenden Microservices, um skalierbare und hochverfügbare Systeme zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61d65-123">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="61d65-124">Einfach ausgedrückt besagt das CAP-Theorem, dass es nicht möglich ist, eine (verteilte) Datenbank (oder einen Microservice, der das Modell besitzt) zu erstellen, die gleichzeitig fortlaufend verfügbar, stark konsistent *und* jeder Partition gegenüber tolerant ist.</span><span class="sxs-lookup"><span data-stu-id="61d65-124">Simplifying somewhat, the CAP theorem says that you cannot build a (distributed) database (or a microservice that owns its model) that's continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="61d65-125">Sie müssen sich für zwei dieser drei Eigenschaften entscheiden.</span><span class="sxs-lookup"><span data-stu-id="61d65-125">You must choose two of these three properties.</span></span>

<span data-ttu-id="61d65-126">In auf Microservices basierenden Architekturen sollten Sie sich für Verfügbarkeit und Toleranz entscheiden und die starke Konsistenz vernachlässigen.</span><span class="sxs-lookup"><span data-stu-id="61d65-126">In microservices-based architectures, you should choose availability and tolerance, and you should de-emphasize strong consistency.</span></span> <span data-ttu-id="61d65-127">Deshalb sollten Sie in modernen, microservice-basierten Anwendungen keine verteilten Transaktionen beim Messaging verwenden, wie Sie es tun würden, wenn Sie [verteilte Transaktionen](/previous-versions/windows/desktop/ms681205(v=vs.85)) auf Grundlage von Microsoft Distributed Transaction Coordinator (DTC) mit [MSMQ](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)) implementieren.</span><span class="sxs-lookup"><span data-stu-id="61d65-127">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](/previous-versions/windows/desktop/ms681205(v=vs.85)) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85)).</span></span>

<span data-ttu-id="61d65-128">Kehren wir nun zum ursprünglichen Problem und dem zugehörigen Beispiel zurück.</span><span class="sxs-lookup"><span data-stu-id="61d65-128">Let's go back to the initial issue and its example.</span></span> <span data-ttu-id="61d65-129">Wenn der Dienst abstürzt, nachdem die Datenbank aktualisiert wurde (in diesem Fall nach der Codezeile mit `_context.SaveChangesAsync()`), aber bevor das Integrationsereignis veröffentlich wurde, besteht die Möglichkeit, dass das Gesamtsystem inkonsistent wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-129">If the service crashes after the database is updated (in this case, right after the line of code with `_context.SaveChangesAsync()`), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="61d65-130">Dieser Ansatz ist möglicherweise unternehmenskritisch, je nachdem, welche betrieblichen Vorgänge einbezogen sind.</span><span class="sxs-lookup"><span data-stu-id="61d65-130">This approach might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="61d65-131">Wie bereits im Abschnitt zur Architektur erwähnt, können Sie dieses Problem auf unterschiedliche Arten behandeln:</span><span class="sxs-lookup"><span data-stu-id="61d65-131">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

- <span data-ttu-id="61d65-132">Sie können das [Muster „Ereignissourcing“](/azure/architecture/patterns/event-sourcing) verwenden.</span><span class="sxs-lookup"><span data-stu-id="61d65-132">Using the full [Event Sourcing pattern](/azure/architecture/patterns/event-sourcing).</span></span>

- <span data-ttu-id="61d65-133">Verwenden von Transaktionsprotokollmining.</span><span class="sxs-lookup"><span data-stu-id="61d65-133">Using transaction log mining.</span></span>

- <span data-ttu-id="61d65-134">Sie können das [Muster „Postausgang“](https://www.kamilgrzybek.com/design/the-outbox-pattern/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="61d65-134">Using the [Outbox pattern](https://www.kamilgrzybek.com/design/the-outbox-pattern/).</span></span> <span data-ttu-id="61d65-135">Dabei handelt es sich um eine Transaktionstabelle, die die Integrationsereignisse speichert (und so die lokale Transaktion erweitert).</span><span class="sxs-lookup"><span data-stu-id="61d65-135">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="61d65-136">Für dieses Szenario ist das vollständige Muster „Ereignissourcing“ (ES) einer der besten, wenn nicht *der* beste Ansatz.</span><span class="sxs-lookup"><span data-stu-id="61d65-136">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="61d65-137">Es gibt jedoch viele Anwendungsszenarios, in denen das Implementieren des vollständigen ES-Systems nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="61d65-137">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="61d65-138">ES bedeutet, dass nur Domänenereignisse und keine aktuellen Statusdatendaten in Ihrer Transaktionsdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="61d65-138">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="61d65-139">Wenn nur Domänenereignisse gespeichert werden, kann dies viele Vorteile haben, wie z.B. die Verfügbarkeit des Systemverlaufs, wodurch Sie den Status Ihres Systems zu jedem zurückliegenden Zeitpunkt nachverfolgen können.</span><span class="sxs-lookup"><span data-stu-id="61d65-139">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="61d65-140">Das Implementieren eines vollständigen ES-Systems erfordert jedoch das Neustrukturieren eines Großteils Ihres Systems und geht mit vielen anderen Komplexitäten und Anforderungen einher.</span><span class="sxs-lookup"><span data-stu-id="61d65-140">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="61d65-141">Beispielsweise sollten Sie dann eine Datenbank speziell zum Ereignissourcing verwenden, wie z.B. [Event Store](https://eventstore.org/) oder dokumentorientierte Datenbanken wie Azure Cosmos DB, MongoDB, Cassandra, CouchDB oder RavenDB.</span><span class="sxs-lookup"><span data-stu-id="61d65-141">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://eventstore.org/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="61d65-142">ES ist eine sinnvolle Herangehensweise an dieses Problem, aber nicht die einfachste Lösung, wenn Sie sich noch nicht mit Ereignissourcing auskennen.</span><span class="sxs-lookup"><span data-stu-id="61d65-142">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="61d65-143">Die Option „Transaktionsprotokollmining“ wirkt zunächst transparent.</span><span class="sxs-lookup"><span data-stu-id="61d65-143">The option to use transaction log mining initially looks transparent.</span></span> <span data-ttu-id="61d65-144">Wenn Sie diesen Ansatz verwenden, muss der Microservice allerdings mit Ihrem RDBMS-Transaktionsprotokoll verknüpft werden, wie z.B. mit dem SQL Server-Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="61d65-144">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="61d65-145">Dieser Ansatz ist wahrscheinlich nicht die Ideallösung.</span><span class="sxs-lookup"><span data-stu-id="61d65-145">This approach is probably not desirable.</span></span> <span data-ttu-id="61d65-146">Ein weiterer Nachteil besteht darin, dass Updates auf niedriger Ebene,die im Transaktionsprotokoll erfasst werden, sich möglicherweise nicht auf der gleichen Ebene wie die allgemeinen Integrationsereignisse befinden.</span><span class="sxs-lookup"><span data-stu-id="61d65-146">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="61d65-147">Wenn dies der Fall ist, kann sich der Prozess des Reverse Engineering (Zurückentwicklung) schwierig gestalten.</span><span class="sxs-lookup"><span data-stu-id="61d65-147">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="61d65-148">Ein ausgewogener Ansatz ist eine Mischung aus einer Transaktionsdatenbanktabelle und einem vereinfachten ES-Muster.</span><span class="sxs-lookup"><span data-stu-id="61d65-148">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="61d65-149">Sie können einen Status wie „Ereignis bereit zur Veröffentlichung“ verwenden, den Sie im ursprünglichen Ereignis festlegen, wenn Sie dieses in der Integrationsereignistabelle committen.</span><span class="sxs-lookup"><span data-stu-id="61d65-149">You can use a state such as "ready to publish the event," which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="61d65-150">Dann können Sie das Ereignis im Ereignisbus veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="61d65-150">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="61d65-151">Wenn die Aktion zum Veröffentlichen des Ereignisses erfolgreich durchgeführt wird, starten Sie eine weitere Transaktion im ursprünglichen Dienst, und ändern Sie den Status von „Ereignis bereit zu Veröffentlichung“ in „Ereignis wurde veröffentlicht“.</span><span class="sxs-lookup"><span data-stu-id="61d65-151">If the publish-event action succeeds, you start another transaction in the origin service and move the state from "ready to publish the event" to "event already published."</span></span>

<span data-ttu-id="61d65-152">Wenn die Aktion zum Veröffentlichen des Ereignisses im Ereignisbus fehlschlägt, sind die Daten im ursprünglichen Microservice dennoch nicht inkonsistent. Sie sind weiterhin als „Ereignis bereit zu Veröffentlichung“ gekennzeichnet und bezüglich der anderen Dienste konsistent.</span><span class="sxs-lookup"><span data-stu-id="61d65-152">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as "ready to publish the event," and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="61d65-153">Sie haben immer die Möglichkeit, mit Hintergrundaufgaben die Status der Transaktionen oder Integrationsereignisse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="61d65-153">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="61d65-154">Wenn der Auftrag ein Ereignis mit dem Status „Ereignis bereit zu Veröffentlichung“ findet, kann dieser versuchen, das Ereignis erneut im Ereignisbus zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="61d65-154">If the job finds an event in the "ready to publish the event" state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="61d65-155">Beachten Sie, dass Sie mit diesem Ansatz nur die Integrationsereignisse für jeden ursprünglichen Microservice und nur die Ereignisse, die Sie an andere Microservices oder externe Systeme weitergeben möchten, speichern.</span><span class="sxs-lookup"><span data-stu-id="61d65-155">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="61d65-156">Im Vergleich dazu speichern Sie in einem vollständigen ES-System auch alle Domänenereignisse.</span><span class="sxs-lookup"><span data-stu-id="61d65-156">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="61d65-157">Aus diesem Grund ist dieser ausgewogene Ansatz ein vereinfachtes ES-System.</span><span class="sxs-lookup"><span data-stu-id="61d65-157">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="61d65-158">Sie benötigen eine Liste der Integrationsereignisse mit dem jeweils aktuellen Status („bereit zur Veröffentlichung“ oder „veröffentlicht“).</span><span class="sxs-lookup"><span data-stu-id="61d65-158">You need a list of integration events with their current state ("ready to publish" versus "published").</span></span> <span data-ttu-id="61d65-159">Diese Status müssen Sie aber nur für die Integrationsereignisse implementieren.</span><span class="sxs-lookup"><span data-stu-id="61d65-159">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="61d65-160">Bei diesem Ansatz müssen Sie nicht alle Domänendaten als Ereignisse in der Transaktionsdatenbank speichern, wie Sie dies in einem vollständigen ES-System tun würden.</span><span class="sxs-lookup"><span data-stu-id="61d65-160">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="61d65-161">Wenn Sie bereits eine relationale Datenbank verwenden, können Sie eine Transaktionstabelle verwenden, um Integrationsereignisse zu speichert.</span><span class="sxs-lookup"><span data-stu-id="61d65-161">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="61d65-162">Um die Unteilbarkeit in Ihrer Anwendung zu erreichen, gibt es einen Prozess in zwei Schritten, der auf lokalen Transaktionen basiert.</span><span class="sxs-lookup"><span data-stu-id="61d65-162">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="61d65-163">Dabei gibt es eine IntegrationEvent-Tabelle in der gleichen Datenbank, in der sich auch Ihre Domänenentitäten befinden.</span><span class="sxs-lookup"><span data-stu-id="61d65-163">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="61d65-164">Diese Tabelle stellt sicher, dass Sie die Unteilbarkeit gewährleisten können, damit Sie gespeicherte Integrationsereignisse in den gleichen Transaktionen einbeziehen können, die Ihre Domänendateien committen.</span><span class="sxs-lookup"><span data-stu-id="61d65-164">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="61d65-165">Der Prozess läuft wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="61d65-165">Step by step, the process goes like this:</span></span>

1. <span data-ttu-id="61d65-166">Die Anwendung startet eine lokale Datenbanktransaktion.</span><span class="sxs-lookup"><span data-stu-id="61d65-166">The application begins a local database transaction.</span></span>

2. <span data-ttu-id="61d65-167">Anschließend aktualisiert sie den Status Ihrer Domänenentitäten und fügt ein Ereignis in der Integrationsereignistabelle ein.</span><span class="sxs-lookup"><span data-stu-id="61d65-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span>

3. <span data-ttu-id="61d65-168">Schließlich wird die Transaktion von der Anwendung committet, und die gewünschte Unteilbarkeit wird erreicht.</span><span class="sxs-lookup"><span data-stu-id="61d65-168">Finally, it commits the transaction, so you get the desired atomicity and then</span></span>

4. <span data-ttu-id="61d65-169">Nun veröffentlichen Sie das Ereignis auf eine beliebige Weise (Weiter).</span><span class="sxs-lookup"><span data-stu-id="61d65-169">You publish the event somehow (next).</span></span>

<span data-ttu-id="61d65-170">Wenn Sie die Schritte zum Veröffentlichen von Ereignissen implementieren, haben Sie die folgenden Wahlmöglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="61d65-170">When implementing the steps of publishing the events, you have these choices:</span></span>

- <span data-ttu-id="61d65-171">Sie können das Integrationsereignis unmittelbar nach dem Committen der Transaktion veröffentlichen und eine andere lokale Transaktion verwenden, um die Ereignisse in der Tabelle als „Veröffentlicht“ zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="61d65-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="61d65-172">Verwenden Sie die Tabelle anschließend wie ein Artefakt, um die Integrationsereignisse nachzuverfolgen, falls Probleme bei den Remotemicroservices auftreten, und ergreifen Sie Ausgleichsmaßnahmen auf Grundlage der gespeicherten Integrationsereignisse.</span><span class="sxs-lookup"><span data-stu-id="61d65-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

- <span data-ttu-id="61d65-173">Sie können die Tabelle als eine Art Warteschlange verwenden.</span><span class="sxs-lookup"><span data-stu-id="61d65-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="61d65-174">Ein separater Anwendungsthread oder -prozess fragt die Integrationsereignistabelle ab, veröffentlicht die Ereignisse im Ereignisbus und verwendet anschließend eine lokale Transaktion, um das Ereignis als „Veröffentlicht“ zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="61d65-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="61d65-175">In Abbildung 6-22 wird der Aufbau des ersten Ansatzes veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="61d65-175">Figure 6-22 shows the architecture for the first of these approaches.</span></span>

![Diagramm der Unteilbarkeit beim Veröffentlichen ohne einen Workermicroservice.](./media/subscribe-events/atomicity-publish-event-bus.png)

<span data-ttu-id="61d65-177">**Abbildung 6-22**.</span><span class="sxs-lookup"><span data-stu-id="61d65-177">**Figure 6-22**.</span></span> <span data-ttu-id="61d65-178">Unteilbarkeit beim Veröffentlichen von Ereignissen im Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="61d65-178">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="61d65-179">Dem in Abbildung 6-22 dargestellten Ansatz fehlt ein zusätzlicher Workermicroservice, der dafür zuständig ist, den Erfolg des veröffentlichten Integrationsereignisses zu überprüfen und zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="61d65-179">The approach illustrated in Figure 6-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="61d65-180">Falls das Veröffentlichen fehlschlägt, kann dieser zusätzliche prüfende Workermicroservice Ereignisse aus der Tabelle lesen und erneut veröffentlichen. Wiederholen Sie hierzu den zweiten Schritt.</span><span class="sxs-lookup"><span data-stu-id="61d65-180">In case of failure, that additional checker worker microservice can read events from the table and republish them, that is, repeat step number 2.</span></span>

<span data-ttu-id="61d65-181">Beim zweiten Ansatz verwenden Sie die EventLog-Tabelle als Warteschlange und zusätzlich immer einen Workermicroservice zum Veröffentlichen von Meldungen.</span><span class="sxs-lookup"><span data-stu-id="61d65-181">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="61d65-182">In diesem Fall sieht der Prozess wie in Abbildung 6-23 dargestellt aus.</span><span class="sxs-lookup"><span data-stu-id="61d65-182">In that case, the process is like that shown in Figure 6-23.</span></span> <span data-ttu-id="61d65-183">Hier sehen Sie einen zusätzlichen Microservice. Die Tabelle ist die einzige Quelle beim Veröffentlichen von Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="61d65-183">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![Diagramm der Unteilbarkeit beim Veröffentlichen mit einem Workermicroservice.](./media/subscribe-events/atomicity-publish-worker-microservice.png)

<span data-ttu-id="61d65-185">**Abbildung 6-23**.</span><span class="sxs-lookup"><span data-stu-id="61d65-185">**Figure 6-23**.</span></span> <span data-ttu-id="61d65-186">Unteilbarkeit beim Veröffentlichen von Ereignissen im Ereignisbus mit einem Workermicroservice</span><span class="sxs-lookup"><span data-stu-id="61d65-186">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="61d65-187">Der Einfachheit halber wird im eShopOnContainers-Beispiel der erste Ansatz (ohne zusätzlichen Prozess oder einen prüfenden Microservice) mit einem Ereignisbus verwendet.</span><span class="sxs-lookup"><span data-stu-id="61d65-187">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="61d65-188">Allerdings werden im eShopOnContainers-Beispiel nicht alle möglichen Fehlerfälle behandelt.</span><span class="sxs-lookup"><span data-stu-id="61d65-188">However, the eShopOnContainers sample is not handling all possible failure cases.</span></span> <span data-ttu-id="61d65-189">In einer echten in der Cloud bereitgestellten Anwendung müssen Sie davon ausgehen, dass früher oder später Probleme auftreten werden und dass Sie Logik zum Überprüfen und erneuten Senden implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="61d65-189">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="61d65-190">Das Verwenden der Tabelle als Warteschlange kann effektiver sein als der erste Ansatz, wenn Sie diese Tabelle als einzige Ereignisquelle beim Veröffentlichen von Ereignissen (mit dem Worker) im Ereignisbus verwenden.</span><span class="sxs-lookup"><span data-stu-id="61d65-190">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them (with the worker) through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="61d65-191">Implementieren von Unteilbarkeit beim Veröffentlichen von Integrationsereignissen im Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="61d65-191">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="61d65-192">Im folgenden Code wird gezeigt, wie Sie eine einzelne Transaktion mit mehreren DbContext-Objekten erstellen, wobei ein Kontext mit den ursprünglichen Daten verknüpft ist, die aktualisiert werden, und der andere mit der IntegrationEventLog-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="61d65-192">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="61d65-193">Die Transaktion im unten stehenden Code ist nicht resilient, wenn bei Verbindungen mit der Datenbank Probleme auftreten, während der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-193">The transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="61d65-194">Dies kann in cloudbasierten Systemen wie Azure SQL Database passieren, wodurch Datenbanken von einem Server auf einen anderen verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="61d65-194">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="61d65-195">Um zu erfahren, wie Sie widerstandsfähige Transaktionen in mehreren Kontexten implementieren, lesen Sie sich den Abschnitt [Implementieren widerstandsfähiger Entity Framework Core SQL-Verbindungen](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) weiter unten in diesem Leitfaden durch.</span><span class="sxs-lookup"><span data-stu-id="61d65-195">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) section later in this guide.</span></span>

<span data-ttu-id="61d65-196">Der Deutlichkeit halber wird im folgenden Beispiel der gesamte Prozess in einem einzigen Codeausschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="61d65-196">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="61d65-197">Die eShopOnContainers-Implementierung wird jedoch umgestaltet und teilt diese Logik in mehrere Klassen auf, sodass sie leichter verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="61d65-197">However, the eShopOnContainers implementation is refactored and splits this logic into multiple classes so it's easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem productToUpdate)
{
  var catalogItem =
       await _catalogContext.CatalogItems.SingleOrDefaultAsync(i => i.Id ==
                                                               productToUpdate.Id);
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

  // Just save the updated product if the Product's Price hasn't changed.
  if (!raiseProductPriceChangedEvent)
  {
      await _catalogContext.SaveChangesAsync();
  }
  else  // Publish to event bus only if product price changed
  {
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

      // Publish the integration event through the event bus
      _eventBus.Publish(priceChangedEvent);

      _integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent);
  }

  return Ok();
}

```

<span data-ttu-id="61d65-198">Nachdem das Integrationsereignis ProductPriceChangedIntegrationEvent erstellt wurde, beinhaltet die Transaktion, die den ursprünglichen Domänenvorgang (das Aktualisieren des Katalogelements) speichert, auch das Speichern des Ereignisses in der EventLog-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="61d65-198">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="61d65-199">Dadurch wird es zu einer einzelnen Transaktion, und Sie können immer überprüfen, ob Ereignismeldungen gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="61d65-199">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="61d65-200">Die EventLog-Tabelle wird unteilbar mit dem ursprünglichen Datenbankvorgang aktualisiert. Dafür wird eine lokale Transaktion mit der gleichen Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="61d65-200">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="61d65-201">Wenn einer der Vorgänge fehlschlägt, wird eine Ausnahme ausgelöst und die Transaktion führt einen Rollback für abgeschlossene Vorgänge aus, sodass die Konsistenz zwischen Domänenvorgängen und den in der Tabelle gespeicherten Ereignismeldungen gewährleistet wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-201">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages saved to the table.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="61d65-202">Empfangen von Abonnementmeldungen: Ereignishandler in empfangenden Microservices</span><span class="sxs-lookup"><span data-stu-id="61d65-202">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="61d65-203">Zusätzlich zur Logik des Ereignisabonnements müssen Sie den internen Code für den Integrationsereignishandler implementieren (wie eine Rückrufmethode).</span><span class="sxs-lookup"><span data-stu-id="61d65-203">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="61d65-204">Mit dem Ereignishandler geben Sie an, an welcher Stelle eine Ereignismeldung eines bestimmten Typs empfangen und verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-204">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="61d65-205">Ein Ereignishandler empfängt zunächst eine Ereignisschnittstelle vom Ereignisbus.</span><span class="sxs-lookup"><span data-stu-id="61d65-205">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="61d65-206">Anschließend findet er die Komponente, die verarbeitet werden soll und die mit diesem Integrationsereignis verknüpft ist. Dann gibt er das Ereignis als Statusänderung des empfangenden Microservice weiter und speichert es als solche.</span><span class="sxs-lookup"><span data-stu-id="61d65-206">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="61d65-207">Wenn z.B. ein ProductPriceChanged-Ereignis vom Katalog-Microservice ausgeht, wird es im Warenkorb-Microservice verarbeitet und ändert auch den Status des empfangenden Warenkorb-Microservice. Dies wird in folgendem Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="61d65-207">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="61d65-208">Der Ereignishandler muss überprüfen, ob das Produkt in einer Warenkorbinstanz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="61d65-208">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="61d65-209">Außerdem aktualisiert er den Preis für jeden verknüpften Warenkorbartikel.</span><span class="sxs-lookup"><span data-stu-id="61d65-209">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="61d65-210">Zum Schluss erstellt er eine Warnung, die dem Benutzer bezüglich der Preisänderung angezeigt wird. Dies wird in Abbildung 6-24 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="61d65-210">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 6-24.</span></span>

![Screenshot eines Browsers, der die Benachrichtigung zur Preisänderung im Warenkorb des Benutzers zeigt.](./media/subscribe-events/display-item-price-change.png)

<span data-ttu-id="61d65-212">**Abbildung 6-24**.</span><span class="sxs-lookup"><span data-stu-id="61d65-212">**Figure 6-24**.</span></span> <span data-ttu-id="61d65-213">Preisänderung in einem Warenkorb wie von Integrationsereignissen gemeldet</span><span class="sxs-lookup"><span data-stu-id="61d65-213">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="61d65-214">Idempotenz bei Updatemeldungsereignissen</span><span class="sxs-lookup"><span data-stu-id="61d65-214">Idempotency in update message events</span></span>

<span data-ttu-id="61d65-215">Ein wichtiger Aspekt von Updatemeldungsereignissen ist die Tatsache, dass die Meldung abgerufen wird, sobald an irgendeinem Punkt in der Kommunikation ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="61d65-215">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="61d65-216">Andernfalls versucht möglicherweise ein Hintergrundtask, ein Ereignis zu veröffentlichen, das bereits veröffentlich wurde, sodass eine Racebedingung verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-216">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="61d65-217">Sie müssen sicherstellen, dass die Updates entweder idempotent sind oder ausreichend Informationen bereitstellen, damit Sie ein Duplikat erkennen, dieses verwerfen und nur eine Antwort zurücksenden können.</span><span class="sxs-lookup"><span data-stu-id="61d65-217">Make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="61d65-218">Wie bereits erwähnt bedeutet Idempotenz, dass ein Vorgang mehrmals durchgeführt werden kann, ohne dass das Ergebnis sich verändert.</span><span class="sxs-lookup"><span data-stu-id="61d65-218">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="61d65-219">In einer Messagingumgebung, z.B. beim Übermitteln von Ereignissen, ist ein Ereignis idempotent, wenn es mehrmals übergeben werden kann, ohne dass sich das Ergebnis für den empfangenden Microservice ändert.</span><span class="sxs-lookup"><span data-stu-id="61d65-219">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="61d65-220">Dies kann aufgrund der Beschaffenheit eines Ereignisses selbst oder aufgrund der Art der Ereignisbehandlung des Systems erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="61d65-220">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="61d65-221">Meldungsidempotenz ist in jeder Anwendung, die Messaging verwendet, von hoher Bedeutung, und nicht nur in Anwendungen, die das Ereignisbusmuster implementieren.</span><span class="sxs-lookup"><span data-stu-id="61d65-221">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="61d65-222">Eine SQL-Anweisung, die Daten nur dann in eine Tabelle einfügt, wenn diese noch nicht in der Tabelle vorhanden sind, ist ein Beispiel für einen idempotenten Vorgang.</span><span class="sxs-lookup"><span data-stu-id="61d65-222">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="61d65-223">Es ist unerheblich, wie oft Sie diese SQL-Anweisung zum Einfügen ausführen, das Ergebnis ist immer das gleiche: die Tabelle enthält die entsprechenden Daten.</span><span class="sxs-lookup"><span data-stu-id="61d65-223">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="61d65-224">Derartige Idempotenz kann auch nötig sein, wenn Sie Meldungen behandeln müssen und diese Meldungen theoretisch mehrmals gesendet und deshalb auch mehrmals verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="61d65-224">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="61d65-225">Wenn z.B. RETRY-Logik dazu führt, dass ein Sender die gleiche Meldung mehr als einmal verschickt, müssen Sie sicherstellen, dass sie idempotent ist.</span><span class="sxs-lookup"><span data-stu-id="61d65-225">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="61d65-226">Es ist möglich, idempotente Meldungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61d65-226">It is possible to design idempotent messages.</span></span> <span data-ttu-id="61d65-227">Sie können z.B. ein Ereignis erstellen, das „Produktpreis auf $25 festlegen“ statt „Produktpreis plus $5“ festlegt.</span><span class="sxs-lookup"><span data-stu-id="61d65-227">For example, you can create an event that says "set the product price to $25" instead of "add $5 to the product price."</span></span> <span data-ttu-id="61d65-228">Die erste Meldung können Sie ohne Bedenken beliebig oft verarbeiten, ohne dass sich das Ergebnis verändert.</span><span class="sxs-lookup"><span data-stu-id="61d65-228">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="61d65-229">Dies trifft nicht auf die zweite Meldung zu.</span><span class="sxs-lookup"><span data-stu-id="61d65-229">That is not true for the second message.</span></span> <span data-ttu-id="61d65-230">Aber selbst im zweiten Fall sollten Sie auch nicht das erste Ereignis verarbeiten, da das System möglicherweise schon ein neueres Ereignis zur Preisänderung gesendet hat und Sie so den neuen Preis überschreiben würden.</span><span class="sxs-lookup"><span data-stu-id="61d65-230">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="61d65-231">Ein weiteres Beispiel ist ein Ereignis zum Abschluss der Bestellung, das an mehrere Abonnenten übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-231">Another example might be an order-completed event that's propagated to multiple subscribers.</span></span> <span data-ttu-id="61d65-232">Die App muss sicherstellen, dass Informationen in anderen Systemen nur einmal aktualisiert werden, auch wenn es duplizierte Meldungsereignisse für das gleiche Ereignis zum Abschluss der Bestellung gibt.</span><span class="sxs-lookup"><span data-stu-id="61d65-232">The app has to make sure that order information is updated in other systems only once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="61d65-233">Es ist praktisch, eine Art Identität pro Ereignis zu haben, damit Sie Logik erstellen können, die erzwingt, dass jedes Ereignis nur einmal pro Empfänger verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="61d65-233">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="61d65-234">Es gibt Meldungsverarbeitungen, die von sich aus idempotent sind.</span><span class="sxs-lookup"><span data-stu-id="61d65-234">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="61d65-235">Wenn ein System z.B. Bildminiaturansichten generiert, ist es egal, wie oft die Meldung zur generierten Miniaturansicht verarbeitet wird. Das Ergebnis ist, dass die Miniaturansichten generiert werden, und das jedes Mal gleich.</span><span class="sxs-lookup"><span data-stu-id="61d65-235">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="61d65-236">Andererseits können Vorgänge wie das Aufrufen eines Bezahlungsgateways zum Belasten einer Kreditkarte möglicherweise nicht idempotent sein.</span><span class="sxs-lookup"><span data-stu-id="61d65-236">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="61d65-237">In diesen Fällen müssen Sie sicherstellen, dass die mehrfache Meldungsverarbeitung die von Ihnen erwarteten Folgen hat.</span><span class="sxs-lookup"><span data-stu-id="61d65-237">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="61d65-238">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="61d65-238">Additional resources</span></span>

- <span data-ttu-id="61d65-239">**Honoring message idempotency (Berücksichtigen der Idempotenz von Nachrichten)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-239">**Honoring message idempotency** </span></span>\
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591565(v=pandp.10)#honoring-message-idempotency>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="61d65-240">Deduplizieren von Integrationsereignismeldungen</span><span class="sxs-lookup"><span data-stu-id="61d65-240">Deduplicating integration event messages</span></span>

<span data-ttu-id="61d65-241">Sie können sicherstellen, dass Meldungsereignisse nur einmal pro Abonnent auf verschiedenen Ebenen gesendet und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="61d65-241">You can make sure that message events are sent and processed only once per subscriber at different levels.</span></span> <span data-ttu-id="61d65-242">Dies können Sie z.B. mit einem Deduplizierungsfeature erreichen, das von der Meldungsinfrastruktur bereitgestellt wird, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="61d65-242">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="61d65-243">Eine weitere Möglichkeit ist das Implementieren benutzerdefinierter Logik in Ihrem Zielmicroservice.</span><span class="sxs-lookup"><span data-stu-id="61d65-243">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="61d65-244">Der sicherste Weg ist die Validierung sowohl auf der Transport- als auch der Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="61d65-244">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="61d65-245">Deduplizieren von Meldungsereignissen auf Ereignishandlerebene</span><span class="sxs-lookup"><span data-stu-id="61d65-245">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="61d65-246">Sie können sicherstellen, dass ein Ereignis nur einmal von einem beliebigen Empfänger verarbeitet wird, indem Sie eine bestimmte Logik implementieren, wenn Meldungsereignisse in Ereignishandlern verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="61d65-246">One way to make sure that an event is processed only once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="61d65-247">Ein Beispiel hierfür ist der in der eShopOnContainers-App verwendete Ansatz, den Sie im [Quellcode der UserCheckoutAcceptedIntegrationEventHandler-Klasse](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) beim Erhalt eines `UserCheckoutAcceptedIntegrationEvent`-Integrationsereignisses sehen können.</span><span class="sxs-lookup"><span data-stu-id="61d65-247">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code of the UserCheckoutAcceptedIntegrationEventHandler class](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) when it receives a `UserCheckoutAcceptedIntegrationEvent` integration event.</span></span> <span data-ttu-id="61d65-248">(In diesem Fall wird `CreateOrderCommand` mit `IdentifiedCommand` umschlossen, wobei `eventMsg.RequestId` als Bezeichner verwendet wird, bevor das Element an den Befehlshandler gesendet wird.)</span><span class="sxs-lookup"><span data-stu-id="61d65-248">(In this case, the `CreateOrderCommand` is wrapped with an `IdentifiedCommand`, using the `eventMsg.RequestId` as an identifier, before sending it to the command handler).</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="61d65-249">Deduplizieren von Meldungen mit RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="61d65-249">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="61d65-250">Wenn zeitweilig Netzwerkfehler auftreten, können Meldungen dupliziert werden, und der Meldungsempfänger muss dazu bereit sein, diese duplizierten Meldungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="61d65-250">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="61d65-251">Wenn möglich sollten Empfänger Meldungen auf idempotente Weise verarbeiten. Dies ist sinnvoller als das explizite Verarbeiten anhand der Deduplizierung.</span><span class="sxs-lookup"><span data-stu-id="61d65-251">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="61d65-252">In der [RabbitMQ-Dokumentation](https://www.rabbitmq.com/reliability.html#consumer) steht sinngemäß: Wenn eine Meldung an einen Consumer gesendet und anschließend erneut in die Warteschlange eingereiht wird (weil sie nicht bestätigt wurde, bevor die Verbindung zum Consumer abgebrochen ist), legt RabbitMQ das Flag „Redelivered“ (Erneut zugestellt) für diese fest, wenn die Meldung erneut gesendet wird (egal ob an den gleichen Consumer oder nicht).</span><span class="sxs-lookup"><span data-stu-id="61d65-252">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), "If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="61d65-253">Wenn das Flag „Redelivered“ festgelegt ist, muss der Empfänger dieses berücksichtigen, da die Meldung möglicherweise bereits verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="61d65-253">If the "redelivered" flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="61d65-254">Das ist jedoch nicht gesichert. Es kann auch sein, dass die Meldung den Empfänger nie erreicht hat, nachdem sie den Meldungsbroker verlassen hat, möglicherweise aufgrund von Netzwerkproblemen.</span><span class="sxs-lookup"><span data-stu-id="61d65-254">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="61d65-255">Andererseits wurde die Meldung garantiert nicht mehr als einmal gesendet, wenn das Flag „Redelivered“ nicht festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="61d65-255">On the other hand, if the "redelivered" flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="61d65-256">Deshalb muss der Empfänger die Meldungen nur dann deduplizieren oder idempotent verarbeiten, wenn das Flag „Redelivered“ in der Meldung festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="61d65-256">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the "redelivered" flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="61d65-257">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="61d65-257">Additional resources</span></span>

- <span data-ttu-id="61d65-258">**Forked eShopOnContainers using NServiceBus (Particular Software) (Forken von eShopOnContainers mit NServiceBus (Bestimmte Software))**  </span><span class="sxs-lookup"><span data-stu-id="61d65-258">**Forked eShopOnContainers using NServiceBus (Particular Software)** </span></span>\
    <https://go.particular.net/eShopOnContainers>

- <span data-ttu-id="61d65-259">**Event Driven Messaging (Ereignisgesteuertes Messaging)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-259">**Event Driven Messaging** </span></span>\
    <https://patterns.arcitura.com/soa-patterns/design_patterns/event_driven_messaging>

- <span data-ttu-id="61d65-260">**Jimmy Bogard. Refactoring für die Dienstbeständigkeit: Eine Beurteilung der Kopplung** </span><span class="sxs-lookup"><span data-stu-id="61d65-260">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling** </span></span>\
    <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

- <span data-ttu-id="61d65-261">**Publish-Subscribe channel (Kanal zum Veröffentlichen/Abonnieren)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-261">**Publish-Subscribe channel** </span></span>\
    <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- <span data-ttu-id="61d65-262">**Kommunizieren zwischen gebundenen Kontexten** </span><span class="sxs-lookup"><span data-stu-id="61d65-262">**Communicating Between Bounded Contexts** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- <span data-ttu-id="61d65-263">**Letztliche Konsistenz** </span><span class="sxs-lookup"><span data-stu-id="61d65-263">**Eventual Consistency** </span></span>\
    <https://en.wikipedia.org/wiki/Eventual_consistency>

- <span data-ttu-id="61d65-264">**Philip Brown. Strategies for Integrating Bounded Contexts (Strategien zur Integration gebundener Kontexte)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-264">**Philip Brown. Strategies for Integrating Bounded Contexts** </span></span>\
    <https://www.culttt.com/2014/11/26/strategies-integrating-bounded-contexts/>

- <span data-ttu-id="61d65-265">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2 (Entwickeln von Transaktionsmicroservices mit Aggregaten, Event Sourcing und CQRS: Teil 2)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-265">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2** </span></span>\
    <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson>

- <span data-ttu-id="61d65-266">**Chris Richardson. Event Sourcing pattern (Muster: Event Sourcing)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-266">**Chris Richardson. Event Sourcing pattern** </span></span>\
    <https://microservices.io/patterns/data/event-sourcing.html>

- <span data-ttu-id="61d65-267">**Introducing Event Sourcing (Einführung in Event Sourcing)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-267">**Introducing Event Sourcing** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591559(v=pandp.10)>

- <span data-ttu-id="61d65-268">**Event Store-Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="61d65-268">**Event Store database**.</span></span> <span data-ttu-id="61d65-269">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="61d65-269">Official site.</span></span> \
    <https://geteventstore.com/>

- <span data-ttu-id="61d65-270">**Patrick Nommensen. Event-Driven Data Management for Microservices (Ereignisgesteuerte Datenverwaltung für Microservices)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-270">**Patrick Nommensen. Event-Driven Data Management for Microservices** </span></span>\
    <https://dzone.com/articles/event-driven-data-management-for-microservices-1>

- <span data-ttu-id="61d65-271">**The CAP Theorem (Das CAP-Theorem)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-271">**The CAP Theorem** </span></span>\
    <https://en.wikipedia.org/wiki/CAP_theorem>

- <span data-ttu-id="61d65-272">**What is CAP Theorem? (Was ist das CAP-Theorem?)**</span><span class="sxs-lookup"><span data-stu-id="61d65-272">**What is CAP Theorem?**</span></span> \
    <https://www.quora.com/What-Is-CAP-Theorem-1>

- <span data-ttu-id="61d65-273">**Einführung in die Datenkonsistenz** </span><span class="sxs-lookup"><span data-stu-id="61d65-273">**Data Consistency Primer** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- <span data-ttu-id="61d65-274">**Rick Saling. The CAP Theorem: Warum für die Cloud und das Internet andere Regeln gelten** </span><span class="sxs-lookup"><span data-stu-id="61d65-274">**Rick Saling. The CAP Theorem: Why "Everything is Different" with the Cloud and Internet** </span></span>\
    <https://docs.microsoft.com/archive/blogs/rickatmicrosoft/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/>

- <span data-ttu-id="61d65-275">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed (CAP zwölf Jahre später: So haben sich die „Regeln“ verändert)**  </span><span class="sxs-lookup"><span data-stu-id="61d65-275">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed** </span></span>\
    <https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed>

- <span data-ttu-id="61d65-276">**Azure Service Bus. Brokered Messaging: Duplicate Detection (Brokermessaging: Erkennen von Duplikaten)**   </span><span class="sxs-lookup"><span data-stu-id="61d65-276">**Azure Service Bus. Brokered Messaging: Duplicate Detection**  </span></span>\
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- <span data-ttu-id="61d65-277">**Reliability Guide (Zuverlässigkeitsleitfaden)** (RabbitMQ-Dokumentation) </span><span class="sxs-lookup"><span data-stu-id="61d65-277">**Reliability Guide** (RabbitMQ documentation) </span></span>\
    <https://www.rabbitmq.com/reliability.html#consumer>

> [!div class="step-by-step"]
> <span data-ttu-id="61d65-278">[Zurück](rabbitmq-event-bus-development-test-environment.md)
> [Weiter](test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="61d65-278">[Previous](rabbitmq-event-bus-development-test-environment.md)
[Next](test-aspnet-core-services-web-apps.md)</span></span>
