---
title: Entwerfen von Validierungen auf der Domänenmodellebene
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Wichtige Konzepte für Validierungen von Domänenmodellen
ms.date: 10/08/2018
ms.openlocfilehash: 94df2d6441581fbbae479da2524d6ffce2037d68
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100911"
---
# <a name="design-validations-in-the-domain-model-layer"></a>Entwerfen von Validierungen auf der Domänenmodellebene

In DDD können Validierungsregeln als Invarianten betrachtet werden. Die wichtigste Verantwortung eines Aggregats besteht darin, Invarianten für Zustandsänderungen für alle Entitäten innerhalb dieses Aggregats zu erzwingen.

Domänenentitäten sollten immer gültige Entitäten sein. Es gibt eine bestimmte Anzahl an Invarianten für ein Objekt, die immer zutreffen sollten. Beispielsweise muss ein Bestellelementobjekt immer über eine Menge mit einer positiven ganzen Zahl plus Artikelnamen und Artikelpreis verfügen. Aus diesem Grund liegt die Erzwingung von Invarianten in der Verantwortung der Domänenentitäten (insbesondere des Aggregatstamms) und ein Entitätsobjekt sollte nicht existieren können, wenn es nicht gültig ist. Invariante Regeln werden einfach als Verträge angegeben, und Ausnahmen oder Benachrichtigungen werden ausgelöst, wenn sie verletzt werden.

Die Überlegung dahinter ist, dass viele Fehler auftreten, weil sich Objekte in einem Zustand befinden, in dem sie nie sein sollten. Im Folgenden finden Sie eine übersichtliche Erläuterung von Greg Young in einer [Onlinediskussion](https://jeffreypalermo.com/2009/05/the-fallacy-of-the-always-valid-entity/):

Nehmen wir an, dass wir SendUserCreationEmailService haben, der ein UserProfile akzeptiert... Wie können wir innerhalb dieses Diensts begründen, dass Name nicht NULL ist? Überprüfen wir ihn erneut? Oder wahrscheinlicher... Sie kümmern sich einfach nicht darum und „hoffen auf das Beste“ – Sie hoffen, dass jemand die Validierung durchführt, bevor es an Sie gesendet wird. Natürlich sollten wir bei der Verwendung von TDD einen der ersten Tests schreiben, bei dem ein Fehler ausgelöst wird, wenn ich einen Kunden mit einem Namen mit einem Wert von NULL schicke. Aber sobald wir diese Art von Tests immer wieder schreiben, erkennen wir: „Moment mal, wenn Namen nie NULL sein könnten, hätten wir nicht alle diese Tests“

## <a name="implement-validations-in-the-domain-model-layer"></a>Implementieren von Validierungen auf der Domänenmodellebene

Validierungen werden in der Regel in Domänenentitätskonstruktoren oder in Methoden implementiert, die die Entität aktualisieren können. Es gibt mehrere Möglichkeiten zum Implementieren von Validierungen, z.B. das Validieren von Daten und Auslösen von Ausnahmen, wenn die Validierung fehlschlägt. Es gibt auch erweiterte Muster wie die Verwendung des Spezifikationsmusters für Validierungen und die Benachrichtigungsmuster zum Zurückgeben einer Auflistung von Fehlern, anstatt eine Ausnahme für jede auftretende Validierung zurückzugeben.

### <a name="validate-conditions-and-throw-exceptions"></a>Validieren von Bedingungen und Auslösen von Ausnahmen

Das folgende Codebeispiel zeigt die einfachste Vorgehensweise zur Validierung in einer Domänenentität durch Auslösen einer Ausnahme. In der Verweistabelle am Ende dieses Abschnitts sehen Sie Links zu fortgeschritteneren Implementierungen, die auf den zuvor besprochenen Mustern basieren.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Ein besseres Beispiel würde zeigen, dass man sicherstellen muss, dass der interne Zustand sich nicht geändert hat oder dass alle Mutationen einer Methode aufgetreten sind. Die folgende Implementierung würde z.B. das Objekt in einem ungültigen Zustand belassen:

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shippingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

Wenn der Wert des Zustands ungültig ist, wurden die erste Adresszeile und der Ort bereits geändert. Somit wird die Adresse möglicherweise ungültig.

Ein ähnlicher Ansatz kann im Entitätskonstruktor verwendet werden, wodurch eine Ausnahme ausgelöst wird, um sicherzustellen, dass die Entität gültig ist, sobald sie erstellt wird.

### <a name="use-validation-attributes-in-the-model-based-on-data-annotations"></a>Verwenden von Validierungsattributen im Modell anhand von Datenanmerkungen

Datenanmerkungen können ähnlich wie die Required- oder MaxLength-Attribute zum Konfigurieren von EF Core-Datenbankfeld-Eigenschaften verwendet werden, wie im Abschnitt [Tabellenzuordnung](infrastructure-persistence-layer-implementation-entity-framework-core.md#table-mapping) detailliert erläutert. Allerdings [können sie nicht mehr für die Entitätsvalidierung EF Core verwendet werden](https://github.com/dotnet/efcore/issues/3680) (Gleiches gilt für die <xref:System.ComponentModel.DataAnnotations.IValidatableObject.Validate%2A?displayProperty=nameWithType>-Methode), wie dies seit EF 4.x in .NET Framework der Fall war.

Datenanmerkungen und die <xref:System.ComponentModel.DataAnnotations.IValidatableObject>-Schnittstelle können weiterhin für die Modellvalidierung während der Modellbindung verwendet werden, bevor die Controlleraktionen aufgerufen werden. Dies ist jedoch für ein ViewModel- oder DTO-Modell vorgesehen. Dabei handelt es sich um einen MVC- oder API-Aspekt, der nicht im Domänenmodell behandelt wird.

Nachdem die Unterschiede in den Konzepten nun klar sind, können Sie Datenanmerkungen und `IValidatableObject` in der Entitätsklasse weiterhin für die Validierung verwenden, wenn Ihre Aktionen einen Objektparameter der Entitätsklasse empfangen. Dies wird aber nicht empfohlen. In diesem Fall erfolgt die Validierung bei der Modellbindung, vor dem Aufrufen der Aktion, und Sie können das Ergebnis in der ModelState.IsValid-Eigenschaft des Controllers überprüfen. Aber auch hier gilt: Die Validierung erfolgt im Controller, d. h., nicht bevor das Entitätsobjekt in DbContext gespeichert wird, wie es seit EF 4.x der Fall ist.

Sie können die benutzerdefinierte Validierung weiterhin mithilfe von Datenanmerkungen und der `IValidatableObject.Validate`-Methode in die Entitätsklasse implementieren, indem Sie die SaveChanges-Methode von DbContext überschreiben.

Eine Beispielimplementierung für die Validierung von `IValidatableObject`-Elementen finden Sie in [diesem Kommentar auf GitHub](https://github.com/dotnet/efcore/issues/3680#issuecomment-155502539). Dieses Beispiel führt keine attributbasierten Validierungen durch. Diese lassen sich jedoch durch Reflexion in der gleichen Überschreibung implementieren.

Allerdings bleibt das Domänenmodell aus DDD-Sicht am besten schlank, mit der Verwendung von Ausnahmen in den Verhaltensmethoden Ihrer Entität, oder durch die Implementierung der Spezifikations- und Benachrichtigungsmuster, um Validierungsregeln zu erzwingen.

Es kann sich als sinnvoll erweisen, Datenanmerkungen auf Anwendungsebene in ViewModel-Klassen (statt Domänenentitäten) zu verwenden, die Eingaben zur Modellvalidierung in der Benutzeroberflächenebene akzeptieren. Dies sollte jedoch nicht unter Ausschluss der Validierung innerhalb des Domänenmodells ausgeführt werden.

### <a name="validate-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Validieren von Entitäten durch Implementieren der Spezifikations- und Benachrichtigungsmuster

Es gibt einen komplexeren Ansatz zum Implementieren von Validierungen im Domänenmodell. Hierbei wird das Spezifikationsmuster in Verbindung mit dem Benachrichtigungsmuster implementiert, wie in einigen der unten aufgeführten zusätzlichen Ressourcen beschrieben wird.

Es ist erwähnenswert, dass Sie auch nur eines dieser Muster verwenden können – z.B. das manuelle Validieren mit Steueranweisungen und das Verwenden des Benachrichtigungsmusters zum Stapeln und Zurückgeben einer Liste von Validierungsfehlern.

### <a name="use-deferred-validation-in-the-domain"></a>Verwenden der verzögerten Validierung in der Domäne

Es gibt verschiedene Ansätze für den Umgang mit verzögerten Validierungen in der Domäne. In seinem Buch [Implementing Domain-Driven Design (Implementieren von domänengesteuertem Design)](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) erläutert Vaughn Vernon dies im Abschnitt zur Validierung.

### <a name="two-step-validation"></a>Zweistufige Validierung

Ziehen Sie auch die zweistufige Validierung in Betracht. Verwenden Sie Feldebenenvalidierung für Ihre Datentransferobjekte (DTOs) und Domänenebenenvalidierung innerhalb Ihrer Entitäten. Dazu wird ein Ergebnisobjekt anstelle von Ausnahmen zurückgegeben, um den Umgang mit den Validierungsfehlern zu erleichtern.

Wenn Sie z.B. die Feldvalidierung mit Datenanmerkungen verwenden, duplizieren Sie die Validierungsdefinition nicht. Die Ausführung kann jedoch im Fall von DTOs serverseitig und clientseitig sein (beispielsweise Befehle und ViewModels).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Rachel Appel. Introduction to model validation in ASP.NET Core MVC** \ (Einführung in die Modellvalidierung im ASP.NET Core MVC)\
  <https://docs.microsoft.com/aspnet/core/mvc/models/validation>

- **Rick Anderson. Adding validation** \ (Hinzufügen der Validierung)\
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

- **Martin Fowler. Replacing Throwing Exceptions with Notification in Validations** \ (Ersetzen des Auslösens von Ausnahmen durch Benachrichtigungen in Validierungen)\
  <https://martinfowler.com/articles/replaceThrowWithNotification.html>

- **Specification and Notification Patterns** \ (Spezifikations- und Benachrichtigungsmuster)\
  <https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns>

- **Lev Gorodinski. Validation in Domain-Driven Design (DDD)**  \ (Validierung in Domain-Driven-Design [DDD])\
  <http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/>

- **Colin Jack. Domain Model Validation** \ (Validierung des Domänenmodells)\
  <https://colinjack.blogspot.com/2008/03/domain-model-validation.html>

- **Jimmy Bogard. Validation in a DDD world** \ (Validierung in einer DDD-Welt)\
  <https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/>

> [!div class="step-by-step"]
> [Zurück](enumeration-classes-over-enum-types.md)
> [Weiter](client-side-validation.md)
