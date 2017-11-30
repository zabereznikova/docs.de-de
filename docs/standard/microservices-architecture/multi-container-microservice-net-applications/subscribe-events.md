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
# <a name="subscribing-to-events"></a>Abonnieren von Ereignissen

Der erste Schritt für die Verwendung der Ereignisbus werden die Microservices auf die Ereignisse zu abonnieren, die empfangen werden soll. Sollte der Empfänger Microservices erfolgen.

Im folgende einfachen Code zeigt jeden Empfänger Microservice herrscht implementieren beim Starten des Diensts (d. h. Start class), damit es auf die Ereignisse benötigt abonniert. Beispielsweise muss der basket.api Microservice ProductPriceChangedIntegrationEvent Nachrichten abonnieren. Dadurch sind die Microservice Änderungen beachten, der Produktpreis und ermöglicht es das Warnen des Benutzers über die Änderung des Produkts im Warenkorb eines Benutzers ist.

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

Nachdem dieser Code ausgeführt wird, wird der Abonnent Microservice über RabbitMQ Kanäle überwacht. Wenn jede Nachricht vom Typ ProductPriceChangedIntegrationEvent eingeht, ruft der Code den Ereignishandler, der an Sie übergeben wird und das Ereignis verarbeitet.

## <a name="publishing-events-through-the-event-bus"></a>Veröffentlichen von Ereignissen über den-Ereignisbus

Der Absender der Nachricht (Ursprung Microservice) veröffentlicht schließlich die integrationsereignisse mit Code wie im folgenden Beispiel. (Dies ist ein vereinfachtes Beispiel, der keinen Unteilbarkeit berücksichtigt.) Wenn ein Ereignis über mehrere Microservices, in der Regel nach dem Commit der Daten oder Transaktionen aus der Ursprung Microservice rechten weitergeleitet werden muss, würden Sie ähnlichen Code implementieren.

Das Ereignis Bus Implementierung-Objekt (basierend auf RabbitMQ oder basierend auf einer Servicebus) würde zunächst an den Konstruktor Controller wie im folgenden Code eingegeben werden:

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

Klicken Sie dann verwenden Sie die Klasse des Controllers-Methoden, wie in der UpdateProduct-Methode:

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

In diesem Fall, da der Ursprung Microservice eine einfache CRUD-Microservice ist, wird dieser Code rechts in einem Web-API-Controller platziert. In komplexeren Microservices könnte es in der richtigen CommandHandler-Klasse implementiert werden, nachdem die ursprünglichen Daten übertragen werden.

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>Entwerfen von Unteilbarkeit und Flexibilität bei der Veröffentlichung in den-Ereignisbus

Wenn Sie über ein verteiltes messaging-integrationsereignisse veröffentlichen System wie Ihr Ereignisbus, müssen Sie das Problem der atomar Aktualisieren der ursprünglichen Datenbank und Veröffentlichen eines Ereignisses. Z. B. ein Commit ausgeführt wird in der vereinfachte weiter oben gezeigten Beispiel wird der Code Daten an die Datenbank der Produktpreis wird geändert, und klicken Sie dann veröffentlicht eine Nachricht ProductPriceChangedIntegrationEvent. Es könnte zu Beginn wichtige aussehen, dass diese beiden Vorgänge automatisch ausgeführt werden. Allerdings bei Verwendung eine verteilte Transaktion, die im Zusammenhang mit der Datenbank und der Meldung broker, wie bei älteren Systemen wie [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), dies wird nicht empfohlen, die durch die beschriebenenGründen[CAP Theorem](https://www.quora.com/What-Is-CAP-Theorem-1).

Verwenden Sie im Grunde Microservices, skalierbar und hoch verfügbaren Systeme erstellen. Vereinfachen in einem gewissen, die CAP Pythagoras gibt an, dass eine Datenbank (oder ein Microservice, der das Modell besitzt) erstellt werden kann, die ständig verfügbar ist, werden hoch konsistent, *und* fehlertoleranten jeder Partition. Sie müssen zwei dieser drei Eigenschaften auswählen.

Microservices-basierten Architekturen empfiehlt, Verfügbarkeit und Fehlertoleranz zu gewährleisten, und sollten Sie starken Konsistenz vervielfachung. Aus diesem Grund in die meisten modernen Microservice-basierten Anwendungen, in der Regel nicht möchten verteilte Transaktionen in messaging verwenden wie bei der Implementierung [verteilte Transaktionen](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) basierend auf der Windows-verteilten Transaktion Coordinator (DTC) mit [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).

Gehen Sie an das erste Problem und dessen Beispiel wir noch. Wenn es sich bei einem Absturz des Diensts, nachdem die Datenbank aktualisiert wird (in diesem Fall mit der rechten Maustaste nach der Zeile des Codes mit \_Kontext. SaveChangesAsync()), aber vor der Integration-Ereignis veröffentlicht wird, kann das Gesamtsystem inkonsistent werden. Dies könnte unternehmenswichtig ist, abhängig vom Vorgang entsprechend den geschäftlichen sein, die mit dem Sie arbeiten.

Wie bereits im Architektur-Abschnitt erwähnt, können Sie mehrere Ansätze für den Umgang mit diesem Problem haben:

-   Verwenden Sie die vollständige [Ereignis Sourcing Muster](https://msdn.microsoft.com/en-us/library/dn589792.aspx).

-   Mit [Transaktionsprotokoll Mining](http://www.scoop.it/t/sql-server-transaction-log-mining).

-   Mithilfe der [Postausgang Muster](http://gistlabs.com/2014/05/the-outbox/). Dies ist eine transaktionale Tabelle zum Speichern der integrationsereignisse (erweitern die lokale Transaktion).

In diesem Szenario der vollständigen Ereignis Quellentnahme (ES) Muster ist eine der besten Vorgehensweisen ist dies nicht der *der* best. Allerdings in vielen Anwendungsszenarios Sie zum Implementieren eines vollständigen Systems für die ES möglicherweise nicht. ES bedeutet nur Domäne Ereignisse in die Transaktionsdatenbank aktuellen Zustandsdaten speichern, statt gespeichert. Speichern nur die Ereignisse Domäne möglich Vorteile, z. B. den Verlauf Ihres Systems zur Verfügung und können den Status Ihres Systems jederzeit in der Vergangenheit zu bestimmen. Allerdings Implementierung eines vollständigen Systems für die ES erfordert, dass Sie die meisten Ihres Systems neu entwerfe und führt viele andere Komplexität und Anforderungen. Beispielsweise soll, verwenden Sie eine Datenbank, die speziell für diese Aufgabe für das Ereignis als Quelle, z. B. [Ereignisspeicher](https://geteventstore.com/), oder einer Datenbank dokumentorientiert, z. B. Azure-Cosmos-DB, MongoDB, Cassandra, CouchDB oder RavenDB. ES ist eine hervorragende Ansatz für dieses Problem, jedoch nicht die einfachste Lösung, wenn Sie bereits mit Ereignis sourcing vertraut sind.

Die Option zum Verwenden des Transaktionsprotokolls anfänglich mining sucht sehr transparent. Um diesen Ansatz verwenden, hat der Microservice, an das RDBMS-Transaktionsprotokoll, z. B. das SQL Server-Transaktionsprotokoll gekoppelt werden. Dies ist wahrscheinlich nicht wünschenswert. Ein weiterer Nachteil ist, dass auf der gleichen Ebene wie Ihre allgemeinen-integrationsereignisse kann möglicherweise nicht die Low-Level-Updates im Transaktionsprotokoll aufgezeichnet werden. Wenn dies der Fall ist, können der Prozess der Reverse Engineering diese Transaktion Protokollvorgänge schwierig sein.

Ein Ansatz mit Lastenausgleich ist eine Mischung aus einer transaktionalen Datenbank-Tabelle und eine vereinfachte Vorangestellten Muster. Sie können einen Status, z. B. "kann jetzt so veröffentlichen Sie das Ereignis" die Sie in der ursprünglichen Ereignis aus, wenn Sie es an die Ereignistabelle Integration verbindlich festgelegt. Sie versuchen dann das Ereignis in den-Ereignisbus zu veröffentlichen. Wenn die Veröffentlichung Ereignisaktion erfolgreich ist, Sie eine andere Transaktion in der "Origin"-Dienst gestartet und verschieben den Status von "zum Veröffentlichen des Ereignisses bereit" zu "Ereignis bereits veröffentlicht."

Wenn die veröffentlichen Ereignisaktion im Ereignis fehlschlägt bus, die Daten immer noch nicht mehr innerhalb der Ursprung Microservice inkonsistent – weiterhin als "bereit zum Veröffentlichen des Ereignisses" gekennzeichnet und im Hinblick auf den Rest der Dienste, es schließlich konsistent sein werden. Sie können stets Überprüfen des Zustands der Transaktionen oder integrationsereignisse Hintergrundaufträge verfügen. Falls der Auftrag ein Ereignis in dem Zustand "bereit zum Veröffentlichen des Ereignisses" findet, kann versucht, dieses Ereignis an den-Ereignisbus nur erneut veröffentlichen.

Beachten Sie, dass bei diesem Ansatz Sie beibehalten werden, nur die integrationsereignisse für jede Microservice Ursprung und nur die Ereignisse, die für die Kommunikation mit anderen Microservices oder externen Systemen verwendet werden sollen. Im Gegensatz dazu speichern in einem vollständigen Vorangestellten-System auch alle Domain-Ereignisse.

Dieser Ansatz mit Lastenausgleich ist daher eine vereinfachte Vorangestellten-System. Benötigen Sie eine Liste der Integration von Ereignissen mit ihren aktuellen Status ("bereit zum Veröffentlichen" im Vergleich zu "veröffentlicht"). Jedoch müssen Sie nur diese Zustände für die integrationsereignisse zu implementieren. Und bei dieser Vorgehensweise Sie müssen nicht alle Domänendaten als Ereignisse in die Transaktionsdatenbank speichern wie in einem vollständigen Vorangestellten System aus.

Wenn Sie bereits eine relationale Datenbank verwenden, können Sie eine transaktionale Tabelle, zum Speichern von Ereignissen für Integration. Um die Unteilbarkeit von Transaktionen in der Anwendung zu erzielen, verwenden Sie einen zweistufiger Prozess basierend auf lokale Transaktionen. Im Wesentlichen müssen Sie eine IntegrationEvent-Tabelle in derselben Datenbank, in dem die Domänenentitäten haben. Diese Tabelle funktioniert wie ein Insurance Unteilbarkeit erreichen Sie, sodass Sie enthalten integrationsereignisse in die gleichen Transaktionen beibehalten, die Ihre Daten ein Commit ausgeführt wird.

Schritt für Schritt, der Prozess ist wie folgt: die Anwendung beginnt eine Transaktion für die lokale Datenbank. Anschließend wird der Status Ihrer Domäne Entitäten aktualisiert und ein Ereignis in der Ereignistabelle Integration eingefügt. Schließlich wird die Transaktion bestätigt. Sie erhalten die gewünschte Unteilbarkeit.

Wenn Sie die Schritte zum Veröffentlichen der Ereignisse zu implementieren, müssen Sie diese Optionen aus:

-   Veröffentlichen Sie das Ereignis Integration direkt nach dem Commit der Transaktion, und verwenden Sie eine andere lokale Transaktion, um die Ereignisse in der Tabelle als die zu veröffentlichenden zu markieren. Anschließend verwenden Sie die Tabelle nur als ein Element im Falle von Problemen in remote Microservices-integrationsereignisse verfolgen und Aktionen Sie Ausgleich basierend auf den gespeicherten integrationsereignisse.

-   Verwenden Sie diese Tabelle als eine Art der Warteschlange an. Eine separate Anwendungsthread oder ein Prozess fragt die Ereignistabelle Integration, die Ereignisse in den-Ereignisbus veröffentlicht und anschließend eine lokale Transaktion verwendet, um die Ereignisse zu markieren, die veröffentlicht.

Abbildung 8-22 zeigt die Architektur für die erste der folgenden Ansätze.

![](./media/image23.png)

**Abbildung 8-22**. Unteilbarkeit von Transaktionen beim Veröffentlichen von Ereignissen in den-Ereignisbus

Der Ansatz dargestellt in Abbildung 8-22 fehlt ein Microservice zusätzlichen Worker, die für das Überprüfen und bestätigen den Erfolg der veröffentlichten-integrationsereignisse ist. Falls ein Fehler auftritt kann diese zusätzlichen Checker Worker Microservice Ereignisse aus der Tabelle gelesen und veröffentlichen Sie sie erneut.

Über die zweite Vorgehensweise: Verwenden Sie die EventLog-Tabelle als eine Warteschlange und immer einen Worker-Microservice verwenden, um die Nachrichten zu veröffentlichen. In diesem Fall wird der Prozess wie in Abbildung 8-23 angezeigt. Dies zeigt, dass eine zusätzliche Microservice, und die Tabelle ist die einzige Quelle beim Veröffentlichen von Ereignissen.

![](./media/image24.png)

**Abbildung 8-23**. Unteilbarkeit von Transaktionen beim Veröffentlichen von Ereignissen in den-Ereignisbus mit einem Worker microservice

Zur Vereinfachung verwendet das Beispiel eShopOnContainers beim ersten Ansatz (mit ohne zusätzliche Prozesse oder Checker Microservices) sowie den-Ereignisbus. Die eShopOnContainers ist jedoch nicht alle möglichen Schwachstellen behandeln. In einer realen Anwendung, die in der Cloud bereitgestellt wird müssen Sie die Tatsache, die dass die Probleme werden schließlich auftreten, und Sie müssen implementieren, das Überprüfen und senden Logik zu nutzen. Anhand der Tabelle als eine Warteschlange kann effektiver ist als die erste Methode sein, wenn stehen Ihnen diese Tabelle als einzelne Quelle der Ereignisse aus, wenn sie über den-Ereignisbus zu veröffentlichen.

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>Implementieren Unteilbarkeit von Transaktionen beim Veröffentlichen von integrationsereignisse über den-Ereignisbus

Der folgende Code zeigt, wie Sie eine einzelne Transaktion, die im Zusammenhang mit mehreren DbContext-Objekten erstellen können – ein Kontext, die im Zusammenhang mit der ursprünglichen Daten aktualisiert wird und die zweite Kontext im Zusammenhang mit der IntegrationEventLog-Tabelle.

Beachten Sie, dass die Transaktion in den folgenden Beispielcode nicht stabil, wenn Verbindungen mit der Datenbank Probleme zum Zeitpunkt verfügen, wenn der Code ausgeführt wird. Dies kann geschehen in Cloud-basierten Systemen wie Azure SQL-Datenbank, die Datenbanken auf Servern verschoben werden können. Implementieren robuste Transaktionen in mehreren Kontexten, finden Sie unter der [implementieren robuste Entity Framework Core-SQL-Verbindungen](#implementing_resilient_EFCore_SQL_conns) Abschnitt weiter unten in diesem Handbuch.

Das folgende Beispiel zeigt den gesamten Prozess in ein einzelnes Stück Code, aus Gründen der Klarheit. Allerdings wird die eShopOnContainers-Implementierung wird tatsächlich umgestaltet und teilen Sie diese Logik in mehrere Klassen, daher ist es einfacher zu verwalten.

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

Nachdem das ProductPriceChangedIntegrationEvent Integration-Ereignis erstellt wurde, enthält die Transaktion, die der ursprünglichen domänenvorgang (Update Katalogelements) speichert auch die Dauerhaftigkeit des Ereignisses in der EventLog-Tabelle. Dies erleichtert eine einzelne Transaktion, und Sie werden immer in der Lage sind, überprüfen Sie, ob die ereignismeldungen gesendet wurden.

Die Ereignisprotokoll-Tabelle wird mit der ursprünglichen Datenbankvorgang mit einer lokalen Transaktion für dieselbe Datenbank automatisch aktualisiert. Wenn einer der Vorgänge fehlschlägt, wird eine Ausnahme ausgelöst und ein Rollback der Transaktions alle abgeschlossenen Vorgang, daher Wahrung der Konsistenz zwischen der Domäne und die ereignismeldungen gesendet.

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>Empfangen von Nachrichten aus Abonnements:-Ereignishandler in Empfänger Microservices

Zusätzlich zu der Logik für den Ereignis-Abonnement müssen Sie den internen Code für die Integration Ereignishandler (z. B. eine Rückrufmethode) zu implementieren. Der Ereignishandler wird in dem Sie angeben, in dem die Nachrichten eines bestimmten Typs empfangen und verarbeitet werden.

Ein Ereignishandler-den-Ereignisbus zunächst eine Ereignisinstanz Empfangsvorgänge. Klicken Sie dann sucht er die Komponente zu verarbeitenden im Zusammenhang mit dieses Ereignisses Integration, weitergeben und das Ereignis als eine Änderung in der Empfänger Microservice Zustand beibehalten. Z. B. wenn ein ProductPriceChanged-Ereignis in den Katalog Microservice stammt, er wird in den Warenkorb Microservice behandelt, und ändert sich der Status in dieser Empfänger Warenkorb Microservice sowie, wie im folgenden Code gezeigt.

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

Der Ereignishandler muss überprüfen, ob das Produkt im Warenkorb-Instanzen vorhanden ist. Es wird auch der Artikelpreis für jedes Zeilenelement verwandte Warenkorb aktualisiert. Schließlich erstellt eine Warnung, die dem Benutzer zur Preisänderung angezeigt werden, wie in Abbildung 8-24 dargestellt.

![](./media/image25.png)

**Abbildung 8-24**. Während der Integration Ereignisse übermittelt eine Preisänderung Element in einen Warenkorb angezeigt

## <a name="idempotency-in-update-message-events"></a>Idempotenz in Update nachrichtenereignisse

Ein wichtiger Aspekt der Update-nachrichtenereignisse ist, dass ein Fehler auf einem beliebigen Punkt in der Kommunikation bewirken, dass die Nachricht wiederholt werden sollte. Andernfalls könnten eine Hintergrundtask versuchen, ein Ereignis zu veröffentlichen, die bereits veröffentlicht wurde, erstellen eine Racebedingung. Sie müssen sicherstellen, dass die Updates sind Idempotent oder, dass genügend Informationen, um sicherzustellen, dass Sie, ein Duplikat erkennen können angebotenen verwerfen und Back nur eine Antwort zu senden.

Wie bereits erwähnt, also Idempotenz ein Vorgang mehrere Male ausgeführt werden kann ohne das Ergebnis zu ändern. In einer Umgebung mit messaging wie bei der Kommunikation von Ereignissen ein Ereignis Idempotent ist, wenn es mehrere Male übermittelt werden kann ohne das Ergebnis für den Empfänger Microservice zu ändern. Dies aufgrund der Natur des Ereignisses kann erforderlich sein, oder aufgrund der Art und Weise das System das Ereignis behandelt. Nachricht Idempotenz ist wichtig, in jeder Anwendung, die Messaging verwendet, nicht nur Anwendungen, die das Ereignis Bus Muster zu implementieren.

Ein Beispiel eines Vorgangs Idempotent ist eine SQL­Anweisung, die Daten in eine Tabelle einfügt, nur dann, wenn diese Daten nicht bereits in der Tabelle ist. Es spielt keine wie oft ausführen, mit dem SQL-Anweisung eingefügt; Das Ergebnis wird gleich sein – in der Tabelle werden diese Daten enthalten. Idempotenz wie folgt kann auch erforderlich, die beim Umgang mit Nachrichten, wenn die Nachrichten möglicherweise gesendet werden konnte und daher verarbeiteten mehr als einmal. Z. B., wenn Wiederholungslogik bewirkt, einen Absender dass auf genau die gleiche Nachricht mehrmals zu senden, müssen Sie sicherstellen, dass es Idempotent ist.

Es ist möglich, Entwurf Idempotent Nachrichten. Sie können z. B. ein Ereignis, das besagt, dass erstellen "legen Sie auf den Produktpreis \$25" anstelle von "hinzufügen \$5, um den Produktpreis." Konnte der ersten Nachricht oft problemlos verarbeiten, und das Ergebnis wird gleich sein. Dies ist nicht "true" für die zweite Meldung. Selbst im ersten Fall, Sie möchten jedoch möglicherweise nicht das erste Ereignis zu verarbeiten, da das System auch ein neuer Preis Änderungsereignis gesendet haben konnte und Sie den neuen Preis überschrieben werden würde.

Ein weiteres Beispiel wären ein Auftrag abgeschlossen-Ereignis, das an mehrere Abonnenten weitergegeben wird. Es ist wichtig, dass die Bestellinformationen in anderen Systemen nur einmal aktualisiert werden, auch wenn doppelte nachrichtenereignisse nach demselben Ereignis Auftrag abgeschlossen.

Es ist sinnvoll, eine Art von pro Ereignis Identität verfügen, sodass Sie Logik erstellen können, die erzwingt, dass jedes Ereignis nur einmal pro Empfänger verarbeitet wird.

Verarbeitung von Nachrichten ist grundsätzlich Idempotent. Z. B. wenn ein System Bildminiaturansichten generiert, kann es nicht wie oft ausschlaggebend der Verarbeitung der Nachricht über die generierten Miniaturansicht; Das Ergebnis ist, dass die Miniaturansichten generiert werden, und sie identisch, jedes Mal sind an. Andererseits, Vorgänge wie das Aufrufen einer Zahlungsgateway um eine Kreditkarte Idempotent überhaupt möglicherweise nicht. In diesen Fällen müssen Sie sicherstellen, dass die Verarbeitung einer Nachricht mehrere Male, die Sie erwarten, dass die Wirkung hat.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Nachricht Idempotenz berücksichtigt** (auf dieser Seite Unterüberschrift) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)

## <a name="deduplicating-integration-event-messages"></a>Deduplizieren von ereignismeldungen integration

Sie können sicherstellen, nachrichtenereignisse gesendet und verarbeitet nur einmal pro Abonnent auf unterschiedlichen Ebenen. Eine Möglichkeit ist die Verwendung eine von der Messaginginfrastruktur verwendeten bereitgestellten deduplizierungsfunktion. Eine andere besteht darin, benutzerdefinierte Logik in der Ziel-Microservice zu implementieren. Überprüfungen ist auf der Transportebene und Anwendungsebene am besten.

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>Deduplizieren von nachrichtenereignissen auf der Ebene des Ereignishandlers

Eine Möglichkeit, um sicherzustellen, dass ein Ereignis nur einmal alle Empfänger verarbeitet wird, wird durch bestimmte Logik implementieren, bei der Verarbeitung der Ereignisse in den Ereignishandlern. Z. B. das Ansatz wird in der Anwendung eShopOnContainers ist, wie in der Sie sehen die [Quellcode](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) der beim Empfang eines Befehls CreateOrderCommand OrdersController-Klasse. (In diesem Fall verwenden wir einen HTTP-Anforderung Befehl kein nachrichtenbasierte Befehl, aber die Logik, Sie einen Befehl nachrichtenbasierte Idempotent müssen, ist ähnlich.)

### <a name="deduplicating-messages-when-using-rabbitmq"></a>Deduplizieren von Nachrichten bei Verwendung von RabbitMQ

Wenn vorübergehende Netzwerkausfälle auftreten, Nachrichten können dupliziert werden, und der Empfänger einer Nachricht werden muss, behandeln diese doppelten Nachrichten. Wenn möglich sollte Empfänger Nachrichten auf eine Weise Idempotent verarbeiten die Behandlung dieser explizit bei der Deduplizierung besser ist.

Gemäß der [RabbitMQ Dokumentation](https://www.rabbitmq.com/reliability.html#consumer), "Wenn eine Nachricht übermittelt, die für einen Consumer, und klicken Sie dann in die Warteschlange (da sie nicht bestätigt wurde, bevor die Consumer-Verbindung gelöscht werden, z. B.) RabbitMQ für das neu zugestellte Flag festgelegt es, wenn er erneut (ob an denselben oder einen anderen) übermittelt wird.

Wenn das Flag "neu zugestellte" festgelegt ist, muss der Empfänger, die berücksichtigen, da die Nachricht möglicherweise bereits verarbeitet wurden. Aber nicht gewährleistet ist. die Nachricht möglicherweise nie den Empfänger erreicht haben, nachdem sie den nachrichtenbroker möglicherweise aufgrund von Netzwerkproblemen unterbrochen. Andererseits, wenn das Flag "neu zugestellte" nicht festgelegt ist, wird sichergestellt, dass die Nachricht nicht mehr als einmal gesendet wurden. Daher muss der Empfänger dedupliziert werden sollen oder Prozess Nachrichten auf eine Weise Idempotent nur, wenn das Flag "neu zugestellte" in der Nachricht festgelegt ist.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Ereignis Driven Messaging**
    [*http://soapatterns.org/design\_Muster-Ereignis\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Jimmy Bogard. Umgestaltung für Stabilität: Auswerten Kopplung**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)

-   **Veröffentlichen / Abonnieren-Kanal**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **Kommunikation zwischen Kontexten begrenzt**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)

-   **Eventuelle Konsistenz**
    [*https://en.wikipedia.org/wiki/Eventual\_Konsistenz*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Philip Brown. Strategien für die Integration von begrenzt Kontexten**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)

-   **Chris Rißling. Entwickeln von transaktionalen Microservices mit Aggregate, Sourcing-Ereignis und CQRS - Teil 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)

-   **Chris Rißling. Sourcing-Ereignismuster**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)

-   **Einführung in Ereignis Sourcing**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)

-   **Ereignis-Speicherdatenbank**. Offizielle Website.
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   **Patrick Nommensen. Ereignisgesteuerte Datenverwaltung für Microservices**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*

-   **Der CAP-Theorem**
    [*https://en.wikipedia.org/wiki/CAP\_theorems*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **Was ist die Obergrenze des Pythagoras? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)

-   **Einführung in Data-Konsistenz**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)

-   **Rick Saling an. Der CAP-Theorem: Warum "Alles anders mit der Cloud und dem Internet ist"**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)

-   **Eric Brewer. CAP zwölf Jahren: wie die "Regeln" geändert haben**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)

-   **Extern (DTC) Transaktionen beteiligt** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)

-   **Azure-Servicebus. Brokermessaging: Duplikaterkennung**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)

-   **Zuverlässigkeit Handbuch** (RabbitMQ-Dokumentation) [ *https://www.rabbitmq.com/reliability.html\#Consumer*](https://www.rabbitmq.com/reliability.html%23consumer)




>[!div class="step-by-step"]
[Vorherigen] (Rabbitmq-event-bus-development-test-environment.md) [weiter] (Test-aspnet-core-services-web-apps.md)
