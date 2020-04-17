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
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Clientseitige Prüfung (Prüfung auf den Darstellungsebenen)

Obwohl alle Daten aus dem Domänenmodell stammen und dort auch geprüft werden müssen, kann die Prüfung sowohl auf Domänenmodellebene (serverseitig) als auch auf Benutzeroberflächenebene (clientseitig) ausgeführt werden.

Die Prüfung auf Clientseite ist ein für Benutzer sehr praktisches Feature, denn sie spart Zeit, die andernfalls verloren gehen würde, während Sie auf einen Roundtrip auf den Server warten, der ggf. Prüfungsfehler zurückgibt. In Unternehmen reicht es schon aus, wenn täglich Hundert Male Bruchteile von Sekunden verloren gehen, denn so summieren sich Kosten, Aufwand und Frustration. Wenn die Prüfung unkompliziert und ohne Umschweife ausgeführt wird, können Benutzer effizienter arbeiten und Eingaben und Ausgaben von besserer Qualität produzieren.

Ebenso wie sich das Ansichts- und das Domänenmodell unterscheiden, ähneln sich zwar die Überprüfungen des Ansichts- und des Domänenmodells, erfüllen jedoch einen unterschiedlichen Zweck. Wenn Sie sich an das DRY-Prinzip (Don’t Repeat Yourself) halten, sollten Sie beachten, dass die Wiederverwendung von Code ggf. mit Kopplung einhergeht, denn in Unternehmensanwendungen ist es wichtiger, eine Kopplung der Server- an die Clientseite zu vermeiden, als das DRY-Prinzip einzuhalten.

Selbst wenn Sie die clientseitige Prüfung verwenden, sollten Sie Befehle und Eingabe-DTOs im serverseitigen Code immer überprüfen, da die Server-APIs ein potenzieller Angriffsvektor sind. Das Sicherste ist es, beide Überprüfungen zu verwenden, denn bei Clientanwendungen ist es aus UX-Perspektive empfehlenswert, proaktiv zu sein und nicht zuzulassen, dass Benutzer ungültige Informationen eingeben.

Aus diesem Grund überprüfen Sie im clientseitigen Code in der Regel die ViewModels. Sie können auch die Ausgabe-DTOs oder -befehle des Clients überprüfen, bevor sie an die Dienste gesendet werden.

Die Implementierung der clientseitigen Prüfung hängt davon ab, welche Art von Clientanwendung Sie erstellen, Sie kann anders ausfallen, wenn Sie Daten in einer MVC-Webanwendung mit einem Großteil des Codes in .NET, in einer SPA-Webanwendung in JavaScript oder TypeScript oder in einer mobilen, in Xamarin und C# codierten App prüfen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

### <a name="validation-in-xamarin-mobile-apps"></a>Prüfung von mobilen Xamarin-Apps

- **Überprüfen von Texteingaben und Anzeigen von Fehlern** \
  [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

- **Validation Callback (Überprüfungsrückruf)**  \
  <https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/>

### <a name="validation-in-aspnet-core-apps"></a>Prüfung in ASP.NET Core-Apps

- **Rick Anderson. Hinzufügen der Validierung** \
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Prüfung in SPA-Web-Apps (Angular 2, TypeScript, JavaScript)

- **Ado Kukic. Angular 2 Form Validation (Formularüberprüfung von Angular 2)**  \
  <https://scotch.io/tutorials/angular-2-form-validation>

- **Form Validation (Formularüberprüfung)**  \
  <https://angular.io/guide/form-validation>

- **Prüfung** Breeze-Dokumentation \
  <https://breeze.github.io/doc-js/validation.html>

Dies sind die wichtigsten Konzepte in Bezug auf die Prüfung:

- Entitäten und Aggregate sollten ihre eigenen Konsistenz erzwingen und „immer gültig“ sein. Aggregatstämme sind für die Konsistenz mehrerer Entitäten innerhalb desselben Aggregats verantwortlich.

- Wenn Sie glauben, dass eine Entität in einen ungültigen Zustand übergehen muss, sollten Sie die Verwendung eines anderen Objektmodells in Betracht ziehen, z.B. ein vorübergehendes DTO, bis Sie die letzte Domänenentität erstellen.

- Wenn Sie mehrere verwandte Objekte wie ein Aggregat erstellen müssen und diese nur gültig sind, wenn alle von ihnen erstellt wurden, sollten Sie die Verwendung des Factorymusters erwägen.

- In vielen Fällen ist eine redundante Prüfung auf Clientseite von Vorteil, da die Anwendung so proaktiv sein kann.

>[!div class="step-by-step"]
>[Zurück](domain-model-layer-validations.md)
>[Weiter](domain-events-design-implementation.md)
