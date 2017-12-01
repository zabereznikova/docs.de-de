---
title: Domain-Ereignisse. Entwurf und Implementierung
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Domain-Ereignisse, Entwurf und Implementierung"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2d98b302be4ee72d8225526944fc3e41cbadcb5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="domain-events-design-and-implementation"></a>Domain-Ereignisse: Entwurf und Implementierung

Verwenden Sie Domain-Ereignisse, um explizit Nebeneffekte der Änderungen in Ihrer Domäne zu implementieren. Verwenden Sie in anderen Worten, und verwenden DDD-Terminologie Domäne Ereignisse Nebeneffekte über mehrere Aggregate explizit implementiert. Verwenden Sie optional für eine bessere Skalierbarkeit und weniger Auswirkungen in Datenbanksperren eventuellen Konsistenz zwischen Aggregate innerhalb der gleichen Domäne.

## <a name="what-is-a-domain-event"></a>Was ist ein Ereignis Domäne?

Ein Ereignis ist etwas, das in der Vergangenheit geschehen ist. Ein Ereignis für die Domäne ist, logisch, etwas, das in einer bestimmten Domäne aufgetreten sind, und etwas andere Teile der gleichen Domäne (in-Process) beachten und potenziell auf reagieren soll.

Ein wesentlicher Vorteil des Domain-Ereignisse ist, dass Nebeneffekte, nachdem ein Fehler in einer Domäne aufgetreten explizit statt implizit ausgedrückt werden kann. Diese Seite, die Auswirkungen konsistent sein müssen, damit entweder alle Vorgänge im Zusammenhang mit der Geschäftsaufgabe ausgeführt, oder keine von ihnen. Domain-Ereignisse aktivieren Sie darüber hinaus eine bessere Trennung von Anliegen zwischen Klassen innerhalb der gleichen Domäne.

Z. B. Wenn Sie einfach nur Entity Framework und Entitäten oder sogar Aggregate verwenden, wenn es von einem Anwendungsfall provoked Nebeneffekte werden müssen, werden die implementiert werden als eine implizite Konzept in der gekoppelten Code nach dem ein Fehler aufgetreten. Aber wenn Sie diesen Code einfach angezeigt wird, bemerken Sie möglicherweise nicht diesen Code (den Nebeneffekt) ist Teil der wichtigsten Operation oder eigentlich ein Nebeneffekt ist. Andererseits, vereinfacht die Verwendung von Domain-Ereignisse das Konzept, explizite und ubiquitäre Sprache Teil. Beispielsweise ist in der Anwendung eShopOnContainers erstellen eine Bestellung nicht nur die Reihenfolge; Aktualisieren oder einen Käufer aggregieren basierend auf den ursprünglichen Benutzer erstellt, da der Benutzer ein Käufer nicht ist, bis es eine Bestellung vorhanden ist. Bei Verwendung von Domain-Ereignisse können Sie diese Domäne regelbasiert in die ubiquitäre Sprache Domänenexperten gebotenen explizit Ausdrücken.

Domäne Ereignisse ähneln Sichtdefinitionen messagingstil-Ereignisse mit einem wichtigen Unterschied. Mit echten messaging, Message Queuing-, nachrichtenbroker oder einen Servicebus AMPQ verwenden wird eine Nachricht immer asynchron gesendet und kommuniziert über Prozesse und Computern. Dies ist hilfreich beim Integrieren von mehrere Kontexte begrenzt, Microservices oder sogar bei unterschiedlichen Anwendungen. Mit Domain-Ereignisse auslösen eines Ereignisses aus der Domäne, die Sie aktuell ausführen möchten, enthält jedoch keine Nebeneffekte innerhalb der gleichen Domäne ausgeführt werden sollen.

Die Domäne Ereignisse und ihre Nebeneffekte (die Aktionen im Anschluss daran ausgelöst, die vom Ereignishandler verwaltet werden) sollten fast sofort auftreten, in der Regel in-Process "und" innerhalb der gleichen Domäne. Daher konnte die Domäne Ereignisse synchron oder asynchron sein. -Integrationsereignisse, sollte jedoch immer asynchron sein.

## <a name="domain-events-versus-integration-events"></a>Domain-Ereignisse im Vergleich zu integrationsereignisse

Semantisch gesehen sind Domänen- und Integration Ereignisse das gleiche: Benachrichtigungen über etwas, das soeben aufgetreten ist. Ihre Implementierung muss jedoch unterscheiden. Domain-Ereignisse werden nur Nachrichten, die per Push übertragen, um ein Ereignisverteiler Domäne, die als ein in-Memory-Vermittler basierend auf einen IoC-Container oder andere Methoden implementiert werden konnte.

Andererseits, werden der Zweck der integrationsereignisse Transaktionen mit ausgeführtem Commit und Updates für zusätzliche Subsysteme weitergegeben, ob sie andere Microservices, begrenzt, die den Kontext oder sogar externen Anwendungen sind. Sie sollten daher auftreten, nur wenn die Entität erfolgreich beibehalten wird, seit in vielen Fällen schlägt dies fehl, der gesamte Vorgang tatsächlich nie aufgetreten sind.

Darüber hinaus und als erwähnt, Integration müssen Ereignisse auf asynchrone Kommunikation zwischen mehreren Microservices (andere begrenzt Kontexten) oder sogar externen Systeme/Anwendungen basieren. Bus Ereignisschnittstelle benötigt daher eine Infrastruktur, die ermöglicht die prozessübergreifende Kommunikation zwischen potenziell Remotedienste verteilt. Es können auf eine kommerzielle Servicebus-Warteschlangen, eine freigegebene Datenbank verwendet wird, wie ein Postfach oder andere verteilt basieren und idealerweise push Basis-messaging-Systems.

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>Domain-Ereignisse als eine bevorzugte Methode zum Auslösen von Nebeneffekte über mehrere Aggregate innerhalb der gleichen Domäne

Wenn im Zusammenhang mit einem aggregierten Instanz zusätzliche Domänenregeln für die Ausführung auf eine oder mehrere zusätzliche Aggregate erforderlich, einen Befehl ausführen, sollten Sie entwerfen und implementieren die möglichen Nebeneffekte, die von der Domäne Ereignisse ausgelöst werden. Wie in Abbildung 9-14 und als eines der wichtigsten Anwendungsfälle, ein Ereignis Domäne sollte Zustandsänderungen über mehrere Aggregate innerhalb desselben Modells Domäne weitergegeben.

![](./media/image15.png)

**Abbildung 9 – 14**. Domain-Ereignisse, um Konsistenz zwischen mehrere Aggregate innerhalb der gleichen Domäne zu erzwingen

Wenn der Benutzer eine Bestellung initiiert, löst das Ereignis für die Domäne OrderStarted in der Abbildung Erstellung eines Objekts Käufer in der Reihenfolge Microservice basierend auf den ursprünglichen Benutzerinformationen aus der Identität Microservice (mit Informationen, die im Befehl CreateOrder bereitgestellten) werden. Das Ereignis für die Domäne wird anhand des Aggregats Reihenfolge generiert, wenn es ursprünglich erstellt wird.

Alternativ können Sie aggregierten Stamm für Ereignisse, die ausgelöst wird, von einem Mitglied der Aggregate (untergeordneten Entitäten) abonniert haben. Jede OrderItem untergeordnete Entität kann z. B. ein Ereignis auszulösen, wenn dem Artikelpreis über einen bestimmten Betrag liegt, oder die Menge der Product-Element ist zu hoch. Aggregieren Stamm kann diese Ereignisse empfangen und eine globale Berechnung oder eine Aggregation durchführen.

Es ist wichtig zu verstehen, dass diese Kommunikation ereignisbasierten nicht direkt in die Aggregate implementiert ist. In diesem Fall müssen Sie eine Domäne Ereignishandler implementieren. Behandeln der Ereignisse für die Domäne ist eine Anwendung relevant. Die Domäne der Ebene konzentrieren sich nur auf die Domänenlogik – Dinge, die einer Domäne Expert ansehen würde, nicht Anwendung Infrastrukturkomponenten, wie Handler und Nebeneffekte persistenzaktionen mit Repositorys. Daher ist die Ebene für die Anwendung dort stehen Ihnen sollte Domäne Ereignishandler Aktionen auslösen, wenn eine Domäne-Ereignis ausgelöst wird.

Domain-Ereignisse können auch verwendet werden, um eine beliebige Anzahl von Anwendungsaktionen auszulösen, und was noch wichtiger ist, erhöhen Sie diese Anzahl in der Zukunft entkoppelte so geöffnet sein müssen. Z. B. wenn der Auftrag gestartet wird, können Sie ein Ereignis Domäne weitergegeben, Info zu anderen Aggregaten oder sogar Anwendungsaktionen wie Benachrichtigungen auslösen veröffentlichen möchten.

Wichtige Punkt soll in ist die öffnen Anzahl von Aktionen an, die ausgeführt werden, wenn ein Domain-Ereignis auftritt. Schließlich werden die Aktionen und Regeln in der Domäne und der Anwendung erweitert werden. Die Komplexität oder die Anzahl der Aktionen Nebeneffekte, wenn etwas passiert wächst, jedoch wurden Wenn Code mit "Kleben" gekoppelt (d. h. nur Instanziieren von Objekten mit dem new-Schlüsselwort in C#\#), dann jedes Mal, wenn Sie benötigt, um eine neue Aktion hinzufügen, Sie müssen Ändern Sie den ursprünglichen Code. Dies könnte in neue Fehler kommen, da mit jeder neuen Anforderung Sie der ursprünglichen Codefluss ändern müssen würde. Dies gilt für die [Öffnen/geschlossen Prinzip](https://en.wikipedia.org/wiki/Open/closed_principle) aus [EINFARBIG](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)). Nicht nur das, die ursprüngliche Klasse, die die Vorgänge orchestriert wurde Wachstum und hinausgeht würde, der gegen wechselt, die [einzelne Verantwortung Prinzip (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).

Andererseits, können Sie bei Verwendung von Domain-Ereignisse eine differenzierte und entkoppelte Implementierung erstellen, durch die Trennung von Aufgaben, die diesen Ansatz verwenden:

1.  Senden eines Befehls (z. B. CreateOrder) an.
2.  Erhalten Sie den Befehl Befehlshandler.
    -   Ausführen einer einzelnen gesamtverstärkung Transaktion.
    -   (Optional) Lösen Sie die Domäne-Ereignisse für Nebeneffekte (z. B. OrderStartedDomainDvent).
1.  Handle Domäne Ereignisse (innerhalb des aktuellen Prozesses) Thast werden eine offene Anzahl von möglichen Nebeneffekte in mehreren Aggregate oder Aktionen ausgeführt werden. Zum Beispiel:
    -   Vergewissern Sie sich, oder erstellen Sie Käufer "und" Payment-Methode.
    -   Erstellen Sie und senden Sie ein Ereignis verknüpften Integration mit dem Ereignisbus Zustände über Microservices oder des Triggers externe Aktionen, z. B. zum Senden einer e-Mails an den Käufer weitergegeben.
    -   Andere Nebeneffekte zu behandeln.

Wie in Abbildung 9 – 15 gezeigt, kann beginnend mit der gleichen Domäne-Ereignis behandelt werden mehrere Aktionen, die im Zusammenhang mit anderen Aggregaten in der Domäne oder zusätzliche Aktionen, die Sie über das Herstellen einer Verbindung mit Integration-Ereignissen und den-Ereignisbus Microservices ausführen müssen.

![](./media/image16.png)

**Abbildung 9 – 15**. Behandlung von mehreren Aktionen pro Domäne

Die Ereignishandler sind in der Regel in der Anwendungsschicht, da Sie für die Microservice Verhalten infrastrukturobjekte wie z. B. Repositorys oder einer Anwendung-API verwenden. In dieser Hinsicht ähneln Ereignishandler Befehlshandler, damit sowohl der Anwendungsschicht gehören. Die wichtiger besteht Unterschied darin, dass ein Befehl nur einmal verarbeitet werden sollen. Ist möglicherweise ein Ereignis Domäne verarbeitet die 0 (null) oder  *n*  erreicht, da Wenn von mehreren Empfängern oder Ereignishandler mit einem anderen Zweck für jeden Handler empfangen werden können.

Die Möglichkeit, eine open Anzahl von Handler pro Domäne Ereignis können Sie viele weitere Domänenregeln hinzufügen, ohne Auswirkungen auf den aktuellen Code. Implementieren die folgenden Geschäftsregel, die nach einem Ereignis rechts durchgeführt werden soll kann beispielsweise so einfach wie das Hinzufügen von wenigen Ereignishandler (oder auch nur eine) sein:

Wenn die Gesamtmenge von einem Kunden im Windows Store erworben haben, über eine beliebige Anzahl von Bestellungen, $6.000 überschreitet, jede neue Bestellung 10 % Preisnachlass angewendet, und benachrichtigen Sie den Kunden mit einer e-Mail-Adresse zu diesem Rabatt für zukünftige Aufträge.

## <a name="implementing-domain-events"></a>Implementierung von Ereignissen der Domäne

In c# ist ein Ereignis Domäne einfach einen Daten-Betrieb Struktur oder Klasse, wie ein DTO, anhand der Informationen im Zusammenhang zu was nur in der Domäne aufgetreten ist, wie im folgenden Beispiel gezeigt:

```csharp
public class OrderStartedDomainEvent : IAsyncNotification
{
    public int CardTypeId { get; private set; }
    public string CardNumber { get; private set; }
    public string CardSecurityNumber { get; private set; }
    public string CardHolderName { get; private set; }
    public DateTime CardExpiration { get; private set; }
    public Order Order { get; private set; }

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

Dies ist im Wesentlichen eine Klasse, die die Daten, die im Zusammenhang mit dem OrderStarted-Ereignis enthält.

Im Hinblick auf die ubiquitäre Sprache der Domäne, da ein Ereignis ist, die in der Vergangenheit aufgetreten sind muss der Klassenname des Ereignisses als Vergangenheitsform Verb, z. B. OrderStartedDomainEvent oder OrderShippedDomainEvent dargestellt werden. Das ist wie das Ereignis für die Domäne in der Reihenfolge Microservice in eShopOnContainers implementiert wird.

Wie erwähnt, ist ein wichtiges Merkmal der Ereignisse, die seit ein Ereignis ist etwas, das in der Vergangenheit aufgetreten sind, nicht geändert werden sollte. Daher muss es einer unveränderlichen Klasse sein. Sie können im vorangehenden Code angezeigt, denen die Eigenschaften schreibgeschützt sind und von außerhalb des Objekts sind. Die einzige Möglichkeit zum Aktualisieren des Objekts ist durch den Konstruktor auf, wenn Sie das Ereignisobjekt erstellen.

### <a name="raising-domain-events"></a>Auslösen von Ereignissen der Domäne

Die nächste Frage ist, wie eine Domäne-Ereignis ausgelöst wird, damit er seine zugehörige Ereignishandler erreicht wird. Sie können mehrere Ansätze verwenden.

Udi Dahan ursprünglich vorgeschlagene (z. B. in mehreren zusammenhängen, Beiträge, wie [Domain-Ereignisse – Erstellen einer 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) mit einer statischen Klasse für die Verwaltung und durch das Auslösen der Ereignisse. Dazu gehören beispielsweise eine statische Klasse mit dem Namen DomainEvents, die auslösen würde Domäne Ereignisse sofort, wenn sie aufgerufen wird, mithilfe der Syntax wie DomainEvents.Raise (Ereignis MyEvent). Jimmy Bogard geschrieben wurde, einen Blogbeitrag ([Stärkung Ihrer Domäne: Domäne Ereignisse](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) empfiehlt, einen ähnlichen Ansatz.

Allerdings sendet die Ereignisse Domänenklasse statisch ist, beim es auch Handler sofort. Dies erschwert testen und Debuggen, da die Ereignishandler mit Nebenwirkungen Logik ausgeführt werden, sofort, nachdem das Ereignis ausgelöst wird. Wenn Sie Tests debuggen sind, sollten Sie den Fokus auf und nur in den aktuellen aggregieren Klassen geschieht; Sie sollten keine plötzlich zu anderer Ereignishandler für Nebeneffekte, die im Zusammenhang mit anderen Aggregaten oder Anwendungslogik umgeleitet werden. Dies ist deshalb andere Ansätze entwickelt haben, wie im nächsten Abschnitt erläutert.

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a>Die verzögerte Ansatz für den durch das Auslösen und Auslösen von Ereignissen

Statt direkt an einen Ereignishandler für die Domäne verteilt, ein besserer Ansatz ist, die Ereignisse für die Domäne zu einer Auflistung hinzufügen und dann beim Verteilen von diesen Ereignissen Domäne *direkt vor dem* oder *rechten*  *nach dem* Commit der Transaktion (wie bei SaveChanges in EF). (Dieser Ansatz wurden durch Jimmy Bogard beschrieben, die in diesen Beitrag [eine bessere Domäne Ereignisse Muster](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)

Entscheidung, ob Sie die Domäne Ereignisse senden ist rechts vor oder nach rechts, nach dem Commit der Transaktion wichtig, da sie bestimmt, ob Sie die Nebeneffekte im Rahmen derselben Transaktion oder in unterschiedlichen Transaktionen enthalten. In letzterem Fall müssen Sie die letztliche Konsistenz über mehrere Aggregate zu verarbeiten. In diesem Thema wird im nächsten Abschnitt erläutert.

Die verzögerte Herangehensweise ist, welche eShopOnContainers verwendet. Fügen Sie zunächst die Ereignisse in Ihren Entitäten in einer Auflistung oder eine Liste der Ereignisse pro Entität geschieht. Diese Liste sollte Teil des Entitätsobjekts oder besser noch, Teil der Basisentität-Klasse handeln, wie im folgenden Beispiel gezeigt:

```csharp
public abstract class Entity
{
    private List<IAsyncNotification> _domainEvents;

    public List<IAsyncNotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(IAsyncNotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<IAsyncNotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(IAsyncNotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

Wenn Sie ein Ereignis auslösen möchten, fügen Sie einfach auf die ereignisauflistung innerhalb einer entitätsmethode, die aggregate platziert werden, wie im folgenden Code dargestellt:

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
    cardTypeId,
    cardNumber,
    cardSecurityNumber,
    cardHolderName,
    cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

Beachten Sie, dass das einzige, das die Methode AddDomainEvent auf diese Weise wird ein Ereignis zur Liste hinzugefügt wird. Noch kein Ereignis ausgelöst, und keine Ereignishandler noch aufgerufen.

Tatsächlich möchten Sie die Ereignisse weiter unten auf verteilen, wenn Sie die Transaktion an die Datenbank übergeben werden. Bei Verwendung von Entity Framework Core bedeutet, dass in der SaveChanges-Methode der EF-DbContext, wie im folgenden Code:

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<int> SaveEntitiesAsync()
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
        // event handlers) performed through the DbContext will be commited
        var result = await base.SaveChangesAsync();
    }
}
```

Mit dem folgenden Code verteilen Sie die Entität-Ereignisse, die den entsprechenden Ereignishandler.

Das Gesamtergebnis ist, dass Sie von verteilen es mit einem Ereignishandler das Auslösen eines Ereignisses Domäne entkoppelten haben (eine einfache Hinzufügen zu einer Liste im Arbeitsspeicher). Darüber hinaus je nach Art der Verteiler Sie verwenden, konnten Sie die Ereignisse synchron oder asynchron verteilen.

Bedenken Sie, dass hier transaktionale Grenzen in erhebliche stammen spielen. Wenn mehr als ein Aggregat Ihre Komponententests von Arbeit und die Transaktion ausgeführt werden kann (wie bei der Verwendung von EF-Kern- und einer relationalen Datenbank), kann dies gut funktionieren. Wenn jedoch Transaktion Aggregate erstrecken kann, z. B. Wenn Sie eine NoSQL-Datenbank, wie Azure DocumentDB, verwenden Sie zum Implementieren von zusätzlichen Schritte aus, um die Konsistenz zu erreichen. Dies ist ein weiterer Grund, warum Persistenz Unkenntnis nicht universelle ist; Es setzt das Speichersystem, das Sie verwenden.

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>Einzelne Transaktion über Aggregate im Vergleich zu eventuellen Konsistenz für Aggregate

Die Frage, ob zum Ausführen einer einzelnen Transaktions für Aggregate im Vergleich zu der vertrauenden Seite auf eventuelle Konsistenz über diese Aggregate ist ein kontroverse. Viele DDD Autoren wie Eric Evans und Vaughn Vernon der Regel, eine Transaktion Vertreter = ein Aggregat und daher für eventuelle Konsistenz über Aggregate behaupten. Beispielsweise ist in seinem Buch *Driven Design*, Eric Evans besagt, dass dies:

Jede Regel, die Aggregate umfasst wird nicht erwartet werden, dass jederzeit auf dem neuesten Stand sein. Durch die Verarbeitung von Ereignissen, Batchverarbeitung oder anderen Aktualisierungsmechanismen können andere Abhängigkeiten innerhalb einer bestimmten Zeit aufgelöst werden. (Pg. 128)

Vaughn Vernon besagt, dass in der folgenden [effektiven aggregieren Entwurf. Teil II: Treffen aggregiert arbeiten zusammen](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):

Wenn also Ausführung eines Befehls auf einem aggregieren Instanz erfordert, dass zusätzliche Geschäftsregeln auf eine oder mehrere Aggregate ausgeführt verwenden eventuellen Konsistenz \[...\] Es ist eine praktische Möglichkeit, eventuelle Konsistenz in einem Modell DDD unterstützen. Ein Aggregatmethoden veröffentlicht ein Domäne-Ereignis, die Zeit, die an einen oder mehrere asynchrone Abonnenten übermittelt wird.

Diese Begründung basiert auf Hinwendung differenzierte Transaktionen anstelle von Transaktionen umfasst viele Aggregate oder Entitäten. Die Idee dabei ist, dass im zweiten Fall die Anzahl von Datenbanksperren erhebliche in umfangreichen Anwendungen mit hoher Skalierbarkeit Anforderungen kann. Übernahme der Tatsache, die dass die hoch skalierbare Anwendungen sofortige Transaktionskonsistenz zwischen mehrere Aggregate keine müssen unterstützt das Konzept der eventuellen Konsistenz akzeptieren. Atomische Änderungen häufig nicht vom Unternehmen erforderlich sind, und es ist in jedem Fall die Zuständigkeit für die Domänenexperten bestimmen, ob bestimmte Vorgänge Atomarische Transaktionen oder nicht benötigen. Wenn ein Vorgang immer eine atomarische Transaktion zwischen mehrere Aggregate benötigt, Fragen Sie sich, ob Ihre Aggregat größer muss oder wurde nicht ordnungsgemäß entworfen.

Anderen Entwicklern und Architekten wie Jimmy Bogard sind jedoch nur eine einzelne Transaktion über mehrere Aggregate Aufteilung – jedoch nur, wenn diese zusätzlichen Aggregate mit Nebeneffekte für den gleichen ursprünglichen Befehl verknüpft sind. Zum Beispiel im [eine bessere Domäne Ereignisse Muster](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard besagt, dass dies:

Ich möchte in der Regel die Nebeneffekte einer Domäne Ereignis innerhalb der gleichen logischen Transaktion, jedoch nicht notwendigerweise in demselben Gültigkeitsbereich Auslösen des Ereignisses Domäne eintritt \[...\] Kurz bevor wir unsere Transaktion einen Commit auszuführen, verteilen wir unsere Ereignisse an ihre jeweiligen Handler.

Wenn Sie die Domäne Ereignisse rechts weiterleitet *vor* Ausführen eines Commits für die ursprüngliche Transaktion, es ist, da die Nebeneffekte des diese Ereignisse, die in derselben Transaktion eingeschlossen werden soll. Z. B. wenn EF DbContext SaveChanges-Methode ein Fehler auftritt, wird die Transaktion alle Änderungen, z. B. das Ergebnis keine Nebeneffekt-Vorgänge, die durch die verknüpfte Domäne Ereignishandler implementiert Rollback. Dies ist, da der DbContext-Lebensdauer-Bereich standardmäßig als "" definiert ist "beschränkt." Aus diesem Grund wird der DbContext-Objekt von mehreren Repository-Objekten, die innerhalb der gleichen Gültigkeitsbereich oder Objektdiagramm instanziierte gemeinsam genutzt. Dies stimmt mit dem HttpRequest-Bereich, bei der Entwicklung von Web-API oder MVC-apps.

In Wirklichkeit können beide Ansätze (einzelnen unteilbaren Transaktion und eventuellen Konsistenz) rechts sein. Es hängt von Ihrer Domäne oder Business-Anforderungen und Domänenexperten Sie zu informieren, was. Davon wie skalierbaren den Dienst benötigen (präzisere Transaktionen sind weniger Auswirkungen in Bezug auf die Datenbanksperren). Und hängt von Umfang Investition riskieren möchten in Ihrem Code vornehmen, da die letztliche Konsistenz mehr komplexen Code erfordert, um die Erkennung von möglichen Inkonsistenzen Aggregate und Ausgleich Aktionen implementiert werden muss. Müssen Sie berücksichtigen, dass wenn Sie an der ursprünglichen Aggregat- und danach Änderungen, wenn die Ereignisse weitergeleitet werden, ein Problem besteht und die Ereignishandler ihre Nebeneffekte können kein commit durchgeführt, müssen Inkonsistenzen zwischen Aggregate.

Eine Möglichkeit zum Ausgleich Aktionen ermöglichen wäre, die Domäne Ereignisse in zusätzliche Datenbanktabellen speichern, damit sie die ursprüngliche Transaktion beteiligt sein können. Danach könnten Sie einen Batchprozess verfügen, der Inkonsistenzen erkennt und Ausgleich Vorgänge ausgeführt wird, vergleichen Sie dazu die Liste von Ereignissen mit dem aktuellen Status der Aggregate. Die Ausgleich Aktionen sind Teil der ein komplexes Thema, das tiefgehende Analysen von Ihrer Seite die enthält erfordern, mit dem Geschäftsbenutzer und Domänenexperten diskutiert.

In jedem Fall können Sie die Methode auswählen, die Sie benötigen. Jedoch der ursprüngliche verzögert Ansatz – vor dem bestätigen, die Ereignisse auslösen, damit Sie eine einzelne Transaktion verwenden, ist der einfachste Ansatz bei Verwendung von EF-Kern- und einer relationalen Datenbank. Es ist einfacher zu implementieren und in vielen Geschäftssituationen gültig. Es ist auch Ansatz wird in der Reihenfolge Microservice in eShopOnContainers.

Aber wie Sie tatsächlich dispatch-Ereignisse an ihre jeweiligen Ereignishandler? Was ist die \_Vermittler-Objekt, das Sie im vorherigen Beispiel sehen? Die muss nur mit den Methoden und Elemente, die Sie verwenden können, um zwischen Ereignissen und den Ereignishandler zuzuordnen.

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>Die Domäne Ereignisverteiler: Zuordnen von Ereignissen zu Ereignishandlern

Sobald Sie verteilen oder die Ereignisse veröffentlichen können sind, benötigen Sie eine Art des Artefakt, das das Ereignis veröffentlicht werden sollen, sodass alle verknüpften Handler sie erhalten und Nebeneffekte Prozess auf der Grundlage dieses Ereignisses.

Ein besteht Ansatz darin real Messagingsystem oder sogar eine-Ereignisbus, meist basierend auf einer Servicebus im Gegensatz zu den Ereignissen im Arbeitsspeicher. Im ersten Fall wird real messaging wäre jedoch Ausgangsstruktur für Verarbeitungsereignisse Domäne, da Sie nur die Ereignisse innerhalb des gleichen Prozesses verarbeiten müssen (d. h. innerhalb der gleichen Ebene der Domäne und Anwendung).

Eine andere Möglichkeit, die für mehrere Ereignishandler zugeordnet ist, mit Typen Registrierung in einen IoC-Container, damit Sie dynamisch, wo Sie die Ereignisse per Rückschluss ableiten können. Das heißt, müssen Sie wissen, was Ereignishandler müssen, um ein bestimmtes Ereignis abzurufen. Abbildung 9 und 16 zeigt einen vereinfachten Ansatz ein, an.

![](./media/image17.png)

**Abbildung 9 und 16**. Domäne Ereignisverteiler mit steuerungsumkehrcontainer (IoC)

Sie können alle zugrunde liegenden Funktionen und Elementen, die diesen Ansatz selbst implementieren erstellen. Allerdings können Sie auch verfügbare Bibliotheken wie verwenden [MediatR](https://github.com/jbogard/MediatR), die im Hintergrund verwendet Ihrer IoT-Containers. Sie können daher direkt die vordefinierten Schnittstellen und die Vermittler Objektmethoden veröffentlichen/Dispatch verwenden.

Im Code müssen Sie zunächst die Handler Ereignistypen im IoC-Container zu registrieren, wie im folgenden Beispiel gezeigt:

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement
        // IAsyncNotificationHandler<>) in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(
            typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
            .GetTypeInfo().Assembly)
            .Where(t => t.IsClosedTypeOf(typeof(IAsyncNotificationHandler<>)))
            .AsImplementedInterfaces();
        // Other registrations ...
    }
}
```

Der Code zunächst identifiziert die Assembly, die die Ereignishandler für die Domäne enthält, suchen Sie die Assembly, die alle der Handler enthält (mit typeof(ValidateOrAddBuyerAggregateWhenXxxx), aber Sie hätten jeder andere Ereignishandler zum Suchen der Assembly). Da alle Ereignishandler die IAsyncNotificationHandler-Schnittstelle implementieren, den Code dann einfach Suchvorgänge für diese Datentypen und registriert den Ereignishandler.

### <a name="how-to-subscribe-to-domain-events"></a>Gewusst wie: Abonnieren von Ereignissen der Domäne

Bei Verwendung von MediatR muss jeder Ereignishandler einen Ereignistyp, der für den generischen Parameter der Schnittstelle IAsyncNotificationHandler bereitgestellt wird verwenden, wie Sie in den folgenden Code sehen können:

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

Basierend auf der Beziehung zwischen Ereignis und Ereignishandler, der das Abonnement betrachtet werden kann, das Artefakt MediatR ermitteln die Ereignishandler für jedes Ereignis und aller diese Ereignishandler ausgelöst.

### <a name="how-to-handle-domain-events"></a>Behandeln von Ereignissen Domäne

Abschließend implementiert der Ereignishandler in der Regel Ebene Anwendungscode, der Infrastruktur-Repositorys zum Abrufen der erforderlichen zusätzlichen Aggregate und auszuführende Nebeneffekte Domänenlogik verwendet. Der folgende Code zeigt ein Beispiel.

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
    : IAsyncNotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;
    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // Parameter validations
        //...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ?
            orderStartedEvent.CardTypeId : 1;
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
        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) :
        _buyerRepository.Add(buyer);
        await _buyerRepository.UnitOfWork.SaveEntitiesAsync();
        // Logging code using buyerUpdated info, etc.
    }
}
```

Diese Ereignishandlercode Ebene Anwendungscode gilt da Infrastruktur-Repositorys, die verwendet wird, wie der Infrastruktur Persistenzebene im nächsten Abschnitt erläutert. Ereignishandler können auch andere Infrastrukturkomponenten verwenden.

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>Domain-Ereignisse können integrationsereignisse außerhalb der Grenzen Microservice veröffentlicht werden generiert.

Schließlich ist wichtig zu erwähnen, dass Sie manchmal sollten Ereignisse über mehrere Microservices weitergegeben. Ein Ereignis Integration angesehen wird, und es über eine Ereignisbus aus jeder Ereignishandler bestimmte Domäne veröffentlicht werden konnte.

## <a name="conclusions-on-domain-events"></a>Schlussfolgerungen auf Domain-Ereignisse 

Wie erwähnt, verwenden Sie Domain-Ereignisse, um explizit Nebeneffekte der Änderungen in Ihrer Domäne zu implementieren. Um DDD Terminologie verwenden zu können, verwenden Sie Domäne Ereignisse Nebeneffekte über eine oder mehrere Aggregate explizit implementiert. Verwenden Sie darüber hinaus und für eine bessere Skalierbarkeit und weniger Auswirkungen auf die Datenbanksperren, die letztliche Konsistenz zwischen Aggregate innerhalb der gleichen Domäne.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Greg Young. Was ist ein Ereignis Domäne? ** 
     [ *http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)

-   **Jan Stenberg. Ereignisse der Domäne und eventuelle Konsistenz**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)

-   **Jimmy Bogard. Eine bessere Domäne Ereignisse Muster**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)

-   **Vaughn Vernon. Effektive aggregieren Entwurf Teil II: Ausführenden Aggregate arbeiten zusammen**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_Artikel/Vernon\_2011\_ 2. pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

-   **Jimmy Bogard. Stärkung Ihrer Domäne: Domäne Ereignisse**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*

-   **Tony Truong. Domäne Ereignisse Muster Beispiel**
    [*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)

-   **Udi Dahan. Vorgehensweise: Erstellen Sie vollständig gekapselt Domänenmodelle**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)

-   **Udi Dahan. Erstellen einer Domäne Ereignisse – 2**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)

-   **Udi Dahan. Domain-Ereignisse – Rettung**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)

-   **Jan Kronquist. Nicht veröffentlichen von Ereignissen der Domäne, zurückgeben! ** 
     [ *https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)

-   **Cesar de la Torre. Domäne-Ereignisse im Vergleich zu DDD und Microservices Architekturen-Integrationsereignisse**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)


>[!div class="step-by-step"]
[Vorherigen] (Client-Side-validation.md) [weiter] (Infrastruktur-Persistenz-Ebene – design.md)
