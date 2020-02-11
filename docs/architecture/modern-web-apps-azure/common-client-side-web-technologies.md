---
title: Allgemeine clientseitige Webtechnologien
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Allgemeine clientseitige Webtechnologien
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 7dd3765b1b71d8c1ef22d714a00be3e171fab523
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093122"
---
# <a name="common-client-side-web-technologies"></a>Allgemeine clientseitige Webtechnologien

> „Websites sollten auf der Oberfläche und in ihrem Inneren gut aussehen.“  
> _– Paul Cookson_

ASP.NET Core-Anwendungen sind Webanwendungen. Sie bauen normalerweise auf clientseitigen Webtechnologien wie HTML, CSS oder JavaScript auf. Indem der Inhalt der Seite (die HTML) vom Layout und Format (das CSS) und dessen Verhalten (über JavaScript) getrennt wird, können komplexe Web-Apps dem Prinzip der Separation of Concerns folgen. Die Struktur, das Design und das Verhalten der Anwendung können so unkomplizierter angepasst werden, da sie nicht miteinander verknüpft sind.

Während HTML und CSS verhältnismäßig stabil sind, entwickelt sich JavaScript bezüglich Anwendungsframeworks und Dienstprogrammen, die von Entwicklern zum Erstellen webbasierter Anwendungen verwendet werden, in Rekordgeschwindigkeit weiter. In diesem Artikel erfahren Sie, wie JavaScript von Webentwicklern verwendet wird. Darüber hinaus wird ein allgemeiner Überblick über die clientseitigen Bibliotheken „Angular“ und „React“ gegeben.

## <a name="html"></a>HTML

HTML (Hypertext Markup Language) ist die Standardmarkupsprache zum Erstellen von Webseiten und -anwendungen. Ihre Bestandteile bilden die Grundlage der Seiten und stehen für formatierten Text, Bilder, Formeingaben und andere Strukturen. Wenn ein Browser eine Anforderung an eine URL durchführt, egal ob es sich dabei um das Abrufen einer Seite oder einer Anwendung handelt, ist die erste Rückgabe ein HTML-Dokument. Dieses HTML-Dokument kann auf zusätzliche Informationen zu seinem Aussehen und Layout (in Form von CSS) oder Verhalten (in Form von JavaScript) verweisen oder diese beinhalten.

## <a name="css"></a>CSS

CSS (Cascading Stylesheet) wird verwendet, um das Aussehen und Layout eines HTML-Elements anzugeben. CSS-Formate können direkt auf ein HTML-Element angewendet werden, das separat auf der gleichen Seite angegeben wird, oder das in einer anderen Datei angegeben wird, auf die von der Seite verwiesen wird. Formate werden auf Grundlage ihrer Verwendung zum Auswählen eines HTML-Elements weitergegeben. Ein Format kann z.B. für ein ganzes Dokument gelten, kann aber von einem Format überschrieben werden, das für ein bestimmtes Element gilt. Ebenso wird ein elementspezifisches Format von einem Format überschrieben, das für eine CSS-Klasse gilt, die auf das Element angewendet wurde. Dieses Format wird wiederum von einem Format überschrieben, das auf eine bestimmte Instanz dieses Elements angewendet wird (über dessen ID). Abbildung 6–1

![CSS-Genauigkeitsregeln](./media/image6-1.png)

**Abbildung 6–1**. CSS-Genauigkeitsregeln, aufsteigend.

Es wird empfohlen, Formate in getrennten Stylesheetdateien zu speichern und das auswahlbasierte Weitergeben zu verwenden, um konsistente und wiederverwendbare Formate innerhalb der Anwendung zu verwenden. Vermeiden Sie Formatregeln in HTML. Wenden Sie nur in Ausnahmefällen Formate auf einzelne Elemente an (statt auf ganze Klassen von Elementen oder auf Elemente, auf die eine bestimmte CSS-Klasse angewendet wurde).

### <a name="css-preprocessors"></a>CSS-Präprozessoren

CSS-Stylesheets unterstützen keine bedingte Logik, Variablen oder andere Programmiersprachenfeatures. Deshalb beinhalten große Stylesheets oft viele Wiederholungen, da die gleiche Farbe, Schriftart oder eine andere Einstellung auf verschiedene Varianten von HTML-Elementen und CSS-Klassen angewendet wird. CSS-Präprozessoren tragen dazu bei, dass Ihre Stylesheets dem [DRY-Prinzip](https://deviq.com/don-t-repeat-yourself/) treu bleiben, indem sie Unterstützung für Variablen und Logik hinzufügen.

Die bekanntesten CSS-Präprozessoren sind Sass und LESS. Beide erweitern CSS und stellen Rückwärtskompatibilität bereit. Das bedeutet, dass eine CSS-Datei eine gültige Sass- oder LESS-Datei ist. Sass basiert auf Ruby und LESS auf JavaScript. Beide werden normalerweise im Rahmen Ihres lokalen Entwicklungsprozesses ausgeführt. Beide verfügen über Befehlszeilentools. Visual Studio verfügt über integrierte Unterstützung für ihre Ausführung mithilfe von Gulp- und Grunt-Tasks.

## <a name="javascript"></a>JavaScript

JavaScript ist eine dynamische, interpretierte Programmiersprache, die in der ECMAScript-Sprachspezifikation standardisiert wurde. JavaScript ist die Programmiersprache des Internets. Ähnlich wie CSS kann JavaScript als Attribute innerhalb von HTML-Elementen, als Skriptblöcke auf einer Seite oder in separaten Dateien definiert werden. Genauso wie bei CSS wird auch hier empfohlen, dass Sie JavaScript in separaten Dateien strukturieren, sodass es so weit wie möglich von der HTML getrennt bleibt, die sich auf Webseiten oder in Anwendungsansichten befindet.

Wenn Sie JavaScript in Ihrer Webanwendung verwenden, müssen Sie zumeist folgende Aufgaben ausführen:

- Sie müssen ein HTML-Element auswählen und dieses abrufen und/oder dessen Wert aktualisieren.

- Sie müssen eine Web-API abfragen, um Daten zu erhalten.

- Sie müssen einen Befehl an eine Web-API senden (und auf einen Rückruf mit ihrem Ergebnis reagieren).

- Sie müssen eine Validierung durchführen.

Diese Aufgaben können Sie alle mit JavaScript alleine durchführen, aber es gibt viele Bibliotheken, die Ihnen den Vorgang erleichtern. Eine der ersten und erfolgreichsten Bibliotheken ist jQuery, die immer noch sehr beliebt ist, wenn es darum geht, diese Aufgaben auf Webseiten zu erleichtern. jQuery bietet für Single-Page-Webanwendungen (SPAs) nur wenige der erwünschten Features, die von den Bibliotheken „Angular“ und „React“ bereitgestellt werden.

### <a name="legacy-web-apps-with-jquery"></a>Legacy-Webanwendungen mit jQuery

Obwohl jQuery für JavaScript-Verhältnisse schon sehr alt ist, ist sie immer noch eine häufig verwendete Bibliothek bei der Arbeit mit HTML/CSS und beim Erstellen von Anwendungen, die AJAX-Aufrufe an Web-APIs durchführen. jQuery funktioniert auf Ebene des Dokumentobjektmodells (DOM) des Browsers und bietet nur ein imperatives statt eines deklarativen Modells.

Gehen wir z.B. davon aus, dass ein Element auf einer Seite sichtbar gemacht wird, wenn der Wert eines Textfelds höher als 10 ist. Dies sollte in jQuery normalerweise durch das Schreiben eines Ereignishandlers implementiert werden. Dazu wird Code benötigt, der den Wert des Textfelds untersucht und die Sichtbarkeit des Zielelements basierend auf diesem Wert ändert. Dabei handelt es sich um eine imperative, codebasierte Herangehensweise. In einem anderen Framework wird möglicherweise die Datenbindung verwendet, um die Sichtbarkeit von Elementen deklarativ an den Wert des Textfelds zu binden. Dazu ist das Schreiben von Code nicht nötig. Allerdings müssen Sie stattdessen die betreffenden Elemente mit Datenbindungsattributen versehen. Mit steigender Komplexität des clientseitigen Verhaltens gewährleisten Herangehensweisen, die die Datenbindung einsetzen, oft einfachere Lösungen mit weniger Code und weniger bedingter Komplexität.

### <a name="jquery-vs-a-spa-framework"></a>Vergleich: jQuery und ein SPA-Framework

| **Aspekt** | **jQuery** | **Angular**|
|--------------------------|------------|-------------|
| Abstraktion des DOM | **Ja** | **Ja** |
| AJAX-Unterstützung | **Ja** | **Ja** |
| Deklarative Datenbindung | **No** | **Ja** |
| MVC-Routing | **No** | **Ja** |
| Vorlagen | **No** | **Ja** |
| Deep-Link-Routing | **No** | **Ja** |

Die meisten Features, die jQuery fehlen, können durch andere Bibliotheken hinzugefügt werden. Ein SPA-Framework wie Angular stellt diese Features einfacher bereit, da diese von Anfang an bei dessen Entwicklung berücksichtigt wurden. Zudem ist jQuery eine imperative Bibliothek, was bedeutet, dass Sie jQuery-Funktionen aufrufen müssen, um Vorgänge mit jQuery durchführen zu können. Die meiste Arbeit und die meisten Funktionen, die von SPA-Frameworks bereitgestellt werden, können deklarativ durchgeführt werden, sodass kein Code geschrieben werden muss.

Die Datenbindung ist ein gutes Beispiel dafür. In jQuery ist normalerweise nur eine Codezeile erforderlich, um den Wert eines DOM-Elements abzurufen oder den Wert eines Elements festzulegen. Diesen Code müssen Sie allerdings immer dann schreiben, wenn Sie den Wert eines Elements verändern möchten, und es kann sein, dass dies für mehrere Funktionen auf einer Seite erforderlich ist. Ein weiteres Beispiel ist die Sichtbarkeit von Elementen. In jQuery müssen Sie an verschiedenen Stellen Code schreiben, um zu steuern, welche Elemente sichtbar sein sollen. In allen diesen Fällen muss jedoch beim Gebrauch der Datenbindung kein Code geschrieben werden. Sie binden lediglich den Wert oder die Sichtbarkeit eines Elements oder mehrerer Elemente an ein *ViewModel*-Objekt auf der Seite, und dann werden Änderungen an diesem Objekt automatisch in den gebundenen Elementen widergespiegelt.

### <a name="angular-spas"></a>Angular-SPAs

AngularJS ist schnell zu einem der beliebtesten JavaScript-Frameworks der Welt geworden. In Angular 2 hat das Team das Framework komplett neu gestaltet (mit [TypeScript](https://www.typescriptlang.org/)). Seitdem ist der Name nicht mehr AngularJS, sondern nur noch Angular. Angular – Version 4 ist die aktuelle Version – ist weiterhin ein widerstandsfähiges Framework zum Erstellen von Single-Page-Webanwendungen.

Angular-Anwendungen setzen sich aus Komponenten zusammen. Komponenten vereinen HTML-Vorlagen mit besonderen Objekten und steuern einen Teil der Seite. Hier sehen Sie eine einfache Komponente aus der Angular-Dokumentation:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

Komponenten werden mit der Decorator-Funktion @Component definiert, die Metadaten zur Komponente beinhaltet. Die selector-Eigenschaft gibt die ID des Elements auf der Seite an, auf der die Komponente angezeigt wird. Die template-Eigenschaft ist eine einfache HTML-Vorlage, die einen Platzhalter enthält, der für die name-Eigenschaft des Elements steht, die in der letzten Zeile definiert wird.

Da Angular-Anwendungen mit Komponenten und Vorlagen statt mit DOM-Elementen arbeiten, ist ihr Grad an Abstraktion höher, und sie erfordern insgesamt weniger Code als Apps, die nur mit JavaScript (auch als „Vanilla JS“ bezeichnet) oder jQuery geschrieben wurden. Außerdem sorgt Angular für einen gewissen Grad an Ordnung bei der Organisation Ihrer clientseitigen Skriptdateien. Gemäß der Konvention verwenden Angular-Apps eine gemeinsame Ordnerstruktur, wobei sich Modul- und Komponentenskriptdateien in einem App-Ordner befinden. Angular-Skripts zum Erstellen, Bereitstellen und Testen der App befinden sich normalerweise in einem Ordner auf einer höheren Ebene.

Angular-Apps können mithilfe einer CLI entwickelt werden. Um lokal mit der Angular-Entwicklung beginnen zu können (wenn Sie git und npm bereits installiert haben), müssen Sie einfach nur ein Repository von GitHub kopieren und `npm install` und `npm start` ausführen. Darüber hinaus ist eine eigene CLI im Lieferumfang von Angular enthalten, mit der Projekte erstellt, Dateien hinzugefügt und Test-, Bündelungs- und Bereitstellungstasks unterstützt werden können. Durch diese CLI-Fähigkeit ist Angular insbesondere kompatibel mit ASP.NET Core, das ebenfalls CLI-Unterstützung beinhaltet.

Microsoft hat die Beispielanwendung [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) entwickelt, die eine Angular-SPA-Implementierung enthält. Diese App beinhaltet Angular-Module zum Verwalten von Einkaufswagen in Onlineshops, zum Laden und Anzeigen von Artikeln aus dem Katalog des Shops und zum Verarbeiten einer Bestellung. Sie können die Beispielanwendung von [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA) herunterladen.

### <a name="react"></a>React

Im Gegensatz zu Angular, das eine vollständige Implementierung des MVC-Musters bereitstellt, befasst React sich nur mit Ansichten. React ist kein Framework, sondern lediglich eine Bibliothek, sodass Sie zum Erstellen einer SPA zusätzliche Bibliotheken benötigen.

Eines der wichtigsten Features von React ist das virtuelle DOM. Das virtuelle DOM in React hat mehrere Vorteile, u.a. bei der Leistung (das virtuelle DOM optimiert, welche Teile des DOM tatsächlich aktualisiert werden müssen) und bei der Testbarkeit (es wird kein Browser zum Testen von React und dessen Interaktionen mit seinem virtuellen DOM benötigt).

Außerdem arbeitet React auf ungewöhnliche Weise mit HTML. Statt einer strikten Trennung zwischen Code und Markup (mit möglichen Verweisen auf JavaScript in HTML-Attributen), fügt React HTML direkt als JSX in seinen JavaScript-Code ein. JSX ist eine Syntax ähnlich wie HTML, die zu reinem JavaScript kompiliert werden kann. Zum Beispiel:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

Wenn Sie bereits mit JavaScript vertraut sind, sollte das Erlernen von React unkompliziert sein. Sie müssen sich bei Weitem nicht so viel Wissen oder besondere Syntax aneignen wie bei Angular oder anderen beliebten Bibliotheken.

Da es sich bei React nicht um ein vollständiges Framework handelt, sollten sich andere Bibliotheken um Routing, Web-API-Aufrufe und die Abhängigkeitsverwaltung kümmern. Der Vorteil besteht darin, dass Sie sich so die beste Bibliothek für jede dieser Aufgaben aussuchen können. Der Nachteil besteht allerdings darin, dass sie sich aktiv mit diesen Entscheidungen auseinandersetzen und sicherstellen müssen, dass die ausgewählten Bibliotheken gut miteinander funktionieren. Wenn Sie einen guten Ausgangspunkt haben möchten, können Sie ein Starter Kit wie React Slingshot verwenden, in dem mehrere kompatible Bibliotheken gemeinsam mit React vorverpackt sind.

### <a name="choosing-a-spa-framework"></a>Entscheidung für ein SPA-Framework

Wenn Sie sich für ein JavaScript-Framework entscheiden müssen, das Ihre SPA am besten unterstützt, beachten Sie besonders die folgenden Aspekte:

- Kennt sich Ihr Team mit dem Framework und dessen Abhängigkeiten aus (dies umfasst in einigen Fällen auch TypeScript)?

- Wie „eigenwillig“ ist das Framework, und passt sein Standardverhalten zu Ihren Bedürfnissen?

- Enthält es (oder eine zugehörige Bibliothek) alle Features, die Ihre App benötigt?

- Ist es gut dokumentiert?

- Wie aktiv ist seine Community? Werden damit neue Projekte erstellt?

- Wie aktiv ist das Kernteam? Werden Probleme behoben und regelmäßig neue Versionen veröffentlicht?

JavaScript-Frameworks entwickeln sich in Rekordgeschwindigkeit weiter. Entscheiden Sie sich anhand der oben aufgelisteten Fragen für ein geeignetes Framework. Wenn es sein kann, dass sich ein Framework für Sie schnell als ungeeignet herausstellt, entscheiden Sie sich für ein Framework, dass kommerziellen Support anbietet und/oder von einem großen Unternehmen entwickelt wird.

> ### <a name="references--client-web-technologies"></a>Ressourcen: Clientseitige Webtechnologien
>
> - **HTML und CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Vergleich von Sass und LESS**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **Formatieren von Apps mit LESS, Sass und Font Awesome**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **Clientseitige Entwicklung in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery vs. AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **Angular**  
> <https://angular.io/>
> - **React**  
> <https://facebook.github.io/react/>
> - **React Slingshot**  
> <https://github.com/coryhouse/react-slingshot>
> - **Vergleich von React und Angular 2**  
> <https://www.codementor.io/codementorteam/react-vs-angular-2-comparison-beginners-guide-lvz5710ha>
> - **5 Best JavaScript Frameworks of 2017 (Die 5 besten JavaScript-Frameworks 2017)**  
> <https://hackernoon.com/5-best-javascript-frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
>[Zurück](common-web-application-architectures.md)
>[Weiter](develop-asp-net-core-mvc-apps.md)
