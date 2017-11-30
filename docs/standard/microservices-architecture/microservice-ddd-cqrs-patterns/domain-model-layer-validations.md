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
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="e9036-104">Entwerfen von Überprüfungen in der Domäne der Ebene</span><span class="sxs-lookup"><span data-stu-id="e9036-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="e9036-105">In DDD können Validierungsregeln als invarianten betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="e9036-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="e9036-106">Die wichtigsten Verantwortung eines Aggregats besteht darin, invarianten für Zustandsänderungen für alle Entitäten innerhalb dieses Aggregat zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e9036-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="e9036-107">Domänenentitäten sollte immer gültige Entitäten sein.</span><span class="sxs-lookup"><span data-stu-id="e9036-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="e9036-108">Es gibt eine bestimmte Anzahl von Invarianten für ein Objekt, das immer "true" werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9036-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="e9036-109">Beispielsweise verfügt ein Order-Element-Objekt immer eine Menge ist, die muss eine positive ganze Zahl plus einen Artikelnamen und Preis.</span><span class="sxs-lookup"><span data-stu-id="e9036-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="e9036-110">Aus diesem Grund invarianten Erzwingung liegt in der Verantwortung der Domänenentitäten (insbesondere von aggregierten Stamm) und ein Entitätsobjekt sollten nicht in der Lage, ohne gültigen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="e9036-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="e9036-111">Invariante Regeln werden einfach als Verträge angegeben wird, und Ausnahmen oder Benachrichtigungen ausgelöst werden, wenn sie verletzt werden.</span><span class="sxs-lookup"><span data-stu-id="e9036-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="e9036-112">Die Überlegung hinter dieser ist, dass viele Fehler auftreten, weil Objekte in einem Zustand befinden, in denen sie nie in Waren sollten.</span><span class="sxs-lookup"><span data-stu-id="e9036-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="e9036-113">Im folgenden finden Sie eine gute Erläuterung von Greg Young in ein [online Diskussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="e9036-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="e9036-114">Wir schlagen vor, dass wir jetzt haben eine SendUserCreationEmailService an, die akzeptiert UserProfile... wie wir innerhalb des betreffenden Diensts rationalisieren können, dass der Name nicht null ist?</span><span class="sxs-lookup"><span data-stu-id="e9036-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="e9036-115">Überprüfen wir es erneut zu?</span><span class="sxs-lookup"><span data-stu-id="e9036-115">Do we check it again?</span></span> <span data-ttu-id="e9036-116">Oder wahrscheinlicher... einfach nicht darum kümmern überprüfen und "hoffen optimale" – Sie hoffen, dass jemand behindert, zu überprüfen, bevor sie an Sie gesendet.</span><span class="sxs-lookup"><span data-stu-id="e9036-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="e9036-117">Natürlich verwenden der testgesteuerten Entwicklung des ersten Tests, die wir also, wenn ich, dass er einen Fehler auszulösen, sollte ein Kunde mit einem null-Namen senden geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9036-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="e9036-118">Beachten dabei aber sobald wir diese Arten von Tests immer wieder schreiben starten wir... "Warten Sie, wenn wir Namen werden Sie niemals zulässig null wir wäre nicht verfügen über alle diese Tests"</span><span class="sxs-lookup"><span data-stu-id="e9036-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="e9036-119">Implementieren von Überprüfungen in der Domäne der Ebene</span><span class="sxs-lookup"><span data-stu-id="e9036-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="e9036-120">Überprüfungen werden in der Regel implementiert, in der Domäne Entität Konstruktoren oder Methoden, mit die die Entität aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e9036-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="e9036-121">Es gibt mehrere Möglichkeiten zum Implementieren von Überprüfungen, z. B. überprüft, ob Daten und das Auslösen von Ausnahmen, wenn die Validierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e9036-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="e9036-122">Es gibt auch erweiterte Muster wie die Verwendung des Musters Spezifikation für Validierungen und die Benachrichtigung Muster zum Zurückgeben einer Auflistung von Fehlern, anstatt eine Ausnahme für jede Überprüfungen, während es eintritt.</span><span class="sxs-lookup"><span data-stu-id="e9036-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="e9036-123">Überprüfen von Bedingungen und Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e9036-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="e9036-124">Das folgende Codebeispiel zeigt die einfachste Vorgehensweise bei der Überprüfung in eine Entität "Domain" durch Auslösen einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="e9036-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="e9036-125">In der Tabelle "Verweise" am Ende dieses Abschnitts können Sie sehen, Links zu weiter fortgeschrittene Implementierungen, die auf der Grundlage der Muster, die wir zuvor besprochen haben können.</span><span class="sxs-lookup"><span data-stu-id="e9036-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="e9036-126">Ein Beispiel für eine bessere veranschaulichen, würde die Notwendigkeit, stellen Sie sicher, dass entweder der interne Zustand nicht geändert hat oder dass alle Mutationen für eine Methode aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e9036-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="e9036-127">Die folgende Implementierung würde z. B. das Objekt in einem ungültigen Zustand lassen:</span><span class="sxs-lookup"><span data-stu-id="e9036-127">For example, the following implementation would leave the object in an invalid state:</span></span>

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

<span data-ttu-id="e9036-128">Wenn der Wert des Status ungültig ist, wurden die erste Adresszeile und den Ort bereits geändert.</span><span class="sxs-lookup"><span data-stu-id="e9036-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="e9036-129">Die möglicherweise die Adresse ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="e9036-129">That might make the address invalid.</span></span>

<span data-ttu-id="e9036-130">Ein ähnlicher Ansatz kann verwendet werden, in der Entität Konstruktor durch das Auslösen einer Ausnahme, um sicherzustellen, dass die Entität gültig ist, sobald es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e9036-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="e9036-131">Verwenden Validierungsattribute in das Modell anhand von datenanmerkungen</span><span class="sxs-lookup"><span data-stu-id="e9036-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="e9036-132">Ein anderer Ansatz ist die Verwendung von Validierungsattributen basierend auf datenanmerkungen.</span><span class="sxs-lookup"><span data-stu-id="e9036-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="e9036-133">Validierungsattribute bieten eine Möglichkeit modellvalidierung konfigurieren, die Überprüfung auf Felder in Datenbanktabellen vom Konzept her ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="e9036-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="e9036-134">Dazu gehören Einschränkungen wie z. B. das Zuweisen von Datentypen oder Pflichtfelder.</span><span class="sxs-lookup"><span data-stu-id="e9036-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="e9036-135">Andere Typen von Validierung umfasst die Anwendung von Mustern auf Daten zum Erzwingen von Geschäftsregeln, z. B. eine Kreditkartennummer, Telefonnummer oder e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="e9036-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="e9036-136">Validierungsattribute erleichtern es, um Anforderungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e9036-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="e9036-137">Jedoch wie im folgenden Code gezeigt wird, diesen Ansatz zu aufwendig, in einem Modell DDD möglicherweise, da es eine Abhängigkeit auf ModelState.IsValid von Microsoft.AspNetCore.Mvc.ModelState, führt die vom MVC-Controllers heraus aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="e9036-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="e9036-138">Die modellüberprüfung wird vor jeder Controlleraktion aufgerufen wurde, und es obliegt dem Controllermethode überprüfen das Ergebnis des aufrufenden ModelState.IsValid und entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="e9036-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="e9036-139">Die Entscheidung zur Verwendung abhängig, wie eng gekoppelt, das Modell, das mit dieser Infrastruktur werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9036-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

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

<span data-ttu-id="e9036-140">Allerdings ist aus Sicht des eine DDD Domänenmodell am besten lean mit der Verwendung von Ausnahmen in der Entität verhaltensmethoden oder durch die Implementierung der Spezifikationen und zur Benachrichtigung Muster, um Überprüfungsregeln durchzusetzen aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="e9036-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="e9036-141">Überprüfung-Frameworks wie datenanmerkungen in ASP.NET Core oder andere Validierung Frameworks wie FluentValidation führen eine Anforderung für das Anwendungsframework aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e9036-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="e9036-142">Beispielsweise fallen beim Aufrufen der Methode ModelState.IsValid in datenanmerkungen ASP.NET Controller aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e9036-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="e9036-143">Es kann sinnvoll, datenanmerkungen auf Anwendungsebene in ViewModel-Klassen (statt Domänenentitäten) verwenden, die Eingaben zur modellvalidierung in der Benutzeroberflächenebene zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="e9036-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="e9036-144">Dies sollte jedoch nicht an den Ausschluss der Überprüfung innerhalb des Domänenmodells ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9036-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="e9036-145">Überprüfen von Entitäten durch Implementieren der Spezifikation und das Muster für die Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="e9036-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="e9036-146">Schließlich ist ein komplexeren Ansatz zum Implementieren von Überprüfungen im Domänenmodell durch die Implementierung des Musters Spezifikation in Verbindung mit dem Muster Benachrichtigung, wie einige der unten aufgeführten zusätzlichen Ressourcen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9036-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="e9036-147">Es ist erwähnenswert, dass Sie nur eine dieser Muster auch verwenden können – z. B. mit Steueranweisungen manuell überprüfen, aber verwenden Sie das Muster für die Benachrichtigung zum Stapeln und Zurückgeben einer Liste der Validierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="e9036-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="e9036-148">Verwenden die verzögerte Validierung in der Domäne</span><span class="sxs-lookup"><span data-stu-id="e9036-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="e9036-149">Es gibt verschiedene Ansätze für den Umgang mit verzögerten Überprüfungen in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="e9036-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="e9036-150">In seinem Buch [Implementing Domain-Driven Entwurf](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon erläutert diese im Abschnitt zur Validierung.</span><span class="sxs-lookup"><span data-stu-id="e9036-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="e9036-151">Überprüfung in zwei Schritten</span><span class="sxs-lookup"><span data-stu-id="e9036-151">Two-step validation</span></span>

<span data-ttu-id="e9036-152">Berücksichtigen Sie auch die Überprüfung in zwei Schritten.</span><span class="sxs-lookup"><span data-stu-id="e9036-152">Also consider two-step validation.</span></span> <span data-ttu-id="e9036-153">Verwenden Sie Überprüfungsfehler auf, auf Ihre Daten übertragen Befehlsobjekte (DTOs) und Domänenebene Validierung innerhalb der Entitäten.</span><span class="sxs-lookup"><span data-stu-id="e9036-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="e9036-154">Dazu wird durch Zurückgeben der Ergebnisobjekt stattdessen Ausnahmen um für den Umgang mit den Validierungsfehler zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="e9036-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="e9036-155">Feldvalidierung mit datenanmerkungen verwenden, z. B. duplizieren Sie nicht die Überprüfungdefinition.</span><span class="sxs-lookup"><span data-stu-id="e9036-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="e9036-156">Die Ausführung kann jedoch serverseitige und clientseitige im Fall von DTOs sein (Befehle und ViewModels, z. B.).</span><span class="sxs-lookup"><span data-stu-id="e9036-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9036-157">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e9036-157">Additional resources</span></span>

-   <span data-ttu-id="e9036-158">**Rachel Appel. Einführung in die modellvalidierung in ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="e9036-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="e9036-159">**Rick Anderson. Hinzufügen einer Validierung**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="e9036-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="e9036-160">**Martin Fowler. Auslösen von Ausnahmen mit der Benachrichtigung im Überprüfungen ersetzen**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="e9036-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="e9036-161">**Spezifikation und Benachrichtigung Muster**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="e9036-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="e9036-162">**Lev Gorodinski. Die Validierung in Domain Driven Design (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="e9036-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="e9036-163">**Colin an. Domäne Modellvalidierung**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="e9036-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="e9036-164">**Jimmy Bogard. Überprüfung in einer Welt DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="e9036-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e9036-165">[Vorherigen] (Enumeration-Klassen-Over-Enum-types.md) [weiter] (Client-Side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="e9036-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>
