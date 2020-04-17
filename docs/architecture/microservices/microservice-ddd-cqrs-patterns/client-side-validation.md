---
title: Clientseitige Prüfung (Prüfung auf den Darstellungsebenen)
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über wichtige Konzepte für clientseitige Validierungen
ms.date: 10/08/2018
ms.openlocfilehash: 44c1e9fa280b19fcee87d4d1cdfcaa2ab9462f27
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988700"
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="c26c2-103">Clientseitige Prüfung (Prüfung auf den Darstellungsebenen)</span><span class="sxs-lookup"><span data-stu-id="c26c2-103">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="c26c2-104">Obwohl alle Daten aus dem Domänenmodell stammen und dort auch geprüft werden müssen, kann die Prüfung sowohl auf Domänenmodellebene (serverseitig) als auch auf Benutzeroberflächenebene (clientseitig) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c26c2-104">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the UI (client side).</span></span>

<span data-ttu-id="c26c2-105">Die Prüfung auf Clientseite ist ein für Benutzer sehr praktisches Feature,</span><span class="sxs-lookup"><span data-stu-id="c26c2-105">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="c26c2-106">denn sie spart Zeit, die andernfalls verloren gehen würde, während Sie auf einen Roundtrip auf den Server warten, der ggf. Prüfungsfehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c26c2-106">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="c26c2-107">In Unternehmen reicht es schon aus, wenn täglich Hundert Male Bruchteile von Sekunden verloren gehen, denn so summieren sich Kosten, Aufwand und Frustration.</span><span class="sxs-lookup"><span data-stu-id="c26c2-107">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="c26c2-108">Wenn die Prüfung unkompliziert und ohne Umschweife ausgeführt wird, können Benutzer effizienter arbeiten und Eingaben und Ausgaben von besserer Qualität produzieren.</span><span class="sxs-lookup"><span data-stu-id="c26c2-108">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="c26c2-109">Ebenso wie sich das Ansichts- und das Domänenmodell unterscheiden, ähneln sich zwar die Überprüfungen des Ansichts- und des Domänenmodells, erfüllen jedoch einen unterschiedlichen Zweck.</span><span class="sxs-lookup"><span data-stu-id="c26c2-109">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="c26c2-110">Wenn Sie sich an das DRY-Prinzip (Don’t Repeat Yourself) halten, sollten Sie beachten, dass die Wiederverwendung von Code ggf. mit Kopplung einhergeht, denn in Unternehmensanwendungen ist es wichtiger, eine Kopplung der Server- an die Clientseite zu vermeiden, als das DRY-Prinzip einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="c26c2-110">If you are concerned about DRY (the Don't Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="c26c2-111">Selbst wenn Sie die clientseitige Prüfung verwenden, sollten Sie Befehle und Eingabe-DTOs im serverseitigen Code immer überprüfen, da die Server-APIs ein potenzieller Angriffsvektor sind.</span><span class="sxs-lookup"><span data-stu-id="c26c2-111">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="c26c2-112">Das Sicherste ist es, beide Überprüfungen zu verwenden, denn bei Clientanwendungen ist es aus UX-Perspektive empfehlenswert, proaktiv zu sein und nicht zuzulassen, dass Benutzer ungültige Informationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="c26c2-112">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="c26c2-113">Aus diesem Grund überprüfen Sie im clientseitigen Code in der Regel die ViewModels.</span><span class="sxs-lookup"><span data-stu-id="c26c2-113">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="c26c2-114">Sie können auch die Ausgabe-DTOs oder -befehle des Clients überprüfen, bevor sie an die Dienste gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c26c2-114">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="c26c2-115">Die Implementierung der clientseitigen Prüfung hängt davon ab, welche Art von Clientanwendung Sie erstellen,</span><span class="sxs-lookup"><span data-stu-id="c26c2-115">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="c26c2-116">Sie kann anders ausfallen, wenn Sie Daten in einer MVC-Webanwendung mit einem Großteil des Codes in .NET, in einer SPA-Webanwendung in JavaScript oder TypeScript oder in einer mobilen, in Xamarin und C# codierten App prüfen.</span><span class="sxs-lookup"><span data-stu-id="c26c2-116">It will be different if you are validating data in a web MVC web application with most of the code in .NET, a SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c26c2-117">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c26c2-117">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="c26c2-118">Prüfung von mobilen Xamarin-Apps</span><span class="sxs-lookup"><span data-stu-id="c26c2-118">Validation in Xamarin mobile apps</span></span>

- <span data-ttu-id="c26c2-119">**Überprüfen von Texteingaben und Anzeigen von Fehlern** </span><span class="sxs-lookup"><span data-stu-id="c26c2-119">**Validate Text Input and Show Errors** </span></span>\
  [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

- <span data-ttu-id="c26c2-120">**Validation Callback (Überprüfungsrückruf)**  </span><span class="sxs-lookup"><span data-stu-id="c26c2-120">**Validation Callback** </span></span>\
  <https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="c26c2-121">Prüfung in ASP.NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="c26c2-121">Validation in ASP.NET Core apps</span></span>

- <span data-ttu-id="c26c2-122">**Rick Anderson. Hinzufügen der Validierung** </span><span class="sxs-lookup"><span data-stu-id="c26c2-122">**Rick Anderson. Adding validation** </span></span>\
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="c26c2-123">Prüfung in SPA-Web-Apps (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="c26c2-123">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

- <span data-ttu-id="c26c2-124">**Ado Kukic. Angular 2 Form Validation (Formularüberprüfung von Angular 2)**  </span><span class="sxs-lookup"><span data-stu-id="c26c2-124">**Ado Kukic. Angular 2 Form Validation** </span></span>\
  <https://scotch.io/tutorials/angular-2-form-validation>

- <span data-ttu-id="c26c2-125">**Form Validation (Formularüberprüfung)**  </span><span class="sxs-lookup"><span data-stu-id="c26c2-125">**Form Validation** </span></span>\
  <https://angular.io/guide/form-validation>

- <span data-ttu-id="c26c2-126">**Prüfung**</span><span class="sxs-lookup"><span data-stu-id="c26c2-126">**Validation.**</span></span> <span data-ttu-id="c26c2-127">Breeze-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="c26c2-127">Breeze documentation.</span></span> \
  <https://breeze.github.io/doc-js/validation.html>

<span data-ttu-id="c26c2-128">Dies sind die wichtigsten Konzepte in Bezug auf die Prüfung:</span><span class="sxs-lookup"><span data-stu-id="c26c2-128">In summary, these are the most important concepts in regards to validation:</span></span>

- <span data-ttu-id="c26c2-129">Entitäten und Aggregate sollten ihre eigenen Konsistenz erzwingen und „immer gültig“ sein.</span><span class="sxs-lookup"><span data-stu-id="c26c2-129">Entities and aggregates should enforce their own consistency and be "always valid".</span></span> <span data-ttu-id="c26c2-130">Aggregatstämme sind für die Konsistenz mehrerer Entitäten innerhalb desselben Aggregats verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="c26c2-130">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

- <span data-ttu-id="c26c2-131">Wenn Sie glauben, dass eine Entität in einen ungültigen Zustand übergehen muss, sollten Sie die Verwendung eines anderen Objektmodells in Betracht ziehen, z.B. ein vorübergehendes DTO, bis Sie die letzte Domänenentität erstellen.</span><span class="sxs-lookup"><span data-stu-id="c26c2-131">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

- <span data-ttu-id="c26c2-132">Wenn Sie mehrere verwandte Objekte wie ein Aggregat erstellen müssen und diese nur gültig sind, wenn alle von ihnen erstellt wurden, sollten Sie die Verwendung des Factorymusters erwägen.</span><span class="sxs-lookup"><span data-stu-id="c26c2-132">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

- <span data-ttu-id="c26c2-133">In vielen Fällen ist eine redundante Prüfung auf Clientseite von Vorteil, da die Anwendung so proaktiv sein kann.</span><span class="sxs-lookup"><span data-stu-id="c26c2-133">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c26c2-134">[Zurück](domain-model-layer-validations.md)
>[Weiter](domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="c26c2-134">[Previous](domain-model-layer-validations.md)
[Next](domain-events-design-implementation.md)</span></span>
