---
title: "Entwerfen von Überprüfungen in der Domäne der Ebene"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entwerfen von Überprüfungen in der Domäne der Ebene"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a>Entwerfen von Überprüfungen in der Domäne der Ebene

In DDD können Validierungsregeln als invarianten betrachtet werden. Die wichtigsten Verantwortung eines Aggregats besteht darin, invarianten für Zustandsänderungen für alle Entitäten innerhalb dieses Aggregat zu erzwingen.

Domänenentitäten sollte immer gültige Entitäten sein. Es gibt eine bestimmte Anzahl von Invarianten für ein Objekt, das immer "true" werden soll. Beispielsweise verfügt ein Order-Element-Objekt immer eine Menge ist, die muss eine positive ganze Zahl plus einen Artikelnamen und Preis. Aus diesem Grund invarianten Erzwingung liegt in der Verantwortung der Domänenentitäten (insbesondere von aggregierten Stamm) und ein Entitätsobjekt sollten nicht in der Lage, ohne gültigen vorhanden sein. Invariante Regeln werden einfach als Verträge angegeben wird, und Ausnahmen oder Benachrichtigungen ausgelöst werden, wenn sie verletzt werden.

Die Überlegung hinter dieser ist, dass viele Fehler auftreten, weil Objekte in einem Zustand befinden, in denen sie nie in Waren sollten. Im folgenden finden Sie eine gute Erläuterung von Greg Young in ein [online Diskussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

Wir schlagen vor, dass wir jetzt haben eine SendUserCreationEmailService an, die akzeptiert UserProfile... wie wir innerhalb des betreffenden Diensts rationalisieren können, dass der Name nicht null ist? Überprüfen wir es erneut zu? Oder wahrscheinlicher... einfach nicht darum kümmern überprüfen und "hoffen optimale" – Sie hoffen, dass jemand behindert, zu überprüfen, bevor sie an Sie gesendet. Natürlich verwenden der testgesteuerten Entwicklung des ersten Tests, die wir also, wenn ich, dass er einen Fehler auszulösen, sollte ein Kunde mit einem null-Namen senden geschrieben werden soll. Beachten dabei aber sobald wir diese Arten von Tests immer wieder schreiben starten wir... "Warten Sie, wenn wir Namen werden Sie niemals zulässig null wir wäre nicht verfügen über alle diese Tests"

## <a name="implementing-validations-in-the-domain-model-layer"></a>Implementieren von Überprüfungen in der Domäne der Ebene

Überprüfungen werden in der Regel implementiert, in der Domäne Entität Konstruktoren oder Methoden, mit die die Entität aktualisiert werden können. Es gibt mehrere Möglichkeiten zum Implementieren von Überprüfungen, z. B. überprüft, ob Daten und das Auslösen von Ausnahmen, wenn die Validierung fehlschlägt. Es gibt auch erweiterte Muster wie die Verwendung des Musters Spezifikation für Validierungen und die Benachrichtigung Muster zum Zurückgeben einer Auflistung von Fehlern, anstatt eine Ausnahme für jede Überprüfungen, während es eintritt.

### <a name="validating-conditions-and-throwing-exceptions"></a>Überprüfen von Bedingungen und Auslösen von Ausnahmen

Das folgende Codebeispiel zeigt die einfachste Vorgehensweise bei der Überprüfung in eine Entität "Domain" durch Auslösen einer Ausnahme. In der Tabelle "Verweise" am Ende dieses Abschnitts können Sie sehen, Links zu weiter fortgeschrittene Implementierungen, die auf der Grundlage der Muster, die wir zuvor besprochen haben können.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Ein Beispiel für eine bessere veranschaulichen, würde die Notwendigkeit, stellen Sie sicher, dass entweder der interne Zustand nicht geändert hat oder dass alle Mutationen für eine Methode aufgetreten sind. Die folgende Implementierung würde z. B. das Objekt in einem ungültigen Zustand lassen:

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

Wenn der Wert des Status ungültig ist, wurden die erste Adresszeile und den Ort bereits geändert. Die möglicherweise die Adresse ungültig wird.

Ein ähnlicher Ansatz kann verwendet werden, in der Entität Konstruktor durch das Auslösen einer Ausnahme, um sicherzustellen, dass die Entität gültig ist, sobald es erstellt wird.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>Verwenden Validierungsattribute in das Modell anhand von datenanmerkungen

Ein anderer Ansatz ist die Verwendung von Validierungsattributen basierend auf datenanmerkungen. Validierungsattribute bieten eine Möglichkeit modellvalidierung konfigurieren, die Überprüfung auf Felder in Datenbanktabellen vom Konzept her ähnlich ist. Dazu gehören Einschränkungen wie z. B. das Zuweisen von Datentypen oder Pflichtfelder. Andere Typen von Validierung umfasst die Anwendung von Mustern auf Daten zum Erzwingen von Geschäftsregeln, z. B. eine Kreditkartennummer, Telefonnummer oder e-Mail-Adresse. Validierungsattribute erleichtern es, um Anforderungen zu erzwingen.

Jedoch wie im folgenden Code gezeigt wird, diesen Ansatz zu aufwendig, in einem Modell DDD möglicherweise, da es eine Abhängigkeit auf ModelState.IsValid von Microsoft.AspNetCore.Mvc.ModelState, führt die vom MVC-Controllers heraus aufgerufen werden muss. Die modellüberprüfung wird vor jeder Controlleraktion aufgerufen wurde, und es obliegt dem Controllermethode überprüfen das Ergebnis des aufrufenden ModelState.IsValid und entsprechend reagieren. Die Entscheidung zur Verwendung abhängig, wie eng gekoppelt, das Modell, das mit dieser Infrastruktur werden soll.

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

Allerdings ist aus Sicht des eine DDD Domänenmodell am besten lean mit der Verwendung von Ausnahmen in der Entität verhaltensmethoden oder durch die Implementierung der Spezifikationen und zur Benachrichtigung Muster, um Überprüfungsregeln durchzusetzen aufbewahrt. Überprüfung-Frameworks wie datenanmerkungen in ASP.NET Core oder andere Validierung Frameworks wie FluentValidation führen eine Anforderung für das Anwendungsframework aufrufen. Beispielsweise fallen beim Aufrufen der Methode ModelState.IsValid in datenanmerkungen ASP.NET Controller aufrufen.

Es kann sinnvoll, datenanmerkungen auf Anwendungsebene in ViewModel-Klassen (statt Domänenentitäten) verwenden, die Eingaben zur modellvalidierung in der Benutzeroberflächenebene zu akzeptieren. Dies sollte jedoch nicht an den Ausschluss der Überprüfung innerhalb des Domänenmodells ausgeführt werden.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Überprüfen von Entitäten durch Implementieren der Spezifikation und das Muster für die Benachrichtigung

Schließlich ist ein komplexeren Ansatz zum Implementieren von Überprüfungen im Domänenmodell durch die Implementierung des Musters Spezifikation in Verbindung mit dem Muster Benachrichtigung, wie einige der unten aufgeführten zusätzlichen Ressourcen beschrieben.

Es ist erwähnenswert, dass Sie nur eine dieser Muster auch verwenden können – z. B. mit Steueranweisungen manuell überprüfen, aber verwenden Sie das Muster für die Benachrichtigung zum Stapeln und Zurückgeben einer Liste der Validierungsfehler.

### <a name="using-deferred-validation-in-the-domain"></a>Verwenden die verzögerte Validierung in der Domäne

Es gibt verschiedene Ansätze für den Umgang mit verzögerten Überprüfungen in der Domäne. In seinem Buch [Implementing Domain-Driven Entwurf](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon erläutert diese im Abschnitt zur Validierung.

### <a name="two-step-validation"></a>Überprüfung in zwei Schritten

Berücksichtigen Sie auch die Überprüfung in zwei Schritten. Verwenden Sie Überprüfungsfehler auf, auf Ihre Daten übertragen Befehlsobjekte (DTOs) und Domänenebene Validierung innerhalb der Entitäten. Dazu wird durch Zurückgeben der Ergebnisobjekt stattdessen Ausnahmen um für den Umgang mit den Validierungsfehler zu erleichtern.

Feldvalidierung mit datenanmerkungen verwenden, z. B. duplizieren Sie nicht die Überprüfungdefinition. Die Ausführung kann jedoch serverseitige und clientseitige im Fall von DTOs sein (Befehle und ViewModels, z. B.).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Rachel Appel. Einführung in die modellvalidierung in ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. Hinzufügen einer Validierung**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. Auslösen von Ausnahmen mit der Benachrichtigung im Überprüfungen ersetzen**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **Spezifikation und Benachrichtigung Muster**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **Lev Gorodinski. Die Validierung in Domain Driven Design (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin an. Domäne Modellvalidierung**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard. Überprüfung in einer Welt DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[Vorherigen] (Enumeration-Klassen-Over-Enum-types.md) [weiter] (Client-Side-validation.md)
