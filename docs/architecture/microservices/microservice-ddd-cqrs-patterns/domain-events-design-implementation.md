---
title: Domänenereignisse. Entwurf und Implementierung
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über Domänenereignisse, ein Schlüsselkonzept zum Herstellen der Kommunikation zwischen Aggregaten
ms.date: 10/08/2018
ms.openlocfilehash: e03abba66945a6434f6a81eaa9f50d53998f346c
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988715"
---
# <a name="domain-events-design-and-implementation"></a>Domänenereignisse: Entwurf und Implementierung

Verwenden Sie Domänenereignisse, um explizit Nebenwirkungen von Änderungen in Ihrer Domäne zu implementieren. Unter Verwendung der DDD-Terminologie bedeutet dies kurz gesagt, dass Sie Domänenereignisse verwenden sollten, um Nebenwirkungen explizit aggregatübergreifend zu implementieren. Verwenden Sie optional für eine bessere Skalierbarkeit und weniger Auswirkungen in Datenbanksperren „Eventual Consistency“ zwischen Aggregaten in der gleichen Domäne.

## <a name="what-is-a-domain-event"></a>Was ist ein Domänenereignis?

Ein Ereignis ist etwas, das in der Vergangenheit geschehen ist. Ein Domänenereignis ist ein Ereignis, das in der Domäne eingetreten ist, und von dem Sie möchten, dass andere Teile der gleichen Domäne (prozessintern) Kenntnis davon nehmen. Die benachrichtigten Teile reagieren in der Regel auf Ereignisse.

Ein wichtiger Vorteil von Domänenereignissen besteht darin, dass Nebenwirkungen explizit ausgedrückt werden können.

Wenn Sie beispielsweise nur Entity Framework verwenden und auf ein Ereignis reagieren müssen, sollten Sie in der Nähe des Ereignisauslösers alles Erforderliche codieren. So wird die Regel implizit mit dem Code gekoppelt. Sie müssen sich den Code ansehen, um zu erkennen, dass die Regel dort implementiert ist.

Andererseits macht die Verwendung von Domänenereignissen das Konzept explizit, weil ein `DomainEvent` und mindestens ein `DomainEventHandler` involviert sind.

Wenn beispielsweise in der Anwendung eShopOnContainers beim Erstellen einer Bestellung der Benutzer zum Käufer wird, wird ein `OrderStartedDomainEvent` ausgelöst und im `ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler` verarbeitet, sodass das zugrunde liegende Konzept offensichtlich ist.

Kurz gesagt: Mit Domänenereignissen können Sie die Domänenregeln ausdrücklich in der ubiquitären Sprache ausdrücken, die von den Domänenexperten bereitgestellt wurde. Domänenereignisse ermöglichen auch eine bessere Trennung der Aufgaben zwischen Klassen in der gleichen Domäne.

Genau wie bei einer Datenbanktransaktion ist es wichtig sicherzustellen, dass entweder alle Vorgänge, die sich auf ein Domänenereignis beziehen, erfolgreich beendet werden, oder keiner davon.

Domänenereignisse ähneln Ereignissen im Messagingstil, unterscheiden sich jedoch in einem wichtigen Punkt. Beim echten Messaging, beim Message Queuing, bei Nachrichtenbrokern oder bei einem Service Bus mit AMQP wird eine Nachricht immer asynchron gesendet und kommuniziert prozess- und computerübergreifend. Dies ist hilfreich beim Integrieren von mehreren Kontextgrenzen, von Microservices oder sogar von verschiedenen Anwendungen. Mit Domänenereignissen soll ein Ereignis über den Domänenvorgang ausgelöst werden, den Sie gerade ausführen, aber alle Nebenwirkungen sollen in der gleichen Domäne auftreten.

Die Domänenereignisse und ihre Nebenwirkungen (die später ausgelösten Aktionen, die vom Ereignishandler verwaltet werden) sollten fast unmittelbar, in der Regel „In-Process“ und in der gleichen Domäne auftreten. Daher könnten Domänenereignisse synchron oder asynchron sein. Integrationsereignisse dagegen sollten immer asynchron sein.

## <a name="domain-events-versus-integration-events"></a>Domänenereignisse im Vergleich zu Integrationsereignissen

Semantisch gesehen sind Domänen- und Integrationsereignisse das gleiche: Benachrichtigungen über etwas, das soeben aufgetreten ist. Ihre Implementierung muss sich jedoch unterscheiden. Domänenereignisse sind einfach per Push übertragene Nachrichten an einen Domänenereignisverteiler, der als In-Memory-Vermittler auf der Grundlage eines IoC-Containers oder einer anderen Methode implementiert werden kann.

Andererseits sollen mit Integrationsereignissen Transaktionen mit ausgeführtem Commit und Updates für zusätzliche Subsysteme weitergegeben werden, wobei es keine Rolle spielt, ob es sich um Microservices, Kontextgrenzen oder externe Anwendungen handelt. Sie sollten daher nur auftreten, wenn die Entität erfolgreich beibehalten wird, denn andernfalls ist es, als hätte der gesamte Vorgang nie stattgefunden.

Wie bereits erwähnt, müssen Integrationsereignisse auf der asynchronen Kommunikation zwischen mehreren Microservices (andere Kontextgrenzen) oder sogar externen Systemen/Anwendungen basieren.

Die Ereignisbusschnittstelle benötigt daher eine Infrastruktur, die die prozessübergreifende und verteilte Kommunikation zwischen potenziellen Remotediensten ermöglicht. Sie kann auf einem kommerziellen Service Bus, Warteschlangen, einer freigegebenen Datenbank, die als Postfach verwendet wird, oder einem anderen verteilten und idealerweise Push-basierten Messagingsystem basieren.

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>Domänenereignisse sind eine bevorzugte Methode zum Auslösen von Nebenwirkungen über mehrere Aggregate innerhalb der gleichen Domäne

Wenn die Ausführung eines Befehls im Zusammenhang mit einer Aggregatinstanz voraussetzt, dass weitere Domänenregeln auf einem oder mehreren zusätzlichen Aggregaten ausgeführt werden, sollten Sie die Nebenwirkungen so entwerfen und implementieren, dass sie von Domänenereignissen ausgelöst werden. Abbildung 7-14 veranschaulicht einen der wichtigsten Anwendungsfälle: Ein Domänenereignis soll verwendet werden, um Zustandsänderungen über mehrere Aggregate innerhalb des gleichen Domänenmodells wiederzugeben.

![Diagramm, das ein Domänenereignis zeigt, das Daten zu einem Käufer-Aggregat steuert.](./media/domain-events-design-implementation/domain-model-ordering-microservice.png)

**Abbildung 7-14**. Domänenereignisse zum Erzwingen der Konsistenz zwischen mehreren Aggregaten in der gleichen Domäne

In Abbildung 7-14 wird gezeigt, wie die Konsistenz zwischen Aggregaten durch Domänenereignisse erzielt wird. Wenn der Benutzer eine Bestellung initiiert, sendet das Order-Aggregat ein `OrderStarted`-Domänenereignis. Das OrderStarted-Domänenereignis wird vom Buyer-Aggregat verarbeitet, um ein Käuferobjekt im Microservice für Bestellungen zu erstellen. Dies erfolgt auf Grundlage der ursprünglichen Benutzerinformationen aus dem Identitäts-Microservice (mit Informationen, die im CreateOrder-Befehl bereitgestellt werden).

Alternativ kann der Aggregatstamm für Ereignisse abonniert werden, die von Mitgliedern seiner Aggregate ausgelöst werden (untergeordnete Entitäten). Jede untergeordnete OrderItem-Entität kann beispielsweise ein Ereignis auslösen, wenn der Artikelpreis über einem bestimmten Betrag liegt oder der Produktartikelbetrag zu hoch ist. Der Aggregatstamm kann dann diese Ereignisse empfangen und eine globale Berechnung oder Aggregation durchführen.

Es ist wichtig zu verstehen, dass diese ereignisbasierte Kommunikation nicht direkt in den Aggregaten implementiert ist, d.h. Sie müssen Domänenereignishandler implementieren.

Die Handhabung der Domänenereignisse ist für eine Anwendung relevant. Die Domänenmodellebene sollte sich nur auf die Domänenlogik konzentrieren, d.h. auf Dinge, die ein Domänenexperte versteht, und nicht auf die Anwendungsinfrastruktur wie Handler und Nebenwirkungspersistenz-Aktionen mithilfe von Repositorys. Daher ist die Ebene der Anwendungsschicht der Ort, an dem Domänenereignishandler Aktionen auslösen, wenn ein Domänenereignis ausgelöst wird.

Domänenereignisse können auch verwendet werden, um eine beliebige Anzahl von Anwendungsaktionen auszulösen. Sie müssen, was noch wichtiger ist, offen sein, um diese Anzahl in der Zukunft entkoppelt zu erhöhen. Wenn beispielsweise die Bestellung gestartet wird, kann es sinnvoll sein, ein Domänenereignis zu veröffentlichen, um diese Informationen an andere Aggregate weiterzuleiten oder sogar Anwendungsaktionen wie Benachrichtigungen auszulösen.

Von zentraler Bedeutung ist hier die offene Anzahl auszuführender Aktionen, wenn ein Domänenereignis auftritt. Letztendlich werden die Aktionen und Regeln in der Domäne und der Anwendung erweitert. Die Komplexität oder die Anzahl von Nebenwirkungsaktionen eines Ereignisses erhöhen sich. Wenn Ihr Code jedoch stark gekoppelt wurde (d. h. bestimmte Objekte werden mit `new` erstellt), müssen Sie jedes Mal den ausgeführten und getesteten Code ändern, wenn Sie eine neue Aktion hinzufügen.

Diese Änderung könnte zu neuen Fehlern führen. Außerdem widerspricht dieser Ansatz dem [Offen/Geschlossen-Prinzip](https://en.wikipedia.org/wiki/Open/closed_principle) von [SOLID](https://en.wikipedia.org/wiki/SOLID). Darüber hinaus wächst dann auch die ursprüngliche Klasse ständig, die die Vorgänge orchestriert, was dem [Prinzip der einzigen Verantwortung](https://en.wikipedia.org/wiki/Single_responsibility_principle) widerspricht.

Wenn Sie Domänenereignisse verwenden, können Sie andererseits eine differenzierte und entkoppelte Implementierung erstellen, indem Sie die Aufgaben mit folgender Methode trennen:

1. Senden Sie einen Befehl (z.B. CreateOrder).
2. Empfangen Sie den Befehl in einem Befehlshandler.
   - Führen Sie eine Transaktion eines einzelnen Aggregats aus.
   - (Optional) Lösen Sie die Domänenereignisse für Nebenwirkungen aus (z.B. OrderStartedDomainEvent).
3. Behandeln Sie die Domänenereignisse (im aktuellen Prozess), die eine offene Anzahl von Nebenwirkungen in mehreren Aggregaten oder Anwendungsaktionen ausführen. Zum Beispiel:
   - Überprüfen oder erstellen Sie Käufer und Zahlungsmethode.
   - Erstellen und senden Sie ein zugehöriges Integrationsereignis an den Ereignisbus, um Zustände über Microservices zu übertragen oder externe Aktionen auszulösen, z.B. Senden einer E-Mail an den Käufer.
   - Behandeln Sie andere Nebenwirkungen.

Wie Abbildung 7-15 zeigt, können Sie ausgehend vom selben Domänenereignis mehrere Aktionen im Zusammenhang mit anderen Aggregaten in der Domäne oder zusätzliche Anwendungsaktionen handhaben, die Sie über Microservices ausführen müssen, wobei eine Verbindung mit Integrationsereignissen und dem Ereignisbus hergestellt wird.

![Diagramm, das ein Domänenereignis zeigt, das Daten an mehrere Ereignishandler übergibt.](./media/domain-events-design-implementation/aggregate-domain-event-handlers.png)

**Abbildung 7-15**. Behandlung mehrerer Aktionen pro Domäne

Es kann mehrere Handler für das gleiche Domänenereignis in der Anwendungsschicht geben. Ein Handler kann die Konsistenz zwischen Aggregaten auflösen, und ein anderer Handler kann ein Integrationsereignis veröffentlichen, damit andere Microservices es verwenden können. Die Ereignishandler befinden sich in der Regel in der Anwendungsschicht, da Sie Infrastrukturobjekte, z. B. Repositorys oder eine Anwendungs-API, für das Microserviceverhalten verwenden. In dieser Hinsicht ähneln Ereignishandler Befehlshandlern, und beide sind Teil der Anwendungsschicht. Der wichtige Unterschied besteht darin, dass ein Befehl nur einmal verarbeitet werden soll. Ein Domänenereignis wird möglicherweise nur null (0) oder *n*-mal verarbeitet, da es von mehreren Empfängern oder Ereignishandlern mit einem anderen Zweck für jeden Handler empfangen werden kann.

Wenn Sie eine offene Anzahl von Handlern pro Domänenereignis verwenden, können Sie beliebig viele Domänenregeln hinzufügen, ohne dass der aktuelle Code beeinträchtigt wird. Das Implementieren der folgenden Geschäftsregel kann sich beispielsweise ebenso einfach gestalten wie das Hinzufügen von einigen Ereignishandlern oder auch nur einem Ereignishandler:

> Wenn der im Rahmen einen beliebigen Anzahl von Bestellungen von einem Kunden im Store für Einkäufe ausgegebene Gesamtbetrag 6.000 Euro überschreitet, wird ein Rabatt von 10 % auf jede neue Bestellung angewendet, und der Kunde wird per E-Mail über diesen Rabatt für zukünftige Bestellungen benachrichtigt.

## <a name="implement-domain-events"></a>Implementieren von Domänenereignissen

In C# ist ein Domänenereignis eine Daten enthaltende Struktur oder Klasse, z.B. ein DTO, mit allen Informationen zu den Ereignissen in der Domäne, wie das folgende Beispiel veranschaulicht:

```csharp
public class OrderStartedDomainEvent : INotification
{
    public string UserId { get; }
    public int CardTypeId { get; }
    public string CardNumber { get; }
    public string CardSecurityNumber { get; }
    public string CardHolderName { get; }
    public DateTime CardExpiration { get; }
    public Order Order { get; }

    public OrderStartedDomainEvent(Order order,
                                   int cardTypeId, string cardNumber,
                                   string cardSecurityNumber, string cardHolderName,
                                   DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

Dies ist im Wesentlichen eine Klasse, die die Daten enthält, die im Zusammenhang mit dem OrderStarted-Ereignis stehen.

Im Hinblick auf die ubiquitäre Sprache der Domäne muss der Klassenname des Ereignisses als Verb in der Vergangenheitsform, z.B. OrderStartedDomainEvent oder OrderShippedDomainEvent, dargestellt werden, da ein Ereignis etwas ist, das in der Vergangenheit aufgetreten ist. Auf diese Weise wird das Domänenereignis in dem Microservice für Bestellungen in eShopOnContainers implementiert.

Wie bereits erwähnt, ist ein wichtiges Merkmal von Ereignissen, dass es nicht geändert werden soll, da es etwas ist, das in der Vergangenheit aufgetreten ist. Daher muss es eine unveränderliche Klasse sein. Im obigen Code sehen Sie, dass die Eigenschaften schreibgeschützt sind. Es gibt keine Möglichkeit, das Objekt zu aktualisieren. Sie können die entsprechenden Werte nur beim Erstellen festlegen.

Wichtig: Wenn Domänenereignisse asynchron mit einer Warteschlange verarbeitet werden, die eine Serialisierung und Deserialisierung der Ereignisobjekte erfordert, müssen die Eigenschaften auf „privat“ statt „schreibgeschützt“ festgelegt werden, damit der Deserialisierer die Werte beim Entfernen aus der Warteschlange zuweisen kann. Das ist kein Problem im Microservice für Bestellungen, da das Domänenereignis „Veröffentlichen/Abonnieren“ synchron über MediatR implementiert wird.

### <a name="raise-domain-events"></a>Auslösen von Domänenereignissen

Die nächste Frage lautet, wie ein Domänenereignis ausgelöst wird, damit es seine zugehörigen Ereignishandler erreicht. Mehrere Methoden stehen zur Verfügung.

Udi Dahan hat ursprünglich (z.B. in mehreren Beiträgen wie [Domain Events – Take 2 (Domänenereignisse – Teil 2)](http://udidahan.com/2008/08/25/domain-events-take-2/)) die Verwendung einer statischen Klasse für die Verwaltung und Auslösung von Ereignissen vorgeschlagen. Dazu gehören beispielsweise eine statische Klasse mit dem Namen DomainEvents, die Domänenereignisse sofort auslöst, wenn sie aufgerufen wird, und eine Syntax wie `DomainEvents.Raise(Event myEvent)` verwendet. Jimmy Bogard empfiehlt in seinem Blogbeitrag ([Strengthening your domain: Domain Events (Stärken Ihrer Domäne: Domänenereignisse)](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) einen ähnlichen Ansatz.

Wenn die Domänenereignisklasse statisch ist, sendet sie auch sofort an Handler. Dies erschwert das Testen und Debuggen, da die Ereignishandler mit Nebenwirkungslogik unmittelbar nach der Auslösung des Ereignisses ausgeführt werden. Wenn Sie testen und debuggen, sollten Sie sich nur auf das konzentrieren, was in den aktuellen Aggregatklassen geschieht. Achten Sie darauf, dass Sie nicht plötzlich zu anderen Ereignishandlern für Nebenwirkungen im Zusammenhang mit anderen Aggregaten oder anderer Anwendungslogik umgeleitet werden. Aus diesem Grund wurden weitere Methoden entwickelt, die im nächsten Abschnitt erläutert werden.

#### <a name="the-deferred-approach-to-raise-and-dispatch-events"></a>Verzögerter Ansatz zum Auslösen und Verteilen von Ereignissen

Anstatt direkt an einen Ereignishandler für die Domäne zu senden, ist es sinnvoller, die Domänenereignisse einer Sammlung hinzuzufügen und diese Domänenereignisse anschließend *direkt vor* oder *direkt*  *nach dem* Commit der Transaktion zu senden (wie bei SaveChanges in EF). (Diese Methode wurde von Jimmy Bogard in seinem Beitrag [A better domain events pattern (Ein besseres Domänenereignismuster)](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/) beschrieben.)

Es ist wichtig zu entscheiden, ob Sie die Domänenereignisse unmittelbar vor oder unmittelbar nach dem Commit der Transaktion senden, da sie festlegt, ob die Nebenwirkungen als Teil derselben Transaktion oder in unterschiedlichen Transaktionen eingeschlossen werden. Im letzterem Fall müssen Sie sich mit „Eventual Consistency“ über mehrere Aggregate befassen. Dieses Thema wird im nächsten Abschnitt behandelt.

eShopOnContainers verwendet den verzögerten Ansatz. Sie fügen zunächst die Ereignisse in Ihren Entitäten in einer Sammlung oder einer Liste von Ereignissen pro Entität hinzu. Diese Liste sollte Teil des Entitätsobjekts oder besser noch Teil der Basisentitätklasse sein, wie im folgenden Beispiel der Entitätsbasisklasse veranschaulicht:

```csharp
public abstract class Entity
{
     //...
     private List<INotification> _domainEvents;
     public List<INotification> DomainEvents => _domainEvents;

     public void AddDomainEvent(INotification eventItem)
     {
         _domainEvents = _domainEvents ?? new List<INotification>();
         _domainEvents.Add(eventItem);
     }

     public void RemoveDomainEvent(INotification eventItem)
     {
         _domainEvents?.Remove(eventItem);
     }
     //... Additional code
}
```

Wenn Sie ein Ereignis auslösen möchten, fügen Sie es einfach der Ereignissammlung aus Code auf jeder Methode der Aggregat-Stamm-Entität hinzu.

Der folgende Code ist Teil von [Order aggregate-root at eShopOnContainers (Aggregatstamm von Bestellung bei eShopOnContainers)](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) und enthält ein Beispiel:

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
                                                          cardTypeId, cardNumber,
                                                          cardSecurityNumber,
                                                          cardHolderName,
                                                          cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

Beachten Sie, dass die AddDomainEvent-Methode lediglich ein Ereignis der Liste hinzufügt. Es wurde noch kein Ereignis gesendet und noch kein Ereignishandler aufgerufen.

Sie sollten die Ereignisse später senden, wenn Sie ein Commit für die Transaktion an die Datenbank ausgeführt haben. Bei Verwendung von Entity Framework Core bedeutet dies in der SaveChanges-Methode Ihres EF-DbContext wie im folgenden Code:

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<bool> SaveEntitiesAsync(CancellationToken cancellationToken = default(CancellationToken))
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.
        await _mediator.DispatchDomainEventsAsync(this);

        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be committed
        var result = await base.SaveChangesAsync();
    }
}
```

Mit dem Code verteilen Sie die Entitätsereignisse an die entsprechenden Ereignishandler.

Insgesamt gesehen haben Sie das Auslösen eines Domänenereignisses (einfaches Hinzufügen zu einer Liste im Speicher) vom Versand an einen Ereignishandler abgekoppelt. Darüber hinaus haben Sie abhängig von der Art des von Ihnen verwendeten Verteilers die Möglichkeit, die Ereignisse synchron oder asynchron zu verwenden.

Bedenken Sie, dass hier transaktionale Grenzen eine gewichtige Rolle spielen. Wenn Arbeitseinheit und Transaktion mehrere Aggregate umfassen können (wie bei Verwendung von EF Core und einer relationalen Datenbank), kann dies gut funktionieren. Wenn jedoch die Transaktion keine Aggregate umfassen kann, z.B. wenn Sie eine NoSQL-Datenbank wie CosmosDB verwenden, implementieren Sie zusätzliche Schritte, um Konsistenz zu gewährleisten. Dies ist ein weiterer Grund, weshalb das Ignorieren der Persistenz nicht universell ist. Es richtet sich vielmehr nach dem von Ihnen verwendeten Speichersystem.

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>Einzelne Transaktion über Aggregate im Vergleich zu „Eventual Consistency“ über Aggregate

Die Frage, ob eine einzelne Transaktion über Aggregate ausgeführt oder „Eventual Consistency“ über diese Aggregate angenommen werden soll, ist durchaus kontrovers. Viele DDD-Autoren wie Eric Evans und Vaughn Vernon befürworten die Regel: eine Transaktion = ein Aggregat und sprechen sich daher für „Eventual Consistency“ über Aggregate aus. Eric Evans erklärt in seinem Buch *Domain-Driven Design(Domänengesteuertes Design)* beispielsweise Folgendes:

> Es kann nicht davon ausgegangen werden, dass jede Regel, die Aggregate umfasst, jederzeit auf dem neuesten Stand ist. Durch die Ereignisverarbeitung, Batchverarbeitung oder andere Aktualisierungsmechanismen können andere Abhängigkeiten innerhalb einer bestimmten Zeit aufgelöst werden. (Seite 128)

Vaughn Vernon erklärt Folgendes in [Effective Aggregate Design. Part II: Making Aggregates Work Together (Effektive Aggregatentwicklung Teil II: Kooperation von Aggregaten)](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):

> Wenn die Ausführung eines Befehls auf einer Aggregatinstanz erfordert, dass zusätzliche Geschäftsregeln auf einem oder mehreren Aggregaten ausgeführt werden, sollte „Eventual Consistency“ verwendet werden\[...\] Es gibt eine praktische Möglichkeit, „Eventual Consistency“ in einem DDD-Modell zu unterstützen. Eine Aggregatmethode veröffentlicht ein Domänenereignis, das rechtzeitig an einen oder mehrere asynchrone Abonnenten übermittelt wird.

Dieser Grundgedanke basiert auf differenzierten Transaktionen und nicht auf Transaktionen, die mehrere Aggregate oder Entitäten umfassen. Dabei wird davon ausgegangen, dass die Anzahl von Datenbanksperren im zweiten Fall in umfangreichen Anwendungen mit hohen Skalierbarkeitsanforderungen erheblich ist. Wenn anerkannt wird, dass hochskalierbare Anwendungen keine sofortige Transaktionskonsistenz zwischen mehreren Aggregaten benötigen, erleichtert dies die Akzeptanz des Konzepts „Letztliche Konsistenz“. Unternehmen benötigen atomische Änderungen häufig nicht, und es ist stets Aufgabe der Domänenexperten festzustellen, ob bestimmte Vorgänge atomische Transaktionen erfordern. Wenn ein Vorgang immer eine atomische Transaktion zwischen mehreren Aggregaten erfordert, könnten Sie die Frage stellen, ob das Aggregat größer sein sollte oder nicht korrekt konzipiert wurde.

Andere Entwickler und Architekten wie Jimmy Bogard akzeptieren, dass eine einzelne Transaktion mehrere Aggregate umfassen kann. Allerdings nur dann, wenn die zusätzlichen Aggregate mit Nebenwirkungen für den gleichen ursprünglichen Befehl verknüpft sind. In [A better domain events pattern (Ein besseres Domänenmuster)](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/) erklärt Bogard beispielsweise:

> Ich möchte in der Regel, dass die Nebenwirkungen eines Domänenereignisses innerhalb der gleichen logischen Transaktion auftreten, aber nicht unbedingt im Rahmen der Auslösung des Domänenereignisses\[...\] Kurz bevor wir unsere Transaktion committen, senden wir die Ereignisse an ihre jeweiligen Handler.

Sie senden Domänenereignisse unmittelbar *vor* dem Ausführen eines Commits für die ursprüngliche Transaktion, falls die Nebenwirkungen dieser Ereignisse in der gleichen Transaktion eingeschlossen werden sollen. Wenn z.B. die EF DbContext SaveChanges-Methode fehlschlägt, führt die Transaktion einen Rollback aller Änderungen durch, auch des Ergebnisses von Nebenwirkungsvorgängen, die von den zugehörigen Domänenereignishandlern implementiert wurden. Dies ist darauf zurückzuführen, dass der DbContext-Lebensdauerbereich standardmäßig als „bereichsbezogen“ definiert ist. Aus diesem Grund wird das DbContext-Objekt von mehreren Repositoryobjekten, die innerhalb des gleichen Bereichs oder Objektdiagramms instanziiert sind, gemeinsam genutzt. Dies stimmt mit dem HttpRequest-Bereich bei der Entwicklung von Web-API- oder MVC-Apps überein.

Tatsächlich können beide Ansätze (einzelne atomische Transaktion und letztliche Konsistenz) korrekt sein. Ausschlaggebend sind in Wirklichkeit Ihre Domänen- oder Geschäftsanforderungen und die Informationen der Domänenexperten. Ausschlaggebend ist auch, wie skalierbar der Dienst sein soll (differenziertere Transaktionen haben weniger Auswirkungen in Bezug auf die Datenbanksperren). Und schließlich ist auch ausschlaggebend, wie viel Sie in Ihren Code investieren möchten, da „Eventual Consistency“ komplexeren Code voraussetzt, um mögliche aggregatübergreifende Inkonsistenzen zu erkennen,und die Implementierung von Kompensationsaktionen erfordert. Berücksichtigen Sie Folgendes: Wenn Sie Änderungen am ursprünglichen Aggregat committen und später beim Verteilen der Ereignisse ein Problem auftritt und die Handler ihre Nebenwirkungen nicht committen können, sind Inkonsistenzen zwischen Aggregaten die Folge.

Kompensationsaktionen können zugelassen werden, indem beispielsweise die Domänenereignisse in zusätzlichen Datenbanktabellen gespeichert werden, sodass sie Bestandteil der ursprünglichen Transaktion sein können. Anschließend kann ein Batchprozess Inkonsistenzen erkennen und Kompensationsaktionen ausführen, indem die Liste der Ereignisse mit dem aktuellen Status der Aggregate verglichen wird. Die Kompensationsaktionen sind Teil eines komplexen Themas, das Sie eingehend analysieren und u.a. mit dem Geschäftskunden und Domänenexperten erörtern müssen.

In jedem Fall können Sie die Methode auswählen, die Sie benötigen. Der ursprüngliche verzögerte Ansatz – Auslösen des Ereignissen vor dem Committen, damit eine einzelne Transaktion verwendet wird – ist der einfachste Ansatz bei Verwendung von EF Core und einer relationalen Datenbank. In vielen Geschäftsvorgängen ist dieser Ansatz einfacher zu implementieren und zu validieren. Der Ansatz wird auch im Microservice für Bestellungen in eShopOnContainers verwendet.

Aber wie senden Sie eigentlich die Ereignisse an ihre jeweiligen Ereignishandler? Worum handelt es sich beim `_mediator`-Objekt aus dem vorherigen Beispiel? Es steht in Verbindung mit den Verfahren und Artefakten, mit denen Sie Ereignisse und Ereignishandler einander zuordnen können.

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>Der Domänenereignisverteiler: Zuordnen von Ereignissen zu Ereignishandlern

Sobald Sie die Ereignisse senden oder veröffentlichen können, benötigen Sie eine Art Artefakt, das das Ereignis veröffentlicht, damit alle zugehörigen Handler es abrufen und Nebenwirkungen auf der Grundlage des Ereignisses verarbeiten können.

Ein Ansatz ist ein echtes Messagingsystem oder sogar ein Ereignisbus, möglicherweise basierend auf einem Service Bus und nicht auf In-Memory-Ereignissen. Beim ersten Fall wäre das echte Messaging „zu viel“ für die Verarbeitung von Domänenereignissen, da Sie diese Ereignisse lediglich im gleichen Prozess verarbeiten müssen, d.h. in der gleichen Domäne und Anwendungsschicht.

Eine andere Möglichkeit, Ereignisse mehreren Ereignishandlern zuzuordnen, ist die Verwendung der Typenregistrierung in einem IoC-Container, damit Sie dynamisch ableiten können, wohin die Ereignisse gesendet werden sollen. Das heißt, Sie müssen wissen, welche Ereignishandler ein bestimmtes Ereignis abrufen müssen. Abbildung 7-16 zeigt einen vereinfachten Ansatz dafür.

![Diagramm, das einen Domänenereignisverteiler zeigt, der Ereignisse an die geeigneten Handler sendet.](./media/domain-events-design-implementation/domain-event-dispatcher.png)

**Abbildung 7-16**. Domänenereignisverteiler mit IoC

Sie können alle zugrunde liegenden Strukturen und Artefakte entwickeln, die diesen Ansatz selbst umzusetzen. Allerdings können Sie auch verfügbare Bibliotheken wie [MediatR](https://github.com/jbogard/MediatR) verwenden, die im Hintergrund Ihren IoC-Container nutzt. Sie können daher direkt die vordefinierten Schnittstellen und die Veröffentlichungs-/Versandmethode des Vermittlerobjekts verwenden.

Im Code müssen Sie zuerst die Ereignishandlertypen im IoC-Container registrieren, was im folgenden Beispiel [eShopOnContainers Reihenfolge Microservice](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs) gezeigt wird:

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement IAsyncNotificationHandler<>)
        // in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
                                       .GetTypeInfo().Assembly)
                                         .AsClosedTypesOf(typeof(IAsyncNotificationHandler<>));
        // Other registrations ...
    }
}
```

Der Code identifiziert zunächst die Assembly, die die Domänenereignishandler enthält, indem die Assembly, die einen Handler enthält, gesucht wird (mit typeof(ValidateOrAddBuyerAggregateWhenXxxx). Sie können die Assembly aber auch mit jedem anderen Ereignishandler suchen). Da alle Ereignishandler die IAsyncNotificationHandler-Schnittstelle implementieren, sucht der Code dann einfach diese Typen und registriert alle Ereignishandler.

### <a name="how-to-subscribe-to-domain-events"></a>Abonnieren von Domänenereignissen

Bei Verwendung von MediatR muss jeder Ereignishandler einen Ereignistyp verwenden, der für den generischen Parameter der INotificationHandler-Schnittstelle bereitgestellt wird, was Sie im folgenden Code sehen können:

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

Basierend auf der Beziehung zwischen Ereignis und Ereignishandler, die als Abonnement betrachtet werden kann, kann das MediatR-Artefakt alle Ereignishandler für jedes Ereignis erkennen und alle Ereignishandler auslösen.

### <a name="how-to-handle-domain-events"></a>Behandeln von Domänenereignissen

Abschließend implementiert der Ereignishandler in der Regel Anwendungsebenencode, der Infrastrukturrepositorys zum Abrufen der erforderlichen zusätzlichen Aggregate und Ausführen der Domänenlogik der Nebenwirkungen verwendet. Der folgende [Code für Domänenereignishandler auf eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs) veranschaulicht ein Implementierungsbeispiel.

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
                   : INotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;

    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // ...Parameter validations...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ? orderStartedEvent.CardTypeId : 1;
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;

        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }

        buyer.VerifyOrAddPaymentMethod(cardTypeId,
                                       $"Payment Method on {DateTime.UtcNow}",
                                       orderStartedEvent.CardNumber,
                                       orderStartedEvent.CardSecurityNumber,
                                       orderStartedEvent.CardHolderName,
                                       orderStartedEvent.CardExpiration,
                                       orderStartedEvent.Order.Id);

        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer)
                                                                      : _buyerRepository.Add(buyer);

        await _buyerRepository.UnitOfWork
                .SaveEntitiesAsync();

        // Logging code using buyerUpdated info, etc.
    }
}
```

Der vorherige Code für Domänenereignishandlercode wird als Anwendungsebenencode betrachtet, da er Infrastrukturrepositorys verwendet, was im nächsten Abschnitt zur Infrastrukturpersistenzebene erläutert wird. Ereignishandler können auch andere Infrastrukturkomponenten verwenden.

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>Domänenereignisse können Integrationsereignisse generieren, die außerhalb der Grenzen von Microservices veröffentlicht werden sollen

Schließlich ist es wichtig zu erwähnen, dass Ereignisse manchmal über mehrere Microservices verteilt werden sollen. Diese Verteilung ist ein Integrationsereignis und kann von jedem Domänenereignishandler über einen Ereignisbus veröffentlicht werden.

## <a name="conclusions-on-domain-events"></a>Domänenereignisse – Fazit

Verwenden Sie Domänenereignisse, um explizit Nebenwirkungen von Änderungen in Ihrer Domäne zu implementieren. Um die DDD-Terminologie zu verwenden, setzen Sie Domänenereignisse ein, um explizit Nebenwirkungen über ein oder mehrere Aggregate zu implementieren. Verwenden Sie zusätzlich für eine bessere Skalierbarkeit und weniger Auswirkungen in Datenbanksperren Eventual Consistency zwischen Aggregaten in der gleichen Domäne.

Die Referenz-App verwendet [MediatR](https://github.com/jbogard/MediatR), um Domänenereignisse innerhalb einer Transaktion synchron zwischen Aggregaten zu verteilen. Sie können auch eine AMQP-Implementierung wie [RabbitMQ](https://www.rabbitmq.com/) oder [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) verwenden, um Domänenereignisse asynchron zu verteilen. Dies geschieht mithilfe der letztlichen Konsistenz, aber Sie müssen, wie oben erwähnt, die Notwendigkeit von Kompensationsaktionen bei Fehlern berücksichtigen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Greg Young. What is a Domain Event? (Was ist ein Domänenereignis?)** \
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf#page=25>

- **Jan Stenberg. Domain Events and Eventual Consistency (Domänenereignisse und letztliche Konsistenz)**  \
  <https://www.infoq.com/news/2015/09/domain-events-consistency>

- **Jimmy Bogard. A better domain events pattern (Ein verbessertes Domänenereignismuster)**  \
  <https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/>

- **Vaughn Vernon. Effective Aggregate Design - Part II: Making Aggregates Work Together (Effektive Aggregatentwicklung Teil II: Kooperation von Aggregaten)**  \
  [https://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

- **Jimmy Bogard. Strengthening your domain: Domain Events (Stärken Ihrer Domäne: Domänenereignisse)**  \
  <https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>

- **Tony Truong. Domain Events Pattern Example (Beispiel für das Domänenereignismuster)**  \
  <https://www.tonytruong.net/domain-events-pattern-example/>

- **Udi Dahan. How to create fully encapsulated Domain Models (Erstellen eines vollständig gekapselten Domänenmodells)**  \
  <http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

- **Udi Dahan. Domain Events – Take 2 (Domänenereignisse: Teil II)**  \
  <http://udidahan.com/2008/08/25/domain-events-take-2/>

- **Udi Dahan. Domain Events – Salvation (Domänenereignisse: Nachtrag mit Verbesserungen)**  \
  <http://udidahan.com/2009/06/14/domain-events-salvation/>

- **Jan Kronquist. Don't publish Domain Events, return them! (Warum das Zurückgeben dem Veröffentlichen von Domänenereignissen vorzuziehen ist)** \
  <https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/>

- **Cesar de la Torre. Domain Events vs. Integration Events in DDD and microservices architectures (Domänenereignisse vs. Integrationsereignisse in DDD und Microservicearchitekturen)**  \
  <https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/>

>[!div class="step-by-step"]
>[Zurück](client-side-validation.md)
>[Weiter](infrastructure-persistence-layer-design.md)
