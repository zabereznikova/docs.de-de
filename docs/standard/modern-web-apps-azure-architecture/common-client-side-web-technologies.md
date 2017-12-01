---
title: Allgemeine Client Side Web-Technologien
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Allgemeine Client Side Web-Technologien
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 1084aee3d81a5df6ac99d6ec0e2ef647b4173c24
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="common-client-side-web-technologies"></a>Allgemeine Client Side Web-Technologien

> "Websites sollte guten von innen nach"und"out."  
> _-Paul Cookson_

## <a name="summary"></a>Zusammenfassung

ASP.NET Core-Anwendungen sind Webanwendungen,, und sie i. d. r. abhängig sind, auf die clientseitige webtechnologien wie HTML, CSS und JavaScript. Durch die Trennung von des Inhalts der Seite (HTML) über das Layout und formatieren (CSS) und sein Verhalten (über JavaScript), können komplexe Web-apps das Prinzip der Trennung von Bereichen nutzen. Zukünftige Änderungen an der Struktur, Entwurf, oder das Verhalten der Anwendung können problemlos weitere vorgenommen werden, wenn diese Probleme nicht ineinander greifen sind.

HTML und CSS sind relativ stabilen JavaScript mithilfe der Anwendungsframeworks und Dienstprogramme Entwickler zum Erstellen von webbasierten Anwendungen arbeiten, wird mit breakneck Geschwindigkeit weiterentwickelt. In diesem Kapitel prüft einige Arten, die von Webentwicklern im Rahmen der Entwicklung von Anwendungen, wie eine allgemeine Übersicht über das Drehmoment und reagieren clientseitige Bibliotheken enthält JavaScript verwendet wird.

## <a name="html"></a>HTML

HTML (HyperText Markup Language) ist die standardmäßige Markupsprache, die zum Erstellen von Webseiten und Web-Apps verwendet. Die Elemente bilden die Bausteine der Seiten, formatierten Text, Bilder, Formulareingaben und andere Strukturen darstellt. Wenn ein Browser an eine URL anfordert, ob eine Seite oder eine Anwendung abrufen, ist also zuerst zurückgegebenen ein HTML-Dokument. HTML-Dokument verweisen oder zusätzliche Informationen über den Aussehen und Layout in Form von CSS oder Verhalten in Form von JavaScript enthalten.

## <a name="css"></a>CSS

CSS (Cascading Style Sheets) wird verwendet, um das Aussehen und Layout der HTML-Elemente zu steuern. CSS-Formatvorlagen können direkt auf ein HTML-Element angewendet, definiert separat auf derselben Seite oder in einer separaten Datei definiert und werden auf der Seite verwiesen wird. Stile kaskadiert werden basierend auf deren Verwendung auf einem angegebenen HTML-Element. Z. B. ein Stil kann möglicherweise für das gesamte Dokument angewendet, aber würde überschrieben werden, indem ein Format, das auf ein bestimmtes Element angewendet. Ebenso würde eine Formatvorlage elementspezifischen durch einen Stil außer Kraft gesetzt werden, die auf eine CSS-Klasse angewendet, die auf das Element angewendet wurde, die wiederum von einer im Format für eine bestimmte Instanz des jeweiligen Elements (über seine Id) überschrieben werden würde. Abbildung 6 – 1

**Abbildung 6 – 1.** Besonderheit der CSS-Regeln in der Reihenfolge.

![](./media/image6-1.png)

Es wird empfohlen, damit Stile in eigenen separaten Stylesheet-Dateien und mit konsistente und wiederverwendbare Stile in der Anwendung implementiert Auswahl basierende cascading. Platzieren Stilregeln in HTML sollte vermieden werden, und Anwenden von Stilen auf bestimmte einzelne Elemente (anstelle von ganze Klassen von Elementen oder Elementen, die eine bestimmte CSS-Klasse, die auf sie angewendet wurden) muss sich auf die Ausnahme, die nicht die Regel.

### <a name="css-preprocessors"></a>CSS-Präprozessoren

CSS-Stylesheets fehlender Unterstützung für bedingte Logik, Variablen und andere Programmiersprachenfeatures. Große Stylesheets gehören daher häufig viele Wiederholung, wie die gleiche Farbe, Schriftart oder andere Einstellungen auf viele verschiedene Variationen von HTML-Elemente und CSS-Klassen angewendet wird. CSS-Präprozessoren können Ihre Stylesheets, befolgen Sie die [TROCKENEN Prinzip](http://deviq.com/don-t-repeat-yourself/) durch Hinzufügen von Unterstützung für Variablen und Logik.

Die am häufigsten verwendeten CSS-Präprozessoren sind Sass und kleiner. Beide CSS erweitern und sind abwärtskompatibel ist, was bedeutet, dass eine einfache CSS-Datei eine gültige Sass oder LESS-Datei ist. Sass basiert auf Ruby und JavaScript-basiertes liegt, und sowohl in der Regel als Teil des lokalen Entwicklungs-Prozesses ausgeführt. Beide Befehl Zeile tools verfügbar, als auch integrierte Unterstützung in Visual Studio für sie ausgeführt haben, verwenden von Gulp oder Grunt-Aufgaben.

## <a name="javascript"></a>JavaScript

JavaScript ist eine dynamische, interpretiert Programmiersprache, die in der ECMAScript-Sprachspezifikation standardisiert wurde. Es ist der Programmiersprache ab, der im Web. Wie CSS kann JavaScript als Attribute in den HTML-Elementen als Blöcke des Skripts innerhalb einer Seite oder in separaten Dateien definiert werden. Genau wie CSS wurde in der Regel empfohlen, JavaScript in separate Dateien organisieren halten getrennt so weit wie möglich aus dem HTML-Code finden Sie auf den einzelnen Webseiten oder Sichten.

Bei der Arbeit mit JavaScript in der Webanwendung stehen einige Aufgaben, die Sie häufig ausführen müssen:

-   Ein HTML-Element auswählen und Abrufen von und/oder aktualisieren den Wert

-   Abfragen einer Web-API für Daten

-   Senden eines Befehls an einer Web-API (und reagieren auf einen Rückruf mit Ergebnis)

-   Überprüfung wird durchgeführt

Sie können diese Aufgaben mit JavaScript allein ausführen, aber viele Bibliotheken vorhanden sein, um diese Aufgaben zu vereinfachen. Einer der ersten und die meisten dieser Bibliotheken erfolgreichen ist jQuery, der weiterhin eine beliebte Wahl für diese Aufgaben auf Webseiten vereinfacht werden. JQuery für Single Page Applications (SPAs) stellt keine viele der gewünschten Funktionen bereit, mit denen Angular und reagieren zu können.

### <a name="legacy-web-apps-with-jquery"></a>Ältere Web-Apps mit jQuery

Obwohl der alten durch JavaScript-Framework-Standards, weiterhin jQuery eine sehr häufig verwendete Bibliothek zum Arbeiten mit HTML/CSS, und Erstellen von Anwendungen, die AJAX-Aufrufe auf Web-APIs ausführen. Allerdings jQuery auf der Ebene des Browser-Dokumentobjektmodells (DOM) arbeitet und bietet standardmäßig nur eine imperative, anstatt deklarativen Modell.

Angenommen Sie, dass wenn ein Textfeld Wert 10 überschreitet, ein Element auf der Seite sichtbar gemacht werden soll. In jQuery würde dies in der Regel implementiert werden durch einen Ereignishandler mit Code, der Wert des Textfelds untersuchen, und legen Sie die Sichtbarkeit des Zielelements basierend auf diesem Wert würde zu schreiben. Dies ist eine imperative codebasierte Ansatz. Ein anderes Framework möglicherweise stattdessen Databinding verwenden, um die Sichtbarkeit des Elements deklarativ auf den Wert des Textfelds zu binden. Dies ist kein notwendig Code schreiben zu müssen, aber stattdessen nur erfordert ergänzen die Elemente, die an Daten binden von Attributen. Seite Clientverhalten komplexere wachsen, nähert Datenbindung häufig in einfachere Lösung mit weniger Code und Komplexität bedingter Ergebnis.

### <a name="jquery-vs-a-spa-framework"></a>jQuery Vs ein SPA-Framework

| **Faktor** | **jQuery** | **Angular**|
|--------------------------|------------|-------------|
| Das DOM abstrahiert | **Ja** | **Ja** |
| AJAX-Unterstützung | **Ja** | **Ja** |
| Deklarative Datenbindung | **No** | **Ja** |
| Routing von MVC-Stil | **No** | **Ja** |
| Textvorlagen | **No** | **Ja** |
| Deep-Link-Routing | **No** | **Ja** |

Die meisten Funktionen, die jQuery systemintern fehlt, können durch das Hinzufügen von anderen Bibliotheken hinzugefügt werden. Eine SPA-Framework, z. B. Angular bietet jedoch diese Funktionen auf eine Weise mehr integrierte, da es mit allen von ihnen Bedenken vom Beginn entworfen wurde. JQuery ist auch eine sehr imperative Bibliothek, was bedeutet, dass Sie jQuery-Funktionen aufrufen, um macht nichts mit jQuery müssen. Ein Großteil der Arbeit und Funktionen, die SPA-Frameworks stellen deklarativ möglich, erfordern keine tatsächlichen Code geschrieben werden.

Binden von Daten ist ein hervorragendes Beispiel für dieses. In jQuery dauert es in der Regel nur eine Codezeile zum Abrufen des Werts ein DOM-Element oder Wert des Elements festgelegt. Allerdings müssen Sie zum Schreiben des Codes jederzeit müssen Sie den Wert des Elements zu ändern und in einigen Fällen wird dies in mehrere Funktionen auf einer Seite auftreten. Ein anderes häufiges Beispiel ist die Sichtbarkeit von Elementen. In jQuery möglicherweise vielen verschiedene Quellen, Schreiben Sie Code steuern möchten, ob bestimmte Elemente sichtbar waren. In jedem dieser Fälle, wenn die Datenbindung verwenden würde kein Code geschrieben werden müssen. Binden Sie einfach den Wert oder die Sichtbarkeit des betreffenden Elemente eine *Viewmodel* auf der Seite "sowie die Änderungen, würde Viewmodel automatisch in den gebundenen Elementen wiedergegeben werden.

### <a name="angular-spas"></a>Angular SPAs

AngularJS wurde schnell mit einer der weltweit am häufigsten verwendeten JavaScript-Frameworks. Mit Angular 2 neu das Team, erstellt das Framework von Grund auf neu einrichten (mit [TypeScript](https://www.typescriptlang.org/)) und von AngularJS an einfach Angular umbenannt. Derzeit weiterhin auf Version 4, Angular eine robuste Framework zum Erstellen von Single Page Applications.

Angular-Anwendungen werden von Komponenten erstellt. Komponenten mit speziellen Objekte kombinieren, HTML-Vorlagen und einen Teil der Seite zu steuern. Eine einfache Komponente aus der Angular Docs wird hier gezeigt:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

Komponenten werden definiert über die @Component Decorator-Funktion, die in den Metadaten über die Komponente akzeptiert. Die Datenauswahl (Eigenschaft) identifiziert die Id des Elements auf der Seite, in diese Komponente angezeigt werden soll. Die Template-Eigenschaft ist eine einfache HTML-Vorlage, die einen Platzhalter, der an die Name-Eigenschaft der Komponente enthält, definiert in der letzten Zeile entspricht.

Arbeiten mit Komponenten und Vorlagen, anstelle von DOM-Elemente können auf einer höheren Ebene der Abstraktion und mit weniger insgesamt Code als apps ausgeführt wird, nur für JavaScript (auch als "Vanille JS" bezeichnet) verwenden oder mit jQuery Angular-apps arbeiten. Angular erzwingt auch einige Reihenfolge auf wie Ihre clientseitige Skriptdateien organisiert. Gemäß der Konvention verwenden Angular-apps eine gemeinsame Ordnerstruktur mit-Modul und die Komponente Skriptdateien, die sich in einem app-Ordner befindet. Angular Skripts erstellen, bereitstellen und testen die app befinden sich in der Regel in einem übergeordneten Ordner dürfte.

Angular nutzt auch hervorragende Tools Befehlszeilenschnittstelle (CLI). Erste Schritte mit Angular Entwicklung lokal (vorausgesetzt, Sie haben bereits Git und Npm installiert) besteht aus Klonen einfach ein Repository aus GitHub und Ausführung \`installieren Sie Npm\` und \`Npm Start\`. Darüber hinaus wird Angular eigene CLI-Tool kann Projekte erstellen, Dateien hinzufügen und Ihnen dabei helfen zu testen, Bündelung und Bereitstellungsaufgaben geliefert. Die CLI tooling Zweckmäßigkeit macht Angular insbesondere mit ASP.NET Core, welche hervorragende CLI unterstützen auch Funktionen kompatibel.

Microsoft hat eine Anwendung Verweis entwickelt [eShopOnContainers](http://aka.ms/MicroservicesArchitecture), darunter eine Angular SPA-Implementierung. Diese app enthält Angular-Module zum Verwalten von des Onlineshops Warenkorb Warenkorb, laden und Anzeigen von Elementen aus seinem Katalog und zum Behandeln von Reihenfolge erstellen. Sie können anzeigen, und Laden Sie die beispielanwendung aus [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).

### <a name="react"></a>reagieren

Im Gegensatz zu Angular, die eine vollständige bietet Model-View-Controller Muster Implementierung reagieren nur mit Sichten betroffen ist. Es ist ein Framework, nur eine Bibliothek nicht um eine SPA zu erstellen, müssen Sie zusätzliche Bibliotheken zu nutzen.

Einer der wichtigsten Funktionen des reagieren ist die Verwendung eines virtuellen DOM Virtuelle DOM bietet mehrere Vorteile, einschließlich Leistung (virtuelle DOM kann optimieren welche Teile des tatsächlichen DOM aktualisiert werden müssen) und die Prüfbarkeit (es muss in einen Browser testen reagieren und seine Interaktionen mit der virtuellen DOM haben) reagieren.

Reagieren ist auch in mit HTML Zusammenarbeit ungewöhnlich. Anstatt eine strikte Trennung zwischen Code und Markup (durch Verweise auf JavaScript im HTML-Attribute angezeigt werden, z. B.), zu reagieren wird als JSX HTML direkt in die JavaScript-Code hinzugefügt. JSX ist HTML-ähnliche Syntax, die auf reinen JavaScript kompiliert werden kann. Zum Beispiel:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

Wenn Sie bereits über JavaScript kennen, sollte das Erlernen von reagieren einfach sein. Es gibt keine fast so viel Lernkurve oder spezielle Syntax als mit dem Angular oder anderen beliebten Bibliotheken sind.

Befindet sich eine vollständigen Framework reagieren nicht, sollten Sie in der Regel, andere Bibliotheken behandeln kann Angaben wie routing, web-API-Aufrufe und abhängigkeitsverwaltung. Das gute ist, Sie können die besten Bibliothek auswählen, für jedes dieser, aber der Nachteil ist, müssen Sie alle diese Entscheidungen zu machen, und stellen Sie sicher, dass alle den ausgewählten Bibliotheken aufeinander abgestimmt, wenn Sie fertig sind. Gegebenenfalls einen guten Ausgangspunkt können Sie ein Starterkit wie Slingshot zu reagieren, die einen Satz von kompatiblen Bibliotheken zusammen mit reagieren prepackages.

### <a name="choosing-a-spa-framework"></a>Auswählen einer SPA-Framework

Bei Berücksichtigung der JavaScript-Framework zur Unterstützung Ihrer SPA am besten geeignet ist, Bedenken Sie Folgendes:

-   Liegt das Team mit der das Framework und die abhängigen Elemente (einschließlich TypeScript in einigen Fällen) vertraut?

-   Wie opinionated ist das Framework, und stimmen Sie mit der Standardmethode Dinge zu erledigen?

-   Ist er (oder eine Begleit-Bibliothek) aller Funktionen enthalten, die Ihre app benötigt?

-   Ist umfassend beschrieben?

-   Wie aktiv der Community ist? Erstellt neue Projekte erstellen, werden mit der sie?

-   Wie aktiv Hashteams Core ist? Werden Probleme werden aufgelöst werden, und neue Versionen werden regelmäßig geliefert?

JavaScript-Frameworks weiterhin mit breakneck Geschwindigkeit entwickeln. Verwenden Sie die oben aufgeführten sind, können Sie das Risiko der Entscheidung für eines Framework, dem Sie später bedauern müssen wird abhängig von Überlegungen. Wenn Sie das Risiko besonders Mengen sind, sollten Sie ein Framework, das bieten die Unterstützung für kommerzielle und/oder wird durch ein großes Unternehmen entwickelt werden.

> ### <a name="references--client-web-technologies"></a>Verweise – Client-Web-Technologien
> - **HTML und CSS**  
> <https://www.w3.org/Standards/Webdesign/htmlcss>
> - **Im Vergleich zur sass WENIGER**  
> <https://www.keycdn.com/Blog/sass-VS-less/>
> - **Formatieren von ASP.NET Core-Apps mit einem niedrigeren Sass und Schriftart Awesome**  
> <https://docs.Microsoft.com/ASPNET/Core/Client-Side/less-sass-FA>
> - **Die clientseitige-Entwicklung in ASP.NET Core**  
> <https://docs.Microsoft.com/ASPNET/Core/Client-Side/>
> - **jQuery**  
> <https://jQuery.com/>
> - **jQuery Vs AngularJS**  
> <https://www.airpair.com/angularjs/Posts/jQuery-angularjs-Comparison-Migration-Walkthrough>
> - **Angular**  
> <https://Angular.IO/>
> - **Reagieren**  
> <https://Facebook.github.IO/REACT/>
> - **Slingshot reagieren**  
> <https://github.com/coryhouse/REACT-Slingshot>
> - **Vs Angular 2 Vergleich reagieren**  
> <https://www.codementor.IO/codementorteam/REACT-VS-Angular-2-Comparison-Beginners-Guide-lvz5710ha>
> - **5 bewährte JavaScript-Frameworks von 2017**  
> <https://hackernoon.com/5-Best-JavaScript-Frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
[Vorherigen] (Allgemeine-Web-Anwendung-architectures.md) [weiter] (Develop-asp-net-core-mvc-apps.md)
