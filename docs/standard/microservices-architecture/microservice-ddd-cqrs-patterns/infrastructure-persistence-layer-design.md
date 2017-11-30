---
title: Entwerfen der Infrastruktur Persistenzebene
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entwerfen der Infrastruktur Persistenzebene"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ce0f1d608eed909a7707f3c580afc5253f3eef06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-infrastructure-persistence-layer"></a>Entwerfen der Infrastruktur Persistenzebene

Dauerhaftigkeitskomponenten Daten bereitstellen, Zugriff auf die Daten innerhalb der Grenzen des ein Microservice (d. h. ein Microservice-Datenbank) gehostet wird. Sie enthalten die tatsächliche Implementierung von Komponenten wie Repositorys und [Unit of Work](http://martinfowler.com/eaaCatalog/unitOfWork.html) -Klassen, wie benutzerdefinierte EF DBContexts.

## <a name="the-repository-pattern"></a>Das Repositorymuster

Repositorys werden Klassen oder Komponenten, die die Logik erforderlich, um den Zugriff auf Datenquellen zu kapseln. Diese Zentralisierung allgemeine Data Access-Funktionalität, bietet eine bessere Verwaltbarkeit und die Entkopplung der Infrastruktur oder eine Technologie, die Zugriff auf die Datenbanken aus der Domäne der Ebene verwendet. Wenn Sie ein ORM wie Entity Framework verwenden, wird der Code, der implementiert werden muss, Dank LINQ und starke Typisierung vereinfacht. Dadurch können Sie den Fokus auf die Persistenzlogik Daten anstatt auf Daten zugreifen, Basisaufgaben.

Das Repositorymuster ist eine gut dokumentierten Möglichkeit des Arbeitens mit einer Datenquelle. Im Buch [Muster der Anwendungsarchitektur Enterprise](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Smell beschreibt ein Repository wie folgt:

Ein Repository führt die Tasks der Vermittler zwischen der Domäne dienstmodellebene und datenzuordnung, auf ähnliche Weise auf einen Satz von Domänenobjekten im Arbeitsspeicher fungiert. -Clientobjekte deklarativ Abfragen erstellen und an den Repositorys für Antworten senden. Im Prinzip kapselt ein Repository einen Satz von Objekten, die in der Datenbank und die Vorgänge, die ausgeführt werden können, auf diesen zu ermöglichen, die näher an der Persistenzebene wird gespeichert. -Repositorys, die unterstützt außerdem des Zwecks trennen, klar und in eine Richtung, die Abhängigkeit zwischen der Domäne für die Arbeit und die Verteilung der Daten oder Zuordnung.

### <a name="define-one-repository-per-aggregate"></a>Definieren Sie ein Repository pro Aggregat

Für jedes Stammelement aggregate oder aggregate sollten Sie eine Repository-Klasse erstellen. In einem Microservice anhand von Mustern Domain driven Design sollte der einzige Kanal, werden, zum Aktualisieren der Datenbank verwendet soll, den Repositorys. Dies ist, da sie eine direkte Beziehung mit der aggregierten Stamm aufweisen, die des Aggregats Invarianten und Transaktionskonsistenz gesteuert. Es ist angemessen, Fragen Sie die Datenbank über andere Kanäle (wie nach einem CQRS-Ansatz), da es sich bei Abfragen der Status der Datenbank nicht geändert werden. Allerdings Bereich transaktional – Updates – muss immer durch den Repositorys und die aggregate Stämme gesteuert werden.

Im Wesentlichen können mit einem Repository Daten im Arbeitsspeicher zu füllen, die aus der Datenbank in Form von Domänenentitäten stammen. Sobald die Entitäten im Arbeitsspeicher befinden, können sie geändert und dann in der Datenbank über Transaktionen übernommen werden.

Wie oben bereits erwähnt, wenn Sie das architektonische CQS/CQRS-Muster verwenden, werden die anfängliche Abfragen von clientseitigen Abfragen Out Domänenmodell ausgeführt durch einfache SQL-Anweisungen, die mit dapper, durch ausgeführt werden. Dieser Ansatz ist viel mehr als Repositorys flexibel, da Sie können Abfragen und verknüpfen alle Tabellen müssen und diese Abfragen werden nicht von Regeln aus der Aggregate eingeschränkt. Diese Daten werden für die Präsentation Ebene oder Client-app wechseln

Wenn der Benutzer Änderungen vornimmt, stammen die Daten aktualisiert werden aus der Client-app oder eine Präsentation-Ebene für die Anwendungsebene (z. B. eine Web-API-Dienst). Wenn Sie einen Befehl (mit Daten) im Befehlshandler erhalten, verwenden Sie Repositorys zum Abrufen der Daten, die Sie aus der Datenbank aktualisieren möchten. Sie es im Arbeitsspeicher mit den Informationen, die mit den Befehlen übergeben aktualisieren, und klicken Sie dann hinzufügen oder aktualisieren Sie die Daten (Domänenentitäten) in der Datenbank über eine Transaktion.

Wir müssen betonen erneut, die nur ein Repository sollte für jedes aggregieren Stammelement definiert werden, wie in Abbildung 9-17 gezeigt. Um das Ziel der Stamm-aggregate, die Transaktionskonsistenz zwischen allen Objekten innerhalb des Aggregats aufrechterhalten zu erreichen, sollten Sie niemals ein Repository für jede Tabelle in der Datenbank erstellen.

![](./media/image18.png)

**Abbildung 9-17**. Die Beziehung zwischen Repositorys, Aggregate und Datenbanktabellen

### <a name="enforcing-one-aggregate-root-per-repository"></a>Erzwingen eine aggregierte Stamm pro repository

Es kann sinnvoll sein, die Ihrem Repository Entwurf so implementieren, dass sie die Regel führt dazu, dass nur aggregate Stämme Repositorys verfügen sollen sein. Sie können einen generische oder eine Basis-Repository-Typ erstellen, der den Typ von Entitäten einschränkt, mit dem es um sicherzustellen, dass sie die IAggregateRoot markerschnittstelle aufweisen.

Daher implementiert jede Repository-Klasse, die auf der Infrastrukturebene implementiert einen eigenen Vertrag oder einer Schnittstelle, wie im folgenden Code gezeigt:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

Jede Schnittstelle spezifischen Repository implementiert die generische IRepository-Schnittstelle:

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

Jedoch eine bessere Möglichkeit, den Code die Konvention zu erzwingen, dass jedes Repository zu einer einzelnen gesamtverstärkung verknüpft werden soll wäre, einen generischen Repository-Typ zu implementieren, sodass er explizit ist, dass Sie ein Repository für eine bestimmte Aggregat entwickeln verwenden. Dies kann problemlos durch die Implementierung dieses Generikum in der Basisschnittstelle IRepository wie im folgenden Code erfolgen:

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>Das Repositorymuster erleichtert es, die Anwendungslogik zu testen.

Das Repositorymuster bietet die Möglichkeit, leicht Testen Ihrer Anwendung mit Komponententests abgedeckt. Denken Sie daran, dass Komponententests nur getestet, Ihr Code, der nicht-Infrastruktur, sodass die Repository-Abstraktionen erreichen dieses Ziels erleichtern.

Wie in einem Abschnitt weiter oben erwähnt, wird empfohlen, dass Sie definieren platziert die Repository-Schnittstellen in die Domäne der Ebene, damit die Anwendungsschicht (z. B. Ihre Web-API-Microservice) nicht direkt auf die Infrastrukturebene abhängt, in denen Ihnen implementiert die tatsächliche Repositoryklassen. Indem Sie auf diese Weise und mithilfe der Abhängigkeitsinjektion in die Ihre Web-API-Controller, können Sie simulierten Repositorys implementieren, die Pseudodaten anstelle von Daten aus der Datenbank zurückgegeben. Entkoppelte Ansatz ermöglicht Ihnen das Erstellen und Ausführen von Komponententests, die können nur die Logik Ihrer Anwendung testen, ohne Verbindung mit der Datenbank.

Verbindungen mit Datenbanken können fehlschlagen, vor allem Hunderte von Tests für eine Datenbank ausgeführt wird und fehlerhafte zwei Gründen. Zuerst, dauert es sehr lange aufgrund der großen Anzahl von Tests. Zweitens können die Datenbankdatensätze ändern und Auswirkungen auf die Ergebnisse der Tests, sodass sie möglicherweise nicht konsistent. Tests für die Datenbank ist keine Komponententests erneut durch, sondern eine Integration testen. Sie sollten viele Komponententests schnell ausgeführt haben, aber weniger Integrationstests für die Datenbanken.

Im Hinblick auf die Abgrenzung von Problemen bei Komponententests verarbeitet Ihre Logik Domänenentitäten im Arbeitsspeicher. Es wird davon ausgegangen, dass die Repository-Klasse, die die übermittelt hat. Sobald Ihre Logik die Domänenentitäten ändert, wird angenommen, dass es sich bei die Repository-Klasse werden ordnungsgemäß gespeichert werden. Wichtig dabei ist zum Erstellen von Komponententests für Ihre Domänenmodell und ihrer Domänenlogik. Aggregate sind die wichtigsten Konsistenz Grenzen in DDD.

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>Der Unterschied zwischen dem Repository und das ältere Datenzugriff (DAL) Klasse Muster

Ein Datenzugriffsobjekt führt direkt Datenvorgänge Zugriff und persistenten Speicher. Ein Repository markiert die Daten für die Vorgänge, die Sie in den Speicher einer Einheit von Arbeitsobjekt (wie in der EF bei Verwendung von ' DbContext '), aber diese Updates durchführen möchten nicht sofort ausgeführt werden.

Eine Arbeitseinheit wird bezeichnet als einzelne Transaktion, die umfasst mehrere INSERT-, Update- und delete-Operationen. Einfach ausgedrückt bedeutet dies, dass alle INSERT-, Update- und Löschtransaktionen für eine bestimmte Benutzeraktion (z. B. die Registrierung auf einer Website), in einer einzelnen Transaktion verarbeitet werden. Dies ist jedoch effizienter, anstatt mehrere Datenbanktransaktionen geschwätzigeren so zu behandeln.

Diese mehrere persistenzvorgänge werden weiter unten in einer einzigen Aktion ausgeführt werden, wenn Ihr Code von der Anwendungsebene von Befehlen. Die Entscheidung zum Anwenden der in-Memory-Änderungen auf den tatsächlichen Datenbankspeicher in der Regel hängt die [Unit of Work Muster](http://martinfowler.com/eaaCatalog/unitOfWork.html). In der EF wird das Muster Unit of Work als DBContext implementiert.

In vielen Fällen kann dieses Muster oder eine Möglichkeit zum Anwenden von Vorgängen für den Speicher Anwendungsleistung erhöhen, und verringern die Gefahr von Inkonsistenzen. Außerdem verringert es Transaktion blockiert sind in den Datenbanktabellen, da die vorgesehene Vorgänge als Teil einer einzigen Transaktion ein Commit ausgeführt werden. Dies ist jedoch effizienter, im Vergleich zu viele isolierte Vorgänge für die Datenbank ausführen. Aus diesem Grund werden können die Ausführung für die Datenbank zu optimieren, indem Sie mehrere Updateaktionen innerhalb derselben Transaktion erfolgt, im Gegensatz zu oft kleiner und separate Transaktion gruppieren die ausgewählten ORM.

### <a name="repositories-should-not-be-mandatory"></a>Repositorys darf nicht obligatorisch sein.

Benutzerdefinierte Repositorys eignen sich für die oben genannten Gründe, und das ist der Ansatz für die Sortierung Microservice in eShopOnContainers. Es ist jedoch kein wichtige Muster, um in einen DDD Entwurf implementieren oder sogar im allgemeinen-Entwicklung in .NET.

Jimmy Bogard, bei der Bereitstellung von direkten Feedback zu diesem Handbuch said z. B. Folgendes:

Dies wird wahrscheinlich mein größten Feedback haben. Ich bin wirklich keines Lüfters des Repositorys, die hauptsächlich, da sie wichtige Details des zugrunde liegenden Dauerhaftigkeit ausblenden. Der warum ich MediatR für Befehle zu finden. Ich kann die volle Leistung von der Persistenzebene verwenden und alle dieser Domänenverhalten in meinem aggregieren Stämme push. Ich möchte nicht in der Regel Meine Repositorys modellieren – ich muss weiterhin haben, die die Integration mit reale Sache Test. CQRS passiert vorgesehen, dass wir eine Notwendigkeit einer Repositorys wirklich mehr hatten.

Wir finden Repositorys nützlich, aber wir bestätigen Sie, dass sie nicht für Ihre DDD, bei der Datenerfassung entscheidender Bedeutung sind, die die aggregierten Muster und umfangreiche Domänenmodell sind. Daher verwenden Sie das Repositorymuster, davon, wie Sie sehen passen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

##### <a name="the-repository-pattern"></a>Das Repositorymuster

-   **Edward Hieatt und Rob me. Repositorymuster. ** 
     [ *http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)

-   **Das Repositorymuster**
    [*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)

-   **Repositorymuster: Eine Daten persistenzabstraktion**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)

-   **Eric Evans. Domain Driven Design: Tackling, Complexity in the Heart of Software wird.** (Book; enthält eine Erläuterung der des Repositorymusters) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

##### <a name="unit-of-work-pattern"></a>Einheit des Musters mit Aufgaben

-   **Martin Fowler. Die Einheit der Arbeit Muster. ** 
     [ *http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)

<!-- -->

-   **Implementieren das Repository und die Einheit der Arbeit Muster in einer ASP.NET MVC-Anwendung**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)


>[!div class="step-by-step"]
[Vorherigen] (Domäne-Ereignisse-Design-implementation.md) [weiter] (Infrastructure-persistence-layer-implemenation-entity-framework-core.md)
