---
title: Entwerfen von Validierungen auf der Domänenmodellebene
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Entwerfen von Validierungen auf der Domänenmodellebene
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ce3cb0c79cbd492224ce1d4ecb25cd02062f11cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578949"
---
# <a name="designing-validations-in-the-domain-model-layer"></a>Entwerfen von Validierungen auf der Domänenmodellebene

In DDD können Validierungsregeln als Invarianten betrachtet werden. Die wichtigste Verantwortung eines Aggregats besteht darin, Invarianten für Zustandsänderungen für alle Entitäten innerhalb dieses Aggregats zu erzwingen.

Domänenentitäten sollten immer gültige Entitäten sein. Es gibt eine bestimmte Anzahl an Invarianten für ein Objekt, die immer zutreffen sollten. Beispielsweise muss ein Bestellelementobjekt immer über eine Menge mit einer positiven ganzen Zahl plus Artikelnamen und Artikelpreis verfügen. Aus diesem Grund liegt die Erzwingung von Invarianten in der Verantwortung der Domänenentitäten (insbesondere des Aggregatstamms) und ein Entitätsobjekt sollte nicht existieren können, wenn es nicht gültig ist. Invariante Regeln werden einfach als Verträge angegeben, und Ausnahmen oder Benachrichtigungen werden ausgelöst, wenn sie verletzt werden.

Die Überlegung dahinter ist, dass viele Fehler auftreten, weil sich Objekte in einem Zustand befinden, in dem sie nie sein sollten. Im Folgenden finden Sie eine übersichtliche Erläuterung von Greg Young in einer [Onlinediskussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

Nehmen wir an, dass wir SendUserCreationEmailService haben, der ein UserProfile akzeptiert... Wie können wir innerhalb dieses Diensts begründen, dass Name nicht NULL ist? Überprüfen wir ihn erneut? Oder wahrscheinlicher... Sie kümmern sich einfach nicht darum und „hoffen auf das Beste“ – Sie hoffen, dass jemand die Validierung durchführt, bevor es an Sie gesendet wird. Natürlich sollten wir bei der Verwendung von TDD einen der ersten Tests schreiben, bei dem ein Fehler ausgelöst wird, wenn ich einen Kunden mit einem Namen mit einem Wert von NULL schicke. Aber sobald wir diese Art von Tests immer wieder schreiben, erkennen wir: „Moment mal, wenn Namen nie NULL sein könnten, hätten wir nicht alle diese Tests“

## <a name="implementing-validations-in-the-domain-model-layer"></a>Implementieren von Validierungen auf der Domänenmodellebene

Validierungen werden in der Regel in Domänenentitätskonstruktoren oder in Methoden implementiert, die die Entität aktualisieren können. Es gibt mehrere Möglichkeiten zum Implementieren von Validierungen, z.B. das Validieren von Daten und Auslösen von Ausnahmen, wenn die Validierung fehlschlägt. Es gibt auch erweiterte Muster wie die Verwendung des Spezifikationsmusters für Validierungen und die Benachrichtigungsmuster zum Zurückgeben einer Auflistung von Fehlern, anstatt eine Ausnahme für jede auftretende Validierung zurückzugeben.

### <a name="validating-conditions-and-throwing-exceptions"></a>Validieren von Bedingungen und Auslösen von Ausnahmen

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
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

Wenn der Wert des Zustands ungültig ist, wurden die erste Adresszeile und der Ort bereits geändert. Somit wird die Adresse möglicherweise ungültig.

Ein ähnlicher Ansatz kann im Entitätskonstruktor verwendet werden, wodurch eine Ausnahme ausgelöst wird, um sicherzustellen, dass die Entität gültig ist, sobald sie erstellt wird.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>Verwenden von Validierungsattributen im Modell anhand von Datenanmerkungen

Ein anderer Ansatz ist die Verwendung von Validierungsattributen anhand von Datenanmerkungen. Mithilfe von Validierungsattributen können Sie die Modellvalidierung konfigurieren. Dies ist mit der Validierung von Feldern in Datenbanktabellen zu vergleichen. Dies beinhaltet Einschränkungen wie das Zuweisen von Datentypen oder erforderlichen Feldern. Andere Arten der Validierung umfassen die Anwendung von Mustern auf Daten, um Geschäftsregeln zu erzwingen – z.B. das Angeben einer Kreditkartenummer, einer Telefonnummer oder einer E-Mail-Adresse. Validierungsattribute erleichtern das Erzwingen von Anforderungen.

Wie jedoch im folgenden Code gezeigt wird, greift dieser Ansatz in einem DDD-Modell möglicherweise zu sehr ein, da er eine Abhängigkeit auf ModelState.IsValid von Microsoft.AspNetCore.Mvc.ModelState abruft, die Sie von Ihren MVC-Controllern aufrufen müssen. Die Modellvalidierung wird vor jeder ausgelösten Controlleraktion ausgelöst. Die Controllermethode ist dafür verantwortlich, das Ergebnis des Aufrufs von ModelState.IsValid zu untersuchen und darauf angemessen zu reagieren. Die Entscheidung zur Verwendung hängt davon ab, wie eng das Modell mit dieser Infrastruktur gekoppelt werden soll.

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

Allerdings bleibt das Domänenmodell aus DDD-Sicht am besten schlank, mit der Verwendung von Ausnahmen in den Verhaltensmethoden Ihrer Entität, oder durch die Implementierung der Spezifikations- und Benachrichtigungsmuster, um Validierungsregeln zu erzwingen. Validierungsframeworks wie Datenanmerkungen in ASP.NET Core oder andere Validierungsframeworks wie FluentValidation erfordern die Auslösung des Anwendungsframeworks. Beispielsweise müssen Sie beim Aufrufen der Methode ModelState.IsValid in Datenanmerkungen ASP.NET-Controller aufrufen.

Es kann sich als sinnvoll erweisen, Datenanmerkungen auf Anwendungsebene in ViewModel-Klassen (statt Domänenentitäten) zu verwenden, die Eingaben zur Modellvalidierung in der Benutzeroberflächenebene akzeptieren. Dies sollte jedoch nicht unter Ausschluss der Validierung innerhalb des Domänenmodells ausgeführt werden.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Validieren von Entitäten durch Implementieren der Spezifikations- und Benachrichtigungsmuster

Es gibt einen komplexeren Ansatz zum Implementieren von Validierungen im Domänenmodell. Hierbei wird das Spezifikationsmuster in Verbindung mit dem Benachrichtigungsmuster implementiert, wie in einigen der unten aufgeführten zusätzlichen Ressourcen beschrieben wird.

Es ist erwähnenswert, dass Sie auch nur eines dieser Muster verwenden können – z.B. das manuelle Validieren mit Steueranweisungen und das Verwenden des Benachrichtigungsmusters zum Stapeln und Zurückgeben einer Liste von Validierungsfehlern.

### <a name="using-deferred-validation-in-the-domain"></a>Verwenden der verzögerten Validierung in der Domäne

Es gibt verschiedene Ansätze für den Umgang mit verzögerten Validierungen in der Domäne. In seinem Buch [Implementing Domain-Driven Design (Implementieren von domänengesteuertem Design)](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) erläutert Vaughn Vernon dies im Abschnitt zur Validierung.

### <a name="two-step-validation"></a>Zweistufige Validierung

Ziehen Sie auch die zweistufige Validierung in Betracht. Verwenden Sie Feldebenenvalidierung für Ihre Datentransferobjekte (DTOs) und Domänenebenenvalidierung innerhalb Ihrer Entitäten. Dazu wird ein Ergebnisobjekt anstelle von Ausnahmen zurückgegeben, um den Umgang mit den Validierungsfehlern zu erleichtern.

Wenn Sie z.B. die Feldvalidierung mit Datenanmerkungen verwenden, duplizieren Sie die Validierungsdefinition nicht. Die Ausführung kann jedoch im Fall von DTOs serverseitig und clientseitig sein (beispielsweise Befehle und ViewModels).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Rachel Appel. Einführung in die Modellvalidierung im ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. Adding validation (Hinzufügen der Überprüfung)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. Ersetzen des Auslösens von Ausnahmen durch Benachrichtigungen in Validierungen**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **Spezifikation und Benachrichtigungsmuster**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **Lev Gorodinski. Validierung in Domain-Driven-Design (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin Jack. Überprüfung des Domänenmodells**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard. Validierung in einer DDD-Welt**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[Zurück] (enumeration-classes-over-enum-types.md) [Weiter] (client-side-validation.md)
