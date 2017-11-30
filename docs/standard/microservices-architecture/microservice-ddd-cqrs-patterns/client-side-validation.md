---
title: "Die clientseitige Validierung (Überprüfung in den Darstellungsschichten)"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Die clientseitige Validierung (Überprüfung in den Darstellungsschichten)"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: db88a3b5c95afdc8d5a20094105f1f5991483ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="5bc82-104">Die clientseitige Validierung (Überprüfung in den Darstellungsschichten)</span><span class="sxs-lookup"><span data-stu-id="5bc82-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="5bc82-105">Auch wenn die Quelle der Wahrheitswert des Domänenmodells und letztlich Sie Validierung auf Modellebene Domäne benötigen, kann Überprüfung immer noch auf der Domänenebene Modell (Serverseite) und der Clientseite verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5bc82-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="5bc82-106">Die clientseitige Validierung ist eine hervorragende Erleichterung für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5bc82-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="5bc82-107">Es speichert wartet auf einen Roundtrip aufgewendete Zeit sie andernfalls würde, auf dem Server, der möglicherweise Überprüfungsfehler zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5bc82-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="5bc82-108">Aus geschäftlicher sogar einige wenige Bruchteilen von Sekunden multipliziert unzählige Male pro Tag addiert viel Zeit und Aufwand Frustration.</span><span class="sxs-lookup"><span data-stu-id="5bc82-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="5bc82-109">Unkompliziert und sofortige Überprüfung kann Benutzer effizienter arbeiten und erzeugt eine bessere Qualität für ein- und Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5bc82-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="5bc82-110">Ebenso wie das Anzeigen und die Domänenmodell unterschiedlich sind, modellvalidierung anzeigen und Domäne modellvalidierung ähnlich sein, jedoch einen anderen Zweck erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5bc82-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="5bc82-111">Wenn Sie befürchten trocken (das wiederhole Dich nicht Prinzip), zu berücksichtigen, dass in diesem Fall Wiederverwendung von Code auch bedeuten, Kopplung dass kann und in unternehmensanwendungen es wichtiger nicht auf die Serverseite mit dem clientseitigen ist als Designanforderungen TROCKENE Prinzip zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="5bc82-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="5bc82-112">Auch wenn Sie die clientseitige Validierung verwenden möchten, sollten immer Ihre Befehle zu überprüfen oder DTOs in Servercode, Eingabe, da der Server-APIs sind ein möglich Angriffsvektor.</span><span class="sxs-lookup"><span data-stu-id="5bc82-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="5bc82-113">Beides ist normalerweise am besten da haben eine Client-Anwendung im Hinblick auf UX, es empfohlen wird, proaktive werden und nicht zulassen, dass der Benutzer ungültige Informationen geben.</span><span class="sxs-lookup"><span data-stu-id="5bc82-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="5bc82-114">Aus diesem Grund überprüfen im clientseitigen Code Sie in der Regel die ViewModels.</span><span class="sxs-lookup"><span data-stu-id="5bc82-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="5bc82-115">Sie können auch den Client überprüfen DTOs oder Befehle ausgeben, bevor sie an die Dienste zu senden.</span><span class="sxs-lookup"><span data-stu-id="5bc82-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="5bc82-116">Die Implementierung der clientseitigen Validierung hängt davon ab, welche Art von Client-Anwendung, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="5bc82-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="5bc82-117">Unterschiedlich sein, wenn Sie Daten in einer webbasierten MVC-Webanwendung mit Großteil des Codes in einer Webanwendung SPA, Validierung, die in JavaScript oder TypeScript programmiert wird .NET überprüfen oder eine mobile app mit Xamarin und C# hartcodiert\#.</span><span class="sxs-lookup"><span data-stu-id="5bc82-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5bc82-118">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5bc82-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="5bc82-119">Die Validierung in mobilen Xamarin-apps</span><span class="sxs-lookup"><span data-stu-id="5bc82-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="5bc82-120">**Validieren von Text Eingabe- und Fehler anzeigen**
    [*https://developer.xamarin.com/recipes/ios/standard\_Steuerelemente/Text\_Feld/Überprüfen von\_Eingabe-/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="5bc82-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="5bc82-121">**Validierungsrückruf**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="5bc82-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="5bc82-122">Die Validierung in ASP.NET Core-apps</span><span class="sxs-lookup"><span data-stu-id="5bc82-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="5bc82-123">**Rick Anderson. Hinzufügen einer Validierung**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="5bc82-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="5bc82-124">Die Validierung in SPA Web-apps (Angular 2 TypeScript JavaScript)</span><span class="sxs-lookup"><span data-stu-id="5bc82-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="5bc82-125">**ADO-Kukic. Überprüfung des Formulars Angular 2** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="5bc82-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="5bc82-126">**Überprüfung des Formulars**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="5bc82-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="5bc82-127">**Überprüfung.**</span><span class="sxs-lookup"><span data-stu-id="5bc82-127">**Validation.**</span></span> <span data-ttu-id="5bc82-128">Kinderspiel-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5bc82-128">Breeze documentation.</span></span>
    [<span data-ttu-id="5bc82-129">*http://Breeze.github.IO/doc-js/Validation.HTML*</span><span class="sxs-lookup"><span data-stu-id="5bc82-129">*http://breeze.github.io/doc-js/validation.html*</span></span>](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="5bc82-130">Zusammenfassend sind dies die wichtigsten Konzepte in Bezug auf Überprüfung:</span><span class="sxs-lookup"><span data-stu-id="5bc82-130">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="5bc82-131">Entitäten und Aggregate sollte ihre eigenen Konsistenz zu erzwingen und "immer gültig" sein.</span><span class="sxs-lookup"><span data-stu-id="5bc82-131">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="5bc82-132">Aggregate sind verantwortlich, Konsistenzgründen mehrerer Entitäten innerhalb der gleichen Aggregat.</span><span class="sxs-lookup"><span data-stu-id="5bc82-132">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="5bc82-133">Wenn Sie glauben, dass eine Entität einen ungültigen Status eingeben muss, erwägen Sie ein anderes Objektmodell – z. B. eine temporäre DTO verwenden, bis Sie die letzte Domänenentität erstellen.</span><span class="sxs-lookup"><span data-stu-id="5bc82-133">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="5bc82-134">Wenn Sie mehrere verwandte Objekte, z. B. ein Aggregat erstellen müssen, und sie sind nur gültig, nachdem alle von ihnen erstellt wurden, sollten erwägen Sie, die Diensthostfactory-Muster zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bc82-134">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="5bc82-135">Überprüfung Frameworks werden in bestimmten Schichten, z. B. die Darstellungsschicht oder die Anwendung bzw. eines Diensts-Ebene, aber normalerweise nicht auf der Ebene der Domäne Modell am besten verwendet, da werden müssten, schalten Sie ein Framework für die Infrastruktur eine starke Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="5bc82-135">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="5bc82-136">In den meisten Fällen ist mit redundanten Überprüfung clientseitig gut, weil die Anwendung proaktiv kann.</span><span class="sxs-lookup"><span data-stu-id="5bc82-136">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5bc82-137">[Vorherigen] (Domäne-Modell-Ebene – validations.md) [weiter] (Domäne-Ereignisse-Design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="5bc82-137">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
