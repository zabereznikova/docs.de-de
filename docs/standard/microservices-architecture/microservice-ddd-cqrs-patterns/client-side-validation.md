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
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Die clientseitige Validierung (Überprüfung in den Darstellungsschichten)

Auch wenn die Quelle der Wahrheitswert des Domänenmodells und letztlich Sie Validierung auf Modellebene Domäne benötigen, kann Überprüfung immer noch auf der Domänenebene Modell (Serverseite) und der Clientseite verarbeitet werden.

Die clientseitige Validierung ist eine hervorragende Erleichterung für Benutzer. Es speichert wartet auf einen Roundtrip aufgewendete Zeit sie andernfalls würde, auf dem Server, der möglicherweise Überprüfungsfehler zurückgeben. Aus geschäftlicher sogar einige wenige Bruchteilen von Sekunden multipliziert unzählige Male pro Tag addiert viel Zeit und Aufwand Frustration. Unkompliziert und sofortige Überprüfung kann Benutzer effizienter arbeiten und erzeugt eine bessere Qualität für ein- und Ausgabe.

Ebenso wie das Anzeigen und die Domänenmodell unterschiedlich sind, modellvalidierung anzeigen und Domäne modellvalidierung ähnlich sein, jedoch einen anderen Zweck erfüllen. Wenn Sie befürchten trocken (das wiederhole Dich nicht Prinzip), zu berücksichtigen, dass in diesem Fall Wiederverwendung von Code auch bedeuten, Kopplung dass kann und in unternehmensanwendungen es wichtiger nicht auf die Serverseite mit dem clientseitigen ist als Designanforderungen TROCKENE Prinzip zu verknüpfen.

Auch wenn Sie die clientseitige Validierung verwenden möchten, sollten immer Ihre Befehle zu überprüfen oder DTOs in Servercode, Eingabe, da der Server-APIs sind ein möglich Angriffsvektor. Beides ist normalerweise am besten da haben eine Client-Anwendung im Hinblick auf UX, es empfohlen wird, proaktive werden und nicht zulassen, dass der Benutzer ungültige Informationen geben.

Aus diesem Grund überprüfen im clientseitigen Code Sie in der Regel die ViewModels. Sie können auch den Client überprüfen DTOs oder Befehle ausgeben, bevor sie an die Dienste zu senden.

Die Implementierung der clientseitigen Validierung hängt davon ab, welche Art von Client-Anwendung, die Sie erstellen. Unterschiedlich sein, wenn Sie Daten in einer webbasierten MVC-Webanwendung mit Großteil des Codes in einer Webanwendung SPA, Validierung, die in JavaScript oder TypeScript programmiert wird .NET überprüfen oder eine mobile app mit Xamarin und C# hartcodiert\#.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

### <a name="validation-in-xamarin-mobile-apps"></a>Die Validierung in mobilen Xamarin-apps

-   **Validieren von Text Eingabe- und Fehler anzeigen**
    [*https://developer.xamarin.com/recipes/ios/standard\_Steuerelemente/Text\_Feld/Überprüfen von\_Eingabe-/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

-   **Validierungsrückruf**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)

### <a name="validation-in-aspnet-core-apps"></a>Die Validierung in ASP.NET Core-apps

-   **Rick Anderson. Hinzufügen einer Validierung**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Die Validierung in SPA Web-apps (Angular 2 TypeScript JavaScript)

-   **ADO-Kukic. Überprüfung des Formulars Angular 2** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)

-   **Überprüfung des Formulars**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)

-   **Überprüfung.** Kinderspiel-Dokumentation.
    [*http://Breeze.github.IO/doc-js/Validation.HTML*](http://breeze.github.io/doc-js/validation.html)

Zusammenfassend sind dies die wichtigsten Konzepte in Bezug auf Überprüfung:

-   Entitäten und Aggregate sollte ihre eigenen Konsistenz zu erzwingen und "immer gültig" sein. Aggregate sind verantwortlich, Konsistenzgründen mehrerer Entitäten innerhalb der gleichen Aggregat.

-   Wenn Sie glauben, dass eine Entität einen ungültigen Status eingeben muss, erwägen Sie ein anderes Objektmodell – z. B. eine temporäre DTO verwenden, bis Sie die letzte Domänenentität erstellen.

-   Wenn Sie mehrere verwandte Objekte, z. B. ein Aggregat erstellen müssen, und sie sind nur gültig, nachdem alle von ihnen erstellt wurden, sollten erwägen Sie, die Diensthostfactory-Muster zu verwenden.

-   Überprüfung Frameworks werden in bestimmten Schichten, z. B. die Darstellungsschicht oder die Anwendung bzw. eines Diensts-Ebene, aber normalerweise nicht auf der Ebene der Domäne Modell am besten verwendet, da werden müssten, schalten Sie ein Framework für die Infrastruktur eine starke Abhängigkeit.

-   In den meisten Fällen ist mit redundanten Überprüfung clientseitig gut, weil die Anwendung proaktiv kann.


>[!div class="step-by-step"]
[Vorherigen] (Domäne-Modell-Ebene – validations.md) [weiter] (Domäne-Ereignisse-Design-implementation.md)
