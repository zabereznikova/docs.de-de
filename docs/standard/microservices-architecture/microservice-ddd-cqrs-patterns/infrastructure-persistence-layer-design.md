---
title: Entwerfen der Persistenzebene der Infrastruktur
description: Erfahren Sie, wie Sie die Persistenzschicht der Infrastruktur entwerfen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/28/2017
ms.openlocfilehash: a0fcaead363e41f0dd02ed1e2ddfc90afb8d0c57
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404472"
---
# <a name="designing-the-infrastructure-persistence-layer"></a>Entwerfen der Persistenzebene der Infrastruktur

Komponenten der Datenpersistenz bieten Zugriff auf die Daten, die innerhalb der Grenzen eines Microservices gehostet werden (d.h. in der Datenbank eines Microservices). Sie enthalten die tatsächliche Implementierung von Komponenten wie Repositorys und [Arbeitseinheits](https://martinfowler.com/eaaCatalog/unitOfWork.html)-Klassen wie benutzerdefinierte Entity Framework-<xref:Microsoft.EntityFrameworkCore.DbContext>-Objekte.

## <a name="the-repository-pattern"></a>Das Repositorymuster

Repositorys sind Klassen oder Komponenten, welche die für den Zugriff auf Datenquellen erforderliche Logik einschließen. Sie zentralisieren allgemeine Funktionen für den Datenzugriff und bieten dabei eine bessere Verwaltbarkeit und Entkopplung der Infrastruktur oder Technologie, die für den Zugriff auf Datenbanken über die Domänenmodellebene verwendet wird. Wenn Sie eine ORM (object-relational mapping) wie Entity Framework verwenden, wird der zu implementierende Code dank LINQ und starker Typisierung vereinfacht. Dadurch können Sie sich auf die Logik der Datenpersistenz konzentrieren und müssen sich nicht mit der Grundstruktur des Datenzugriffs befassen.

Das Repositorymuster stellt eine Methode mit umfassender Dokumentation für die Arbeit mit einer Datenquelle dar. Im Buch [Patterns of Enterprise Application Architecture (Muster der Architektur von Unternehmensanwendungen)](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/) beschreibt Martin Fowler ein Repository wie folgt:

> Ein Repository führt die Tasks eines Zwischenspeichers zwischen den Domänenmodellebenen und der Datenzuordnung aus und agiert dabei ähnlich wie eine Reihe von Domänenobjekten im Arbeitsspeicher. Clientobjekte erstellen deklarativ Abfragen und senden diese an die Repositorys, um Antworten darauf zu bekommen. Im Prinzip schließt ein Repository eine Reihe von Objekten, die in der Datenbank gespeichert sind, sowie Vorgänge ein, die darin ausgeführt werden können, und bietet damit eine Möglichkeit, die näher an der Persistenzebene liegt. Zudem unterstützen Repositorys den Zweck der eindeutigen und unidirektionalen Trennung der Abhängigkeit zwischen der Arbeitsdomäne und der Datenzuordnung.

### <a name="define-one-repository-per-aggregate"></a>Definieren eines Repositorys pro Aggregat

Sie sollten für jedes Aggregat bzw. für jeden Aggregatstamm eine Repositoryklasse erstellen. In einem auf domänengesteuerten Entwurfsmustern (DDD) basierenden Microservice sollten Sie für das Update der Datenbank als einzigen Kanal die Repositorys verwenden. Grund dafür ist, dass sie in einer 1:1-Beziehung zum Aggregatstamm stehen, wodurch die Invarianten und die Transaktionskonsistenz des Aggregats gesteuert werden. Die Datenbank kann auch über andere Kanäle abgefragt werden (nach einem CQRS-Ansatz), da sich der Status der Datenbank bei Abfragen nicht ändert. Der Transaktionsbereich (d.h. die Updates) muss jedoch immer von den Repositorys und den Aggregatstämmen gesteuert werden.

Im Wesentlichen können Sie in einem Repository den Arbeitsspeicher mit Daten auffüllen, die aus der Datenbank in Form von Domänenentitäten stammen. Sobald sich die Entitäten im Arbeitsspeicher befinden, können sie geändert und über Transaktionen wieder in der Datenbank gespeichert werden.

Wie bereits erwähnt wurde, werden bei Verwendung des CQS/CQRS-Architekturmusters die ersten Abfragen mit Abfragen aus dem Domänenmodell über einfache SQL-Anweisungen mit Dapper ausgeführt. Dieser Ansatz ist flexibler als Repositorys, da Sie alle erforderlichen Tabelle abfragen und verknüpfen können und diese Abfragen nicht durch Regeln aus den Aggregaten eingeschränkt werden. Diese Daten sind dann auf der Darstellungsschicht oder in der Client-App enthalten.

Wenn der Benutzer Änderungen vornimmt, werden die zu aktualisierenden Daten von der Client-App oder der Darstellungsschicht auf die Anwendungsschicht (z.B. ein Web-API-Dienst) verschoben. Wenn Sie in einem Befehlshandler einen Befehl mit Daten empfangen, rufen Sie die Daten, die Sie aus der Datenbank aktualisieren möchten, über Repositorys ab. Sie aktualisieren die Daten im Arbeitsspeicher mit den Informationen, die mit den Befehlen übergeben wurden, und können die Daten (Domänenentitäten) anschließend in der Datenbank über eine Transaktion hinzufügen oder aktualisieren.

Denken Sie daran, dass für jeden Aggregatstamm wie in Abbildung 9-17 dargestellt nur ein Repository definiert werden sollte. Damit das Ziel des Aggregatstamms erreicht wird und die Transaktionskonsistenz zwischen allen Objekten im Aggregat erhalten bleibt, sollten Sie niemals für jede Tabelle in der Datenbank ein Repository erstellen.

![](./media/image18.png)

**Abbildung 9-17**. Die Beziehung zwischen Repositorys, Aggregaten und Datenbanktabellen

### <a name="enforcing-one-aggregate-root-per-repository"></a>Erzwingen eines Aggregatstamms pro Repository

Es kann sinnvoll sein, Ihren Repositoryentwurf so zu implementieren, dass die Regel erzwungen wird, nach der nur Aggregatstämme über Repositorys verfügen sollten. Sie können einen generischen oder grundlegenden Repositorytyp erstellen, der den Entitätstyp einschränkt, mit dem er arbeitet, um sicherzustellen, dass die Entitäten die `IAggregateRoot`-Markerschnittstelle aufweisen.

Daher implementiert jede auf der Infrastrukturebene implementierte Repositoryklasse wie im folgenden Code dargestellt ihren eigenen Vertrag bzw. ihre eigene Schnittstelle:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
      // ...
    }
}
```

Jede spezifische Repositoryschnittstelle implementiert die generische IRepository-Schnittstelle:

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

Allerdings besteht im Implementieren eines generischen Repositorytyps eine bessere Möglichkeit, damit der Code die Konvention erzwingt, dass jedes Repository mit einem einzelnen Aggregat verknüpft ist. Auf diese Weise ist explizit festgelegt, dass Sie ein Repository für ein bestimmtes Aggregat verwenden. Dies kann problemlos wie im folgenden Code dargestellt durch Implementierung einer generischen `IRepository`-Basisschnittstelle geschehen:

```csharp
public interface IRepository<T> where T : IAggregateRoot
{
    //....
}
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>Das Repositorymuster erleichtert das Testen Ihrer Anwendungslogik

Das Repositorymuster bietet die Möglichkeit, Ihre Anwendung ohne großen Aufwand mithilfe von Komponententests zu testen. Beachten Sie, dass bei Komponententests nur Ihr Code getestet wird, nicht die Infrastruktur, damit dieses Ziel durch die Repositoryabstraktionen leichter erreicht werden kann.

Wie in einem Abschnitt weiter oben erwähnt wurde, wird empfohlen, die Repositoryschnittstellen auf der Domänenmodellebene zu definieren und anzuordnen, damit die Anwendungsschicht, z.B. Ihr Web-API-Microservice, nicht direkt von der Infrastrukturebene abhängt, auf der Sie die tatsächlichen Repositoryklassen implementiert haben. Auf diese Weise und durch Verwendung der Abhängigkeitsinjektion in den Controllern Ihrer Web-API können Sie Pseudorepositorys implementieren, die anstelle von Daten aus der Datenbank falsche Daten zurückgeben. Mit diesem entkoppelten Ansatz können Sie Komponententests erstellen und ausführen, in denen die Logik Ihrer Anwendung getestet werden kann, ohne dass eine Verbindung zur Datenbank erforderlich ist.

Verbindungen zu Datenbanken können fehlschlagen, und aus zwei Gründen ist von der Durchführung von Hunderten von Tests in einer Datenbank abzuraten. Zunächst einmal kann dies aufgrund der zahlreichen Tests viel Zeit in Anspruch nehmen. Zudem könnten sich die Datensätze in der Datenbank ändern. Dies könnte Auswirkungen auf die Ergebnisse Ihrer Tests haben, sodass diese möglicherweise nicht konsistent sind. Das Testen der Datenbank ist kein Komponententest, sondern ein Integrationstest. Für die Datenbanken sollten viele schnelle Komponententests, aber wenige Integrationstest durchgeführt werden.

Im Hinblick auf die Abgrenzung von Problemen bei Komponententests verwaltet Ihre Logik Domänenentitäten im Arbeitsspeicher. Es wird davon ausgegangen, dass die Repositoryklasse diese Entitäten übermittelt hat. Sobald Ihre Logik die Domänenentitäten ändert, wird davon ausgegangen, dass diese ordnungsgemäß in der Repositoryklasse gespeichert werden. Wichtig dabei ist, dass Komponententests für Ihr Domänenmodell und die zugehörige Domänenlogik erstellt werden. Aggregatstämme stellen die hauptsächlichen Konsistenzgrenzen in DDD dar.

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>Der Unterschied zwischen dem Repositorymuster und dem älteren Muster der Datenzugriffsklasse (DAL-Klasse)

Ein Datenzugriffsobjekt führt direkt Datenzugriffs- und Persistenzvorgänge für den Speicher aus. Ein Repository markiert die Daten mit den Vorgängen, die Sie im Speicher eines Arbeitseinheitsobjekts (wie in EF bei der Verwendung der <xref:Microsoft.EntityFrameworkCore.DbContext>-Klasse) durchführen möchten. Diese Updates werden jedoch nicht sofort durchgeführt.

Eine Arbeitseinheit wird als einzelne Transaktion bezeichnet, die mehrere INSERT-, UPDATE- oder DELETE-Vorgänge umfasst. Einfach ausgedrückt bedeutet dies, dass alle INSERT-, UPDATE- und DELETE-Transaktionen für eine bestimmte Benutzeraktion, z.B. die Registrierung auf einer Website, in einer einzelnen Transaktion verarbeitet werden. Dies ist effizienter als mehrere Datenbanktransaktionen auf umständlichere Weise zu verarbeiten.

Diese Persistenzvorgänge werden zu einem späteren Zeitpunkt in einer einzelnen Aktion durchgeführt, wenn Ihr Code aus der Anwendungsebene dies anordnet. Die Entscheidung, ob die im Speicher vorgenommenen Änderungen am tatsächlichen Datenbankspeicher angewendet werden sollen, basiert in der Regel auf dem [Arbeitseinheitsmuster](https://martinfowler.com/eaaCatalog/unitOfWork.html). In EF wird das Arbeitseinheitsmuster als <xref:Microsoft.EntityFrameworkCore.DbContext> implementiert.

In vielen Fällen kann dieses Muster bzw. diese Methode zum Anwenden von Vorgängen im Speicher die Anwendungsleistung erhöhen und die Gefahr von Inkonsistenzen verringern. Zudem können Transaktionsblockierungen in den Datenbanktabellen verringert werden, da alle vorgesehenen Vorgänge im Rahmen einer Transaktion zugesichert werden. Im Vergleich zur Ausführung vieler isolierter Vorgänge in der Datenbank ist dies der effizientere Weg. Daher kann die ausgewählte ORM die Ausführung für die Datenbank optimieren, indem statt der Ausführung vieler kleiner und separater Transaktionen mehrere Updateaktionen innerhalb derselben Transaktion gruppiert werden.

### <a name="repositories-shouldnt-be-mandatory"></a>Repositorys sollten nicht obligatorisch sein.

Benutzerdefinierte Repositorys sind aus den oben genannten Gründen hilfreich, und dies ist der Ansatz für den Microservice „Ordering“ (Bestellung) in eShopOnContainers. Es ist jedoch kein essentielles Muster, das in einem domänengesteuerten Entwurf oder in der allgemeinen .NET-Entwicklung implementiert werden muss.

Jimmy Bogard hat beispielsweise Folgendes geäußert, als er direktes Feedback zu diesem Leitfaden gegeben hat:

> Dies wird wahrscheinlich mein ausführlichstes Feedback. Ich bin wirklich kein Fan von Repositorys, hauptsächlich deshalb, weil sie die wichtigen Details des zugrunde liegenden Persistenzmechanismus ausblenden. Deswegen vertraue ich auch bei Befehlen auf MediatR. Ich kann die volle Leistung der Persistenzebene nutzen und das gesamte Domänenverhalten per Push in meine Aggregatstämme übertragen. Normalerweise möchte ich keine Pseudorepositorys haben. Ich muss diese Integrationstests weiterhin am Original durchführen können. Dass wir uns nach CQRS gerichtet haben, bedeutet, dass wir keine Repositorys mehr benötigt haben.

Repositorys sind zwar nützlich, aber sie sind für Ihren domänengesteuerten Entwurf nicht genauso wichtig wie Aggregatmuster und ein umfassendes Domänenmodell. Daher können Sie selbst entscheiden, ob Sie das Repositorymuster verwenden möchten oder nicht.

## <a name="the-specification-pattern"></a>Das Spezifikationsmuster

Das Spezifikationsmuster (dessen vollständiger Name Abfragespezifikationsmuster lautet) ist ein DDD-Muster, in dem Sie die Definition einer Abfrage mit optionaler Sortier- und Auslagerungslogik ablegen können.

Das Spezifikationsmuster definiert eine Abfrage in einem Objekt. Sie können eine `PagedProduct`-Spezifikation erstellen, die die erforderlichen Eingabeparameter akzeptiert (z.B. `pageNumber`, `pageSize`, `filter` usw.), wenn Sie beispielsweise eine ausgelagerte Abfrage einschließen möchten, die nach bestimmten Produkten sucht. Anschließend würde eine `ISpecification`-Schnittstelle innerhalb einer Repositorymethode (üblicherweise eine List()-Überladung) akzeptiert und die erwartete Abfrage anhand dieser Spezifikation ausgeführt werden.

Die Verwendung dieses Ansatzes hat mehrere Vorteile:

- Die Spezifikation hat einen Namen (im Gegensatz zu einer Reihe von LINQ-Ausdrücken), den Sie bei Diskussionen verwenden können.

- Für die Spezifikation kann ein Komponententest ausgeführt werden, um sicherzustellen, dass sie korrekt ist. Sie kann auch ohne großen Aufwand wiederverwendet werden, wenn Sie ähnliche Verhaltensweisen benötigen, beispielsweise in einer MVC View-Aktion, einer Web API-Aktion sowie in verschiedenen Diensten.

- Eine Spezifikation kann auch verwendet werden, um die Form der zurückzugebenen Daten zu beschreiben, damit in Abfragen nur die erforderlichen Daten zurückgegeben werden. Dadurch entfällt die Notwendigkeit des verzögerten Ladens in Webanwendungen, wovon in der Regel ohnehin abgeraten wird. Zudem wird verhindert, dass Repositoryimplementierungen mit diesen Details überladen werden.

Der folgende Code aus [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb) dient als Beispiel einer generischen Spezifikationsschnittstelle.

```csharp
// https://github.com/dotnet-architecture/eShopOnWeb
public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

In den nächsten Abschnitten wird erläutert, wie das Spezifikationsmuster mit EF Core 2.x implementiert und über eine beliebige Repositoryklasse verwendet wird.

> [!IMPORTANT]
> Bei diesem Spezifikationsmuster handelt es sich um ein altes Muster, das auf viele verschiedene Arten implementiert werden kann, z.B. wie in den folgenden zusätzlichen Ressourcen. Als Muster bzw. Anregung ist es hilfreich, ältere Ansätze zu kennen. Meiden Sie jedoch ältere Implementierungen, die keinen modernen Sprachfunktionen wie Linq und Ausdrücke nutzen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

### <a name="the-repository-pattern"></a>Das Repositorymuster

- **Das Repositorymuster**
  [https://deviq.com/repository-pattern/](https://deviq.com/repository-pattern/)

- **Edward Hieatt und Rob Mee. Repository pattern (Repositorymuster).**
  [_https://martinfowler.com/eaaCatalog/repository.html_](https://martinfowler.com/eaaCatalog/repository.html)

- **The Repository Pattern (Das Repositorymuster)**
  [_https://docs.microsoft.com/previous-versions/msp-n-p/ff649690(v=pandp.10)_](https://docs.microsoft.com/previous-versions/msp-n-p/ff649690(v=pandp.10))

- **Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software (Domänengesteuertes Design: Umgang mit Komplexität im Kern einer Software).** (Buch; enthält eine Diskussion des Repositorymusters) [_https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/_](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="unit-of-work-pattern"></a>Arbeitseinheitsmuster

- **Martin Fowler. Unit of Work pattern (Arbeitseinheitsmuster).**
  [_https://martinfowler.com/eaaCatalog/unitOfWork.html_](https://martinfowler.com/eaaCatalog/unitOfWork.html)

- **Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application (Implementieren der Muster „Repository“ und „Arbeitseinheit“ in eine ASP.NET MVC-Anwendung)**
  [_https://docs.microsoft.com/aspnet/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application_](https://docs.microsoft.com/aspnet/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)

### <a name="the-specification-pattern"></a>Das Spezifikationsmuster

- **The Specification pattern (Das Spezifikationsmuster)**
  [_https://deviq.com/specification-pattern/_](https://deviq.com/specification-pattern/)

- **Evans, Eric (2004). Domain-Driven Design. Addison-Wesley. S. 224.**

- **Specifications (Spezifikationen). Martin Fowler**
  [_https://www.martinfowler.com/apsupp/spec.pdf/_](https://www.martinfowler.com/apsupp/spec.pdf)

>[!div class="step-by-step"]
[Zurück](domain-events-design-implementation.md)
[Weiter](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
