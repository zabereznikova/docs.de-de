---
title: Abonnieren von Ereignissen
description: '.NET Microservices: Architektur für .NET-Containeranwendungen | Details verstehen zum Veröffentlichen und Abonnieren von Integrationsereignissen.'
ms.date: 01/30/2020
ms.openlocfilehash: 544af8035ed23dd6507dfed4944b0c327c81d943
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501814"
---
# <a name="subscribing-to-events"></a>Abonnieren von Ereignissen

Wenn Sie den Ereignisbus verwenden möchten, müssen Sie zunächst mit den Microservices die Ereignisse abonnieren, die sie erhalten sollen. Dies sollte im empfangenden Microservice erfolgen.

Im folgenden einfachen Codebeispiel wird veranschaulicht, was in jedem empfangenden Microservice implementiert werden muss, wenn Sie den Dienst starten (in der `Startup`-Klasse), damit ein Abonnement der nötigen Ereignisse erfolgt. In diesem Fall benötigt der `basket-api`-Microservice ein Abonnement von `ProductPriceChangedIntegrationEvent`- und `OrderStartedIntegrationEvent`-Meldungen.

Wenn z.B. das `ProductPriceChangedIntegrationEvent`-Ereignis abonniert wird, erkennt der Warenkorb-Microservice Änderungen am Produktpreis und warnt den Benutzer, wenn es eine Änderung an einem Produkt gab, das sich in dessen Warenkorb befindet.

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent,
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent,
                   OrderStartedIntegrationEventHandler>();

```

Nachdem dieser Code ausgeführt wurde, lauscht der Abonnenten-Microservice über RabbitMQ-Kanäle. Wenn eine Meldung des Typs ProductPriceChangedIntegrationEvent eingeht, ruft der Code den Ereignishandler auf, der an ihn übergeben wird, und verarbeitet das Ereignis.

## <a name="publishing-events-through-the-event-bus"></a>Veröffentlichen von Ereignissen mit dem Ereignisbus

Der Sender der Meldung (der ursprüngliche Microservice) veröffentlicht das Integrationsereignis mit Code wie dem folgenden. Dabei handelt es sich um ein vereinfachtes Beispiel, das die Unteilbarkeit nicht berücksichtigt. Wenn Sie ein Ereignis an mehrere Microservices weitergeben müssen, müssen Sie ähnlichen Code implementieren, normalerweise unmittelbar nach dem Committen von Daten oder Transaktionen vom ursprünglichen Microservice.

Zunächst wird dann das Ereignisbusimplementierungsobjekt (basierend auf RabbitMQ oder auf einem Service Bus) wie im folgenden Code in den Controllerkonstruktor eingefügt:

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

Danach verwenden Sie es wie in der UpdateProduct-Methode von den Methoden des Controllers aus:

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

In diesem Fall wird dieser Code in einen Web-API-Controller eingefügt, da der ursprüngliche Microservice ein einfacher CRUD-Microservice ist.

In komplexeren Microservices (wenn Sie z.B. CQRS-Ansätze verwenden) kann er in der `CommandHandler`-Klasse in der `Handle()`-Methode implementiert werden.

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>Entwerfen von Unteilbarkeit und Stabilität beim Veröffentlichen im Ereignisbus

Wenn Sie Integrationsereignisse über ein verteiltes Messaging-System wie Ihren Ereignisbus veröffentlichen, besteht das Problem des unteilbaren Aktualisierens der ursprünglichen Datenbank und Veröffentlichens eines Ereignisses (d.h. entweder beide Vorgänge schließen ab oder keiner von beiden). Im vereinfachten Codebeispiel von oben committet der Code Daten in der Datenbank, wenn der Produktpreis geändert wird, und veröffentlicht anschließend eine ProductPriceChangedIntegrationEvent-Meldung. Zunächst erscheint es möglicherweise so, als sei es notwendig, dass diese beiden Vorgänge unteilbar durchgeführt werden. Wenn Sie jedoch eine verteilte Transaktion mit der Datenbank und dem Meldungsbroker verwenden, wie auch in älteren Systemen wie [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), wird dies nicht empfohlen. Die Gründe werden im [CAP-Theorem](https://www.quora.com/What-Is-CAP-Theorem-1) beschrieben.

Sie verwenden Microservices, um skalierbare und hochverfügbare Systeme zu erstellen. Einfach ausgedrückt besagt das CAP-Theorem, dass es nicht möglich ist, eine (verteilte) Datenbank (oder einen Microservice, der das Modell besitzt) zu erstellen, die gleichzeitig fortlaufend verfügbar, stark konsistent *und* ausfalltolerant ist. Sie müssen sich für zwei dieser drei Eigenschaften entscheiden.

In microservices-basierten Architekturen sollten Sie sich für Verfügbarkeit und Toleranz entscheiden und die starke Konsistenz vernachlässigen. Deshalb sollten Sie in modernen, microservice-basierten Anwendungen keine verteilten Transaktionen beim Messaging verwenden, wie Sie es tun würden, wenn Sie [verteilte Transaktionen](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) auf Grundlage von Microsoft Distributed Transaction Coordinator (DTC) mit [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx) implementieren.

Kehren wir nun zum ursprünglichen Problem und dem dazugehörigen Beispiel zurück. Wenn der Dienst abstürzt, nachdem die Datenbank aktualisiert wurde (in diesem Fall nach der Codezeile mit \_context.SaveChangesAsync()), aber bevor das Integrationsereignis veröffentlich wurde, besteht die Möglichkeit, dass das Gesamtsystem inkonsistent wird. Dies ist möglicherweise unternehmenskritisch, je nachdem, um welche Unternehmensvorgänge es sich handelt.

Wie bereits im Abschnitt zur Architektur erwähnt, können Sie dieses Problem auf unterschiedliche Arten behandeln:

- Sie können das [Muster „Ereignissourcing“](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing) verwenden.

- Verwenden von [Transaktionsprotokollmining](https://www.scoop.it/t/sql-server-transaction-log-mining).

- Sie können das [Muster „Postausgang“](https://www.kamilgrzybek.com/design/the-outbox-pattern/) verwenden. Dabei handelt es sich um eine Transaktionstabelle, die die Integrationsereignisse speichert (und so die lokale Transaktion erweitert).

Für dieses Szenario ist das vollständige Muster „Ereignissourcing“ (ES) einer der besten, wenn nicht *der* beste Ansatz. Es gibt jedoch viele Anwendungsszenarios, in denen das Implementieren des vollständigen ES-Systems nicht möglich ist. ES bedeutet, dass nur Domänenereignisse und keine aktuellen Statusdatendaten in Ihrer Transaktionsdatenbank gespeichert werden. Wenn nur Domänenereignisse gespeichert werden, kann dies viele Vorteile haben, wie z.B. die Verfügbarkeit des Systemverlaufs, wodurch Sie den Status Ihres Systems zu jedem zurückliegenden Zeitpunkt nachverfolgen können. Das Implementieren eines vollständigen ES-Systems erfordert jedoch das Neustrukturieren eines Großteils Ihres Systems und geht mit vielen anderen Komplexitäten und Anforderungen einher. Beispielsweise sollten Sie dann eine Datenbank speziell zum Ereignissourcing verwenden, wie z.B. [Event Store](https://eventstore.org/) oder dokumentorientierte Datenbanken wie Azure Cosmos DB, MongoDB, Cassandra, CouchDB oder RavenDB. ES ist eine sinnvolle Herangehensweise an dieses Problem, aber nicht die einfachste Lösung, wenn Sie sich noch nicht mit Ereignissourcing auskennen.

Die Option „Transaktionsprotokollmining“ wirkt zunächst sehr transparent. Wenn Sie diesen Ansatz verwenden, muss der Microservice allerdings mit Ihrem RDBMS-Transaktionsprotokoll verknüpft werden, wie z.B. mit dem SQL Server-Transaktionsprotokoll. Dies ist keine ideale Lösung. Ein weiterer Nachteil besteht darin, dass Updates auf niedriger Ebene,die im Transaktionsprotokoll erfasst werden, sich möglicherweise nicht auf der gleichen Ebene wie die allgemeinen Integrationsereignisse befinden. Wenn dies der Fall ist, kann sich der Prozess des Reverse Engineering (Zurückentwicklung) schwierig gestalten.

Ein ausgewogener Ansatz ist eine Mischung aus einer Transaktionsdatenbanktabelle und einem vereinfachten ES-Muster. Sie können einen Status (z.B. „ready to publish the event“ (Ereignis bereit zur Veröffentlichung)) verwenden, den Sie im ursprünglichen Ereignis festlegen, wenn Sie dieses in der Integrationsereignistabelle committen. Dann können Sie das Ereignis im Ereignisbus veröffentlichen. Wenn die Aktion zum Veröffentlichen des Ereignisses erfolgreich durchgeführt wird, starten Sie eine weitere Transaktion im ursprünglichen Dienst, und ändern Sie den Status von „Ereignis bereit zu Veröffentlichung“ in „event already published“ (Ereignis wurde veröffentlicht).

Wenn die Aktion zum Veröffentlichen des Ereignisses im Ereignisbus fehlschlägt, sind die Daten im ursprünglichen Microservice dennoch nicht inkonsistent. Sie sind weiterhin als „Ereignis bereit zu Veröffentlichung“ gekennzeichnet und bezüglich der anderen Dienste konsistent. Sie haben immer die Möglichkeit, mit Hintergrundaufgaben die Status der Transaktionen oder Integrationsereignisse zu überprüfen. Wenn die Aufgabe ein Ereignis mit dem Status „Ereignis bereit zu Veröffentlichung“ findet, kann sie versuchen, dieses erneut im Ereignisbus zu veröffentlichen.

Beachten Sie, dass Sie mit diesem Ansatz nur die Integrationsereignisse für jeden ursprünglichen Microservice und nur die Ereignisse, die Sie an andere Microservices oder externe Systeme weitergeben möchten, speichern. Im Vergleich dazu speichern Sie in einem vollständigen ES-System auch alle Domänenereignisse.

Aus diesem Grund ist dieser ausgewogene Ansatz ein vereinfachtes ES-System. Sie benötigen eine Liste von Integrationsereignissen mit deren aktuellem Status („bereit zur Veröffentlichung“ oder „veröffentlicht“). Diese Status müssen Sie aber nur für die Integrationsereignisse implementieren. Bei diesem Ansatz müssen Sie nicht alle Domänendaten als Ereignisse in der Transaktionsdatenbank speichern, wie Sie dies in einem vollständigen ES-System tun würden.

Wenn Sie bereits eine relationale Datenbank verwenden, können Sie eine Transaktionstabelle verwenden, um Integrationsereignisse zu speichert. Um die Unteilbarkeit in Ihrer Anwendung zu erreichen, gibt es einen Prozess in zwei Schritten, der auf lokalen Transaktionen basiert. Dabei gibt es eine IntegrationEvent-Tabelle in der gleichen Datenbank, in der sich auch Ihre Domänenentitäten befinden. Diese Tabelle stellt sicher, dass Sie die Unteilbarkeit gewährleisten können, damit Sie gespeicherte Integrationsereignisse in den gleichen Transaktionen einbeziehen können, die Ihre Domänendateien committen.

Der Prozess läuft wie folgt ab:

1. Die Anwendung startet eine lokale Datenbanktransaktion.

2. Anschließend aktualisiert sie den Status Ihrer Domänenentitäten und fügt ein Ereignis in der Integrationsereignistabelle ein.

3. Schließlich wird die Transaktion von der Anwendung committet, und die gewünschte Unteilbarkeit wird erreicht.

4. Nun veröffentlichen Sie das Ereignis auf eine beliebige Weise (Weiter).

Wenn Sie die Schritte zum Veröffentlichen von Ereignissen implementieren, haben Sie die folgenden Wahlmöglichkeiten:

- Sie können das Integrationsereignis unmittelbar nach dem Committen der Transaktion veröffentlichen und eine andere lokale Transaktion verwenden, um die Ereignisse in der Tabelle als „Veröffentlicht“ zu kennzeichnen. Verwenden Sie die Tabelle anschließend wie ein Artefakt, um die Integrationsereignisse nachzuverfolgen, falls Probleme bei den Remotemicroservices auftreten, und ergreifen Sie Ausgleichsmaßnahmen auf Grundlage der gespeicherten Integrationsereignisse.

- Sie können die Tabelle als eine Art Warteschlange verwenden. Ein separater Anwendungsthread oder -prozess fragt die Integrationsereignistabelle ab, veröffentlicht die Ereignisse im Ereignisbus und verwendet anschließend eine lokale Transaktion, um das Ereignis als „Veröffentlicht“ zu kennzeichnen.

In Abbildung 6-22 wird der Aufbau des ersten Ansatzes veranschaulicht.

![Diagramm der Unteilbarkeit beim Veröffentlichen ohne einen Workermicroservice.](./media/subscribe-events/atomicity-publish-event-bus.png)

**Abbildung 6-22**. Unteilbarkeit beim Veröffentlichen von Ereignissen im Ereignisbus

Dem in Abbildung 6-22 dargestellten Ansatz fehlt ein zusätzlicher Workermicroservice, der dafür zuständig ist, den Erfolg des veröffentlichten Integrationsereignisses zu überprüfen und zu bestätigen. Falls das Veröffentlichen fehlschlägt, kann dieser zusätzliche prüfende Workermicroservice Ereignisse aus der Tabelle lesen und erneut veröffentlichen. Wiederholen Sie hierzu den zweiten Schritt.

Beim zweiten Ansatz verwenden Sie die EventLog-Tabelle als Warteschlange und zusätzlich immer einen Workermicroservice zum Veröffentlichen von Meldungen. In diesem Fall sieht der Prozess wie in Abbildung 6-23 dargestellt aus. Hier sehen Sie einen zusätzlichen Microservice. Die Tabelle ist die einzige Quelle beim Veröffentlichen von Ereignissen.

![Diagramm der Unteilbarkeit beim Veröffentlichen mit einem Workermicroservice.](./media/subscribe-events/atomicity-publish-worker-microservice.png)

**Abbildung 6-23**. Unteilbarkeit beim Veröffentlichen von Ereignissen im Ereignisbus mit einem Workermicroservice

Der Einfachheit halber wird im eShopOnContainers-Beispiel der erste Ansatz (ohne zusätzlichen Prozess oder einen prüfenden Microservice) mit einem Ereignisbus verwendet. Allerdings werden nicht alle möglichen Fehlerfälle behandelt. In einer echten in der Cloud bereitgestellten Anwendung müssen Sie davon ausgehen, dass früher oder später Probleme auftreten werden und dass Sie Logik zum Überprüfen und erneuten Senden implementieren müssen. Das Verwenden der Tabelle als Warteschlange kann effektiver sein als der erste Ansatz, wenn Sie diese Tabelle als einzige Ereignisquelle beim Veröffentlichen von Ereignissen (mit dem Worker) im Ereignisbus verwenden.

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>Implementieren von Unteilbarkeit beim Veröffentlichen von Integrationsereignissen im Ereignisbus

Im folgenden Code wird gezeigt, wie Sie eine einzelne Transaktion mit mehreren DbContext-Objekten erstellen, wobei ein Kontext mit den ursprünglichen Daten verknüpft ist, die aktualisiert werden, und der andere mit der IntegrationEventLog-Tabelle.

Beachten Sie, dass die Transaktion im unten stehenden Code nicht widerstandsfähig ist, wenn bei Verbindungen mit der Datenbank Probleme auftreten, während der Code ausgeführt wird. Dies kann in cloudbasierten Systemen wie Azure SQL Database passieren, wodurch Datenbanken von einem Server auf einen anderen verschoben werden können. Um zu erfahren, wie Sie widerstandsfähige Transaktionen in mehreren Kontexten implementieren, lesen Sie sich den Abschnitt [Implementieren widerstandsfähiger Entity Framework Core SQL-Verbindungen](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) weiter unten in diesem Leitfaden durch.

Der Deutlichkeit halber wird im folgenden Beispiel der gesamte Prozess in einem einzigen Codeausschnitt dargestellt. Die eShopOnContainers-Implementierung wird aber eigentlich umgestaltet und teilt diese Logik in mehrere Klassen, sodass sie leichter verwaltet werden kann.

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

      integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent);
  }

  return Ok();
}

```

Nachdem das Integrationsereignis ProductPriceChangedIntegrationEvent erstellt wurde, beinhaltet die Transaktion, die den ursprünglichen Domänenvorgang (das Aktualisieren des Katalogelements) speichert, auch das Speichern des Ereignisses in der EventLog-Tabelle. Dadurch wird es zu einer einzelnen Transaktion, und Sie können immer überprüfen, ob Ereignismeldungen gesendet wurden.

Die EventLog-Tabelle wird unteilbar mit dem ursprünglichen Datenbankvorgang aktualisiert. Dafür wird eine lokale Transaktion mit der gleichen Datenbank verwendet. Wenn einer der Vorgänge fehlschlägt, wird eine Ausnahme ausgelöst und die Transaktion führt einen Rollback für abgeschlossene Vorgänge aus, sodass die Konsistenz zwischen Domänenvorgängen und den in der Tabelle gespeicherten Ereignismeldungen gewährleistet wird.

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>Empfangen von Abonnementmeldungen: Ereignishandler in empfangenden Microservices

Zusätzlich zur Logik des Ereignisabonnements müssen Sie den internen Code für den Integrationsereignishandler implementieren (wie eine Rückrufmethode). Mit dem Ereignishandler geben Sie an, an welcher Stelle eine Ereignismeldung eines bestimmten Typs empfangen und verarbeitet wird.

Ein Ereignishandler empfängt zunächst eine Ereignisschnittstelle vom Ereignisbus. Anschließend findet er die Komponente, die verarbeitet werden soll und die mit diesem Integrationsereignis verknüpft ist. Dann gibt er das Ereignis als Statusänderung des empfangenden Microservice weiter und speichert es als solche. Wenn z.B. ein ProductPriceChanged-Ereignis vom Katalog-Microservice ausgeht, wird es im Warenkorb-Microservice verarbeitet und ändert auch den Status des empfangenden Warenkorb-Microservice. Dies wird in folgendem Code veranschaulicht.

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

Der Ereignishandler muss überprüfen, ob das Produkt in einer Warenkorbinstanz vorhanden ist. Außerdem aktualisiert er den Preis für jeden verknüpften Warenkorbartikel. Zum Schluss erstellt er eine Warnung, die dem Benutzer bezüglich der Preisänderung angezeigt wird. Dies wird in Abbildung 6-24 veranschaulicht.

![Screenshot eines Browsers, der die Benachrichtigung zur Preisänderung im Warenkorb des Benutzers zeigt.](./media/subscribe-events/display-item-price-change.png)

**Abbildung 6-24**. Preisänderung in einem Warenkorb wie von Integrationsereignissen gemeldet

## <a name="idempotency-in-update-message-events"></a>Idempotenz bei Updatemeldungsereignissen

Ein wichtiger Aspekt von Updatemeldungsereignissen ist die Tatsache, dass die Meldung abgerufen wird, sobald an irgendeinem Punkt in der Kommunikation ein Fehler auftritt. Andernfalls versucht möglicherweise ein Hintergrundtask, ein Ereignis zu veröffentlichen, das bereits veröffentlich wurde, sodass eine Racebedingung verursacht wird. Sie müssen sicherstellen, dass die Updates entweder idempotent sind oder genug Informationen bereitstellen, um sicherzustellen, dass Sie ein Duplikat erkennen, dieses verwerfen und nur eine Antwort zurücksenden können.

Wie bereits erwähnt bedeutet Idempotenz, dass ein Vorgang mehrmals durchgeführt werden kann, ohne dass das Ergebnis sich verändert. In einer Messagingumgebung, z.B. beim Übermitteln von Ereignissen, ist ein Ereignis idempotent, wenn es mehrmals übergeben werden kann, ohne dass sich das Ergebnis für den empfangenden Microservice ändert. Dies kann aufgrund der Beschaffenheit eines Ereignisses selbst oder aufgrund der Art der Ereignisbehandlung des Systems erforderlich sein. Meldungsidempotenz ist in jeder Anwendung, die Messaging verwendet, von hoher Bedeutung, und nicht nur in Anwendungen, die das Ereignisbusmuster implementieren.

Eine SQL-Anweisung, die Daten nur dann in eine Tabelle einfügt, wenn diese noch nicht in der Tabelle vorhanden sind, ist ein Beispiel für einen idempotenten Vorgang. Es ist unerheblich, wie oft Sie diese SQL-Anweisung zum Einfügen ausführen, das Ergebnis ist immer das gleiche: die Tabelle enthält die entsprechenden Daten. Derartige Idempotenz kann auch nötig sein, wenn Sie Meldungen behandeln müssen und diese Meldungen theoretisch mehrmals gesendet und deshalb auch mehrmals verarbeitet werden können. Wenn z.B. RETRY-Logik dazu führt, dass ein Sender die gleiche Meldung mehr als einmal verschickt, müssen Sie sicherstellen, dass sie idempotent ist.

Es ist möglich, idempotente Meldungen zu erstellen. Sie können z.B. ein Ereignis erstellen, das „Produktpreis auf $25 festlegen“ statt „Produktpreis plus $5“ festlegt. Die erste Meldung können Sie ohne Bedenken beliebig oft verarbeiten, ohne dass sich das Ergebnis verändert. Dies trifft nicht auf die zweite Meldung zu. Aber selbst im zweiten Fall sollten Sie auch nicht das erste Ereignis verarbeiten, da das System möglicherweise schon ein neueres Ereignis zur Preisänderung gesendet hat und Sie so den neuen Preis überschreiben würden.

Ein weiteres Beispiel ist ein Ereignis zum Abschluss der Bestellung, das an mehrere Abonnenten übermittelt wird. Es ist wichtig, dass Informationen in anderen Systemen nur einmal aktualisiert werden, auch wenn es Meldungsereignisduplikate für das gleiche Ereignis zum Abschluss der Bestellung gibt.

Es ist praktisch, eine Art Identität pro Ereignis zu haben, damit Sie Logik erstellen können, die erzwingt, dass jedes Ereignis nur einmal pro Empfänger verarbeitet wird.

Es gibt Meldungsverarbeitungen, die von sich aus idempotent sind. Wenn ein System z.B. Bildminiaturansichten generiert, ist es egal, wie oft die Meldung zur generierten Miniaturansicht verarbeitet wird. Das Ergebnis ist, dass die Miniaturansichten generiert werden, und das jedes Mal gleich. Andererseits können Vorgänge wie das Aufrufen eines Bezahlungsgateways zum Belasten einer Kreditkarte möglicherweise nicht idempotent sein. In diesen Fällen müssen Sie sicherstellen, dass die mehrfache Meldungsverarbeitung die von Ihnen erwarteten Folgen hat.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Honoring message idempotency (Berücksichtigen der Idempotenz von Nachrichten)**  \
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591565(v=pandp.10)#honoring-message-idempotency>

## <a name="deduplicating-integration-event-messages"></a>Deduplizieren von Integrationsereignismeldungen

Sie können sicherstellen, dass Meldungsereignisse gesendet werden und dann nur einmal pro Abonnent auf verschiedenen Ebenen verarbeitet werden. Dies können Sie z.B. mit einem Deduplizierungsfeature erreichen, das von der Meldungsinfrastruktur bereitgestellt wird, die Sie verwenden. Eine weitere Möglichkeit ist das Implementieren benutzerdefinierter Logik in Ihrem Zielmicroservice. Der sicherste Weg ist die Validierung sowohl auf der Transport- als auch der Anwendungsebene.

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>Deduplizieren von Meldungsereignissen auf Ereignishandlerebene

Sie können sicherstellen, dass ein Ereignis nur einmal von einem beliebigen Empfänger verarbeitet wird, indem Sie bestimmte Logik implementieren, wenn Meldungsereignisse in Ereignishandlern verarbeitet werden. Dies ist z.B. der in der eShopOnContainers-App verwendete Ansatz, wie Sie im [Quellcode der UserCheckoutAcceptedIntegrationEventHandler-Klasse](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) beim Erhalt eines UserCheckoutAcceptedIntegrationEvent-Integrationsereignisses sehen können. (In diesem Fall umschließen wir die CreateOrderCommand mit einer IdentifiedCommand und verwenden die eventMsg.RequestId als Bezeichner vor dem Senden an den Befehlshandler).

### <a name="deduplicating-messages-when-using-rabbitmq"></a>Deduplizieren von Meldungen mit RabbitMQ

Wenn zeitweilig Netzwerkfehler auftreten, können Meldungen dupliziert werden, und der Meldungsempfänger muss dazu bereit sein, diese duplizierten Meldungen zu verarbeiten. Wenn möglich sollten Empfänger Meldungen auf idempotente Weise verarbeiten. Dies ist sinnvoller als das explizite Verarbeiten anhand der Deduplizierung.

In der [RabbitMQ-Dokumentation](https://www.rabbitmq.com/reliability.html#consumer) heißt es, dass, wenn eine Meldung an einen Consumer gesendet wird und anschließend erneut in die Warteschlange eingereiht wird (weil sie nicht bestätigt wurde, bevor die Verbindung zum Consumer abgebrochen ist), RabbitMQ das Flag „Redelivered“ (Erneut zugestellt) festlegt, wenn die Meldung erneut gesendet wird (egal ob an den gleichen Consumer oder nicht).

Wenn das Flag „Redelivered“ festgelegt ist, muss der Empfänger dies beachten, da die Meldung möglicherweise schon verarbeitet wurde. Das ist jedoch nicht gesichert. Es kann auch sein, dass die Meldung den Empfänger nie erreicht hat, nachdem sie den Meldungsbroker verlassen hat, möglicherweise aufgrund von Netzwerkproblemen. Andererseits ist gesichert, dass die Meldung nicht mehr als einmal gesendet wurde, wenn das Flag „Redelivered“ nicht festgelegt wurde. Deshalb muss der Empfänger die Meldungen nur dann deduplizieren oder idempotent verarbeiten, wenn das Flag „Redelivered“ in der Meldung festgelegt wurde.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Forked eShopOnContainers using NServiceBus (Particular Software) (Forken von eShopOnContainers mit NServiceBus (Bestimmte Software))**  \
    <https://go.particular.net/eShopOnContainers>

- **Event Driven Messaging (Ereignisgesteuertes Messaging)**  \
    <https://patterns.arcitura.com/soa-patterns/design_patterns/event_driven_messaging>

- **Jimmy Bogard. Refactoring für die Dienstbeständigkeit: Eine Beurteilung der Kopplung** \
    <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

- **Publish-Subscribe channel (Kanal zum Veröffentlichen/Abonnieren)**  \
    <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- **Kommunizieren zwischen gebundenen Kontexten** \
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- **Letztliche Konsistenz** \
    <https://en.wikipedia.org/wiki/Eventual_consistency>

- **Philip Brown. Strategies for Integrating Bounded Contexts (Strategien zur Integration gebundener Kontexte)**  \
    <https://www.culttt.com/2014/11/26/strategies-integrating-bounded-contexts/>

- **Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2 (Entwickeln von Transaktionsmicroservices mit Aggregaten, Event Sourcing und CQRS: Teil 2)**  \
    <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson>

- **Chris Richardson. Event Sourcing pattern (Muster: Event Sourcing)**  \
    <https://microservices.io/patterns/data/event-sourcing.html>

- **Introducing Event Sourcing (Einführung in Event Sourcing)**  \
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591559(v=pandp.10)>

- **Event Store-Datenbank**. Offizielle Website. \
    <https://geteventstore.com/>

- **Patrick Nommensen. Event-Driven Data Management for Microservices (Ereignisgesteuerte Datenverwaltung für Microservices)**  \
    <https://dzone.com/articles/event-driven-data-management-for-microservices-1>

- **The CAP Theorem (Das CAP-Theorem)**  \
    <https://en.wikipedia.org/wiki/CAP_theorem>

- **What is CAP Theorem? (Was ist das CAP-Theorem?)** \
    <https://www.quora.com/What-Is-CAP-Theorem-1>

- **Einführung in die Datenkonsistenz** \
    <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- **Rick Saling. The CAP Theorem: Why „Everything is Different“ with the Cloud and Internet (Das CAP-Theorem: Warum für die Cloud und das Internet andere „Regeln“ gelten)**  \
    <https://docs.microsoft.com/archive/blogs/rickatmicrosoft/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/>

- **Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed (CAP zwölf Jahre später: So haben sich die „Regeln“ verändert)**  \
    <https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed>

- **Azure Service Bus. Brokered Messaging: Duplicate Detection (Brokermessaging: Erkennen von Duplikaten)**   \
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- **Reliability Guide (Zuverlässigkeitsleitfaden)** (RabbitMQ-Dokumentation) \
    <https://www.rabbitmq.com/reliability.html#consumer>

> [!div class="step-by-step"]
> [Zurück](rabbitmq-event-bus-development-test-environment.md)
> [Weiter](test-aspnet-core-services-web-apps.md)
