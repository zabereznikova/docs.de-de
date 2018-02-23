---
title: "Entwerfen von Validierungen auf der Domänenmodellebene"
description: ".NET Microservicesarchitektur für .NET-Containeranwendungen | Entwerfen von Validierungen auf der Domänenmodellebene"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e7a111ce20039f8c87d3c3d63efdeaf38a4e1e96
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="32f5b-104">Entwerfen von Validierungen auf der Domänenmodellebene</span><span class="sxs-lookup"><span data-stu-id="32f5b-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="32f5b-105">In DDD können Validierungsregeln als Invarianten betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="32f5b-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="32f5b-106">Die wichtigste Verantwortung eines Aggregats besteht darin, Invarianten für Zustandsänderungen für alle Entitäten innerhalb dieses Aggregats zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="32f5b-107">Domänenentitäten sollten immer gültige Entitäten sein.</span><span class="sxs-lookup"><span data-stu-id="32f5b-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="32f5b-108">Es gibt eine bestimmte Anzahl an Invarianten für ein Objekt, die immer zutreffen sollten.</span><span class="sxs-lookup"><span data-stu-id="32f5b-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="32f5b-109">Beispielsweise muss ein Bestellelementobjekt immer über eine Menge mit einer positiven ganzen Zahl plus Artikelnamen und Artikelpreis verfügen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="32f5b-110">Aus diesem Grund liegt die Erzwingung von Invarianten in der Verantwortung der Domänenentitäten (insbesondere des Aggregatstamms) und ein Entitätsobjekt sollte nicht existieren können, wenn es nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="32f5b-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="32f5b-111">Invariante Regeln werden einfach als Verträge angegeben, und Ausnahmen oder Benachrichtigungen werden ausgelöst, wenn sie verletzt werden.</span><span class="sxs-lookup"><span data-stu-id="32f5b-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="32f5b-112">Die Überlegung dahinter ist, dass viele Fehler auftreten, weil sich Objekte in einem Zustand befinden, in dem sie nie sein sollten.</span><span class="sxs-lookup"><span data-stu-id="32f5b-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="32f5b-113">Im Folgenden finden Sie eine übersichtliche Erläuterung von Greg Young in einer [Onlinediskussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="32f5b-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="32f5b-114">Nehmen wir an, dass wir SendUserCreationEmailService haben, der ein UserProfile akzeptiert... Wie können wir innerhalb dieses Diensts begründen, dass Name nicht NULL ist?</span><span class="sxs-lookup"><span data-stu-id="32f5b-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="32f5b-115">Überprüfen wir ihn erneut?</span><span class="sxs-lookup"><span data-stu-id="32f5b-115">Do we check it again?</span></span> <span data-ttu-id="32f5b-116">Oder wahrscheinlicher... Sie kümmern sich einfach nicht darum und „hoffen auf das Beste“ – Sie hoffen, dass jemand die Validierung durchführt, bevor es an Sie gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="32f5b-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="32f5b-117">Natürlich sollten wir bei der Verwendung von TDD einen der ersten Tests schreiben, bei dem ein Fehler ausgelöst wird, wenn ich einen Kunden mit einem Namen mit einem Wert von NULL schicke.</span><span class="sxs-lookup"><span data-stu-id="32f5b-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="32f5b-118">Aber sobald wir diese Art von Tests immer wieder schreiben, erkennen wir: „Moment mal, wenn Namen nie NULL sein könnten, hätten wir nicht alle diese Tests“</span><span class="sxs-lookup"><span data-stu-id="32f5b-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="32f5b-119">Implementieren von Validierungen auf der Domänenmodellebene</span><span class="sxs-lookup"><span data-stu-id="32f5b-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="32f5b-120">Validierungen werden in der Regel in Domänenentitätskonstruktoren oder in Methoden implementiert, die die Entität aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="32f5b-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="32f5b-121">Es gibt mehrere Möglichkeiten zum Implementieren von Validierungen, z.B. das Validieren von Daten und Auslösen von Ausnahmen, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="32f5b-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="32f5b-122">Es gibt auch erweiterte Muster wie die Verwendung des Spezifikationsmusters für Validierungen und die Benachrichtigungsmuster zum Zurückgeben einer Auflistung von Fehlern, anstatt eine Ausnahme für jede auftretende Validierung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="32f5b-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="32f5b-123">Validieren von Bedingungen und Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="32f5b-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="32f5b-124">Das folgende Codebeispiel zeigt die einfachste Vorgehensweise zur Validierung in einer Domänenentität durch Auslösen einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="32f5b-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="32f5b-125">In der Verweistabelle am Ende dieses Abschnitts sehen Sie Links zu fortgeschritteneren Implementierungen, die auf den zuvor besprochenen Mustern basieren.</span><span class="sxs-lookup"><span data-stu-id="32f5b-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="32f5b-126">Ein besseres Beispiel würde zeigen, dass man sicherstellen muss, dass der interne Zustand sich nicht geändert hat oder dass alle Mutationen einer Methode aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="32f5b-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="32f5b-127">Die folgende Implementierung würde z.B. das Objekt in einem ungültigen Zustand belassen:</span><span class="sxs-lookup"><span data-stu-id="32f5b-127">For example, the following implementation would leave the object in an invalid state:</span></span>

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

<span data-ttu-id="32f5b-128">Wenn der Wert des Zustands ungültig ist, wurden die erste Adresszeile und der Ort bereits geändert.</span><span class="sxs-lookup"><span data-stu-id="32f5b-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="32f5b-129">Somit wird die Adresse möglicherweise ungültig.</span><span class="sxs-lookup"><span data-stu-id="32f5b-129">That might make the address invalid.</span></span>

<span data-ttu-id="32f5b-130">Ein ähnlicher Ansatz kann im Entitätskonstruktor verwendet werden, wodurch eine Ausnahme ausgelöst wird, um sicherzustellen, dass die Entität gültig ist, sobald sie erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="32f5b-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="32f5b-131">Verwenden von Validierungsattributen im Modell anhand von Datenanmerkungen</span><span class="sxs-lookup"><span data-stu-id="32f5b-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="32f5b-132">Ein anderer Ansatz ist die Verwendung von Validierungsattributen anhand von Datenanmerkungen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="32f5b-133">Mithilfe von Validierungsattributen können Sie die Modellvalidierung konfigurieren. Dies ist mit der Validierung von Feldern in Datenbanktabellen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="32f5b-134">Dies beinhaltet Einschränkungen wie das Zuweisen von Datentypen oder erforderlichen Feldern.</span><span class="sxs-lookup"><span data-stu-id="32f5b-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="32f5b-135">Andere Arten der Validierung umfassen die Anwendung von Mustern auf Daten, um Geschäftsregeln zu erzwingen – z.B. das Angeben einer Kreditkartenummer, einer Telefonnummer oder einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="32f5b-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="32f5b-136">Validierungsattribute erleichtern das Erzwingen von Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="32f5b-137">Wie jedoch im folgenden Code gezeigt wird, greift dieser Ansatz in einem DDD-Modell möglicherweise zu sehr ein, da er eine Abhängigkeit auf ModelState.IsValid von Microsoft.AspNetCore.Mvc.ModelState abruft, die Sie von Ihren MVC-Controllern aufrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="32f5b-138">Die Modellvalidierung wird vor jeder ausgelösten Controlleraktion ausgelöst. Die Controllermethode ist dafür verantwortlich, das Ergebnis des Aufrufs von ModelState.IsValid zu untersuchen und darauf angemessen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="32f5b-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="32f5b-139">Die Entscheidung zur Verwendung hängt davon ab, wie eng das Modell mit dieser Infrastruktur gekoppelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="32f5b-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

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

<span data-ttu-id="32f5b-140">Allerdings bleibt das Domänenmodell aus DDD-Sicht am besten schlank, mit der Verwendung von Ausnahmen in den Verhaltensmethoden Ihrer Entität, oder durch die Implementierung der Spezifikations- und Benachrichtigungsmuster, um Validierungsregeln zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="32f5b-141">Validierungsframeworks wie Datenanmerkungen in ASP.NET Core oder andere Validierungsframeworks wie FluentValidation erfordern die Auslösung des Anwendungsframeworks.</span><span class="sxs-lookup"><span data-stu-id="32f5b-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="32f5b-142">Beispielsweise müssen Sie beim Aufrufen der Methode ModelState.IsValid in Datenanmerkungen ASP.NET-Controller aufrufen.</span><span class="sxs-lookup"><span data-stu-id="32f5b-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="32f5b-143">Es kann sich als sinnvoll erweisen, Datenanmerkungen auf Anwendungsebene in ViewModel-Klassen (statt Domänenentitäten) zu verwenden, die Eingaben zur Modellvalidierung in der Benutzeroberflächenebene akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="32f5b-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="32f5b-144">Dies sollte jedoch nicht unter Ausschluss der Validierung innerhalb des Domänenmodells ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="32f5b-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="32f5b-145">Validieren von Entitäten durch Implementieren der Spezifikations- und Benachrichtigungsmuster</span><span class="sxs-lookup"><span data-stu-id="32f5b-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="32f5b-146">Es gibt einen komplexeren Ansatz zum Implementieren von Validierungen im Domänenmodell. Hierbei wird das Spezifikationsmuster in Verbindung mit dem Benachrichtigungsmuster implementiert, wie in einigen der unten aufgeführten zusätzlichen Ressourcen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="32f5b-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="32f5b-147">Es ist erwähnenswert, dass Sie auch nur eines dieser Muster verwenden können – z.B. das manuelle Validieren mit Steueranweisungen und das Verwenden des Benachrichtigungsmusters zum Stapeln und Zurückgeben einer Liste von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="32f5b-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="32f5b-148">Verwenden der verzögerten Validierung in der Domäne</span><span class="sxs-lookup"><span data-stu-id="32f5b-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="32f5b-149">Es gibt verschiedene Ansätze für den Umgang mit verzögerten Validierungen in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="32f5b-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="32f5b-150">In seinem Buch [Implementing Domain-Driven Design (Implementieren von domänengesteuertem Design)](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) erläutert Vaughn Vernon dies im Abschnitt zur Validierung.</span><span class="sxs-lookup"><span data-stu-id="32f5b-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="32f5b-151">Zweistufige Validierung</span><span class="sxs-lookup"><span data-stu-id="32f5b-151">Two-step validation</span></span>

<span data-ttu-id="32f5b-152">Ziehen Sie auch die zweistufige Validierung in Betracht.</span><span class="sxs-lookup"><span data-stu-id="32f5b-152">Also consider two-step validation.</span></span> <span data-ttu-id="32f5b-153">Verwenden Sie Feldebenenvalidierung für Ihre Datentransferobjekte (DTOs) und Domänenebenenvalidierung innerhalb Ihrer Entitäten.</span><span class="sxs-lookup"><span data-stu-id="32f5b-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="32f5b-154">Dazu wird ein Ergebnisobjekt anstelle von Ausnahmen zurückgegeben, um den Umgang mit den Validierungsfehlern zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="32f5b-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="32f5b-155">Wenn Sie z.B. die Feldvalidierung mit Datenanmerkungen verwenden, duplizieren Sie die Validierungsdefinition nicht.</span><span class="sxs-lookup"><span data-stu-id="32f5b-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="32f5b-156">Die Ausführung kann jedoch im Fall von DTOs serverseitig und clientseitig sein (beispielsweise Befehle und ViewModels).</span><span class="sxs-lookup"><span data-stu-id="32f5b-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32f5b-157">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="32f5b-157">Additional resources</span></span>

-   <span data-ttu-id="32f5b-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC (Einführung in die Modellvalidierung in ASP.NET Core MVC)**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="32f5b-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="32f5b-159">**Rick Anderson. Adding validation (Hinzufügen einer Validierung)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="32f5b-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="32f5b-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations (Ersetzen der Ausnahmeauslösungen durch Validierungsbenachrichtigungen)**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="32f5b-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="32f5b-161">**Specification and Notification Patterns (Spezifikations- und Benachrichtigungsmuster)**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="32f5b-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="32f5b-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD) (Die Validierung in domänengesteuertem Design (DDD))**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="32f5b-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="32f5b-163">**Colin Jack. Domain Model Validation (Domänenmodellvalidierung)**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="32f5b-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="32f5b-164">**Jimmy Bogard. Validation in a DDD world (Validierung in einer Welt mit DDD)**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="32f5b-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="32f5b-165">[Zurück] (enumeration-classes-over-enum-types.md) [Weiter] (client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="32f5b-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>
