---
title: "Wählen Sie zwischen herkömmlichen Web-apps und apps einseitige"
description: Architekt moderner Webanwendungen mit ASP.NET Core und Microsoft Azure
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 5bae77fc4e0df9d0bc7fecfad25adfcee2419084
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Wählen Sie zwischen herkömmlichen Web-Apps und einseitige Apps (SPAs)

> "Der Atwood Recht: jede Anwendung, die in JavaScript geschrieben werden, kann schließlich in JavaScript geschrieben."  
> _\-Jeff Atwood_

## <a name="summary"></a>Zusammenfassung

Es gibt zwei allgemeine Vorgehensweisen beim Erstellen von Webanwendungen heute: herkömmlichen Web-Anwendungen, die meisten der Anwendungslogik auf dem Server und einseitige Anwendungen (SPAs), die meisten der Benutzeroberflächenlogik in einem Webbrowser ausführen Ausführen Bei der Kommunikation mit dem Webserver, die in erster Linie mit Web-APIs. Ein Hybridansatz ist auch möglich, die einfachste wird mindestens ein umfassende SPA-ähnliche untergeordnete Anwendungen innerhalb einer größeren herkömmlichen Web-Anwendung hosten.

Verwenden Sie herkömmliche Webanwendungen wenn:

-   Die Anwendung die clientseitige Anforderungen sind oder einfach auch schreibgeschützt.

-   Ihre Anwendung benötigt, um Browser ohne Unterstützung für JavaScript-Funktion.

-   Das Team ist nicht mit JavaScript oder TypeScript Entwicklungstechniken vertraut.

Sie sollten eine SPA verwenden, wenn:

-   Die Anwendung muss eine umfangreiche Benutzeroberfläche mit vielen Funktionen verfügbar machen.

-   Das Team ist mit JavaScript und/oder TypeScript-Entwicklung vertraut.

-   Die Anwendung muss bereits eine API für andere Clients (intern oder öffentlich) verfügbar machen.

Darüber hinaus SPA-Frameworks erfordern größer Architektur und Sicherheit. Größer Änderungsumfang aufgrund der häufigen Updates und neuen Frameworks als herkömmliche Webanwendungen auftreten. Konfigurieren von automatisierten Build- und Bereitstellungsprozessen und Nutzung von Bereitstellungsoptionen wie Container sind schwieriger mit SPA-Anwendungen als herkömmlichen Web-apps.

Verbesserung der benutzerfreundlichkeit, die über die SPA-Modell müssen gegen diese Überlegungen abgewogen werden.

## <a name="when-to-choose-traditional-web-apps"></a>Beim herkömmlichen Web-apps auswählen

Im folgenden finden eine ausführlichere Erläuterung der Gründe für die Entnahme von herkömmlichen Webanwendungen bereits erwähnt.

**Die Anwendung enthält einfache, möglicherweise schreibgeschützt, clientseitige Anforderungen**

Viele Webanwendungen werden in erster Linie durch die meisten ihrer Benutzer in einer nur-Lese Weise genutzt. Nur-Lese (oder überwiegend schreibgeschützten Anwendungen) tendenziell sehr viel einfacher als die, die verwalten und bearbeiten sehr viel systemverarbeitungszeit in Status. Beispielsweise kann ein Suchmodul für einen einzigen Einstiegspunkt mit einem Textfeld und einer zweiten Seite für die Anzeige von Suchergebnissen bestehen. Anonyme Benutzer können auf einfache Weise Anforderungen durchführen, und es besteht kaum Bedarf für die clientseitige Logik. Ebenso besteht ein Blog oder Ihre Inhalte Verwaltungssystem des öffentlichkeitszugewandte Anwendung in der Regel hauptsächlich von Inhalten mit wenig clientseitige Verhalten aus. Solche Anwendungen werden einfach als traditionellen serverbasierten Webanwendungen erstellt, der Logik auf dem Webserver ausführen und Rendern von HTML-Code im Browser angezeigt werden. Die Tatsache, dass jedes eindeutige Seite der Website eine eigene URL, die mit einem Lesezeichen versehene und (Standardmäßig verfügt, ohne dass er dies als separates Feature der Anwendung hinzufügen) von Suchmaschinen indiziert werden können, ist auch bietet einen entscheidenden Vorteil in einem solchen Szenario.

**Ihre Anwendung benötigt, um Browser ohne Unterstützung für JavaScript-Funktion**

Webanwendungen, die in Browsern mit wenig oder keine Unterstützung für JavaScript-Funktion müssen mithilfe von herkömmlichen Web-app-Workflows geschrieben werden soll (oder zumindest können beim ausweichen auf ein solches Verhalten). SPAs benötigen clientseitiges JavaScript, um funktionieren; Wenn sie nicht verfügbar ist, sind SPAs nicht empfehlenswert.

**Das Team ist nicht mit JavaScript oder TypeScript Entwicklungstechniken vertraut**

Wenn Ihr Team mit JavaScript oder TypeScript nicht vertraut sind, jedoch mit serverseitigen Webanwendungsentwicklung vertraut ist, wird sie wahrscheinlich eine herkömmliche Web-app schneller als eine SPA übermitteln können. Wenn die Anwendung SPAs Lernen ist das Ziel oder durch eine SPA Authentifizierungsprozesses erforderlichen Erfahrungsgrad des Benutzers ist erforderlich, sind herkömmlichen Web-apps produktiver geeignet für Teams, die bereits mit dem Erstellen von sie vertraut sind.

## <a name="when-to-choose-spas"></a>Wenn SPAs auswählen

Im folgenden finden eine ausführlichere Erläuterung wann einen Single Page Applications Entwicklung für Ihre Web-app aus auswählen.

**Die Anwendung muss eine umfangreiche Benutzeroberfläche mit vielen Funktionen verfügbar machen.**

SPAs kann rich Client-Side-Funktionalität unterstützen, die keine erneute Laden der Seite Aktionen oder navigieren Sie zwischen den Bereichen der app erforderlich. SPAs können schneller geladen, Abrufen von Daten im Hintergrund, und einzelne Benutzeraktionen sind anpassbar, da die vollständige Seite Neuladen selten sind. SPAs können inkrementelle Updates, die teilweise abgeschlossene Formulare oder Dokumente speichern, ohne dass des Benutzers auf eine Schaltfläche zum Senden eines Formulars unterstützen. Rich Client-Side Verhalten wie das Ziehen und ablegen, können viel schneller als herkömmliche Anwendungen sPAs unterstützt werden. Zum Ausführen der in einer getrennten Modus, vornehmen von Aktualisierungen an eine clientseitige-Modell, die schließlich zurück an den Server synchronisiert werden, sobald eine Verbindung hergestellt wurde, können sPAs entworfen werden. Wählen Sie eine Anwendung im Stil SPA, wenn Ihre app-Anforderungen reichhaltige Funktionen, die hinausgeht enthalten, was typische HTML-Formularen bieten.

Beachten Sie, dass häufig SPAs müssen, um Funktionen zu implementieren, die in herkömmlichen Web-apps, z. B. das Anzeigen einer sinnvollen URL in die Adresse der Symbolleiste spiegeln den aktuellen Vorgang (und ermöglicht Benutzern das Lesezeichen oder deep-Link an diese URL zurückgegeben,) integriert sind. SPAs sollten auch Benutzer im Browsers auf die Schaltflächen zurück und Weiter mit Ergebnissen verwenden, die sie überraschen wird nicht zulassen.

**Das Team ist bei der Entwicklung von JavaScript und/oder TypeScript vertraut**

Schreiben von SPAs erfordert Vertrautheit mit JavaScript und/oder TypeScript und clientseitige Programmiertechniken und Bibliotheken. Das Team sollte beim Schreiben von modernen JavaScript mit einem SPA-Framework, z. B. Angular zuständigen sein.

> ### <a name="references--spa-frameworks"></a>Verweise – SPA-Frameworks
> - **AngularJS**  
> <https://angularjs.org/>
> - **Vergleich von 4 beliebte JavaScript-Frameworks**  
> <https://www.developereconomics.com/Feature-Comparison-of-4-Popular-js-MV-Frameworks>

**Die Anwendung muss bereits eine API für andere Clients (intern oder öffentlich) verfügbar machen**

Wenn Sie bereits eine Web-API für die Verwendung durch andere Clients unterstützen, müssen möglicherweise weniger Aufwand zum Erstellen einer SPA-Implementierung, die diese APIs ausreizen, anstatt die Logik in serverseitigen Format nutzt. SPAs machen umfangreichen Gebrauch von Web-APIs zum Abfragen und Aktualisieren von Daten, wie Benutzer mit der Anwendung interagieren.

## <a name="decision-table--traditional-web-or-spa"></a>Entscheidungstabelle – herkömmlichen Web- oder SPA

In der folgenden Entscheidungstabelle werden einige der grundlegenden Faktoren zu berücksichtigen, bei der Auswahl zwischen einer herkömmlichen Web-Anwendung und einer SPA zusammengefasst.

  | **Faktor** | **Herkömmlichen Web-App** | **Einzelne Page-Anwendung** |
  |---|---|---|
  | Erforderliche Team Vertrautheit mit JavaScript/TypeScript | **Minimale** | **Erforderlich** |
  | Unterstützen Browser ohne Scripting | **Unterstützt** | **Nicht unterstützt.** |
  | Das Verhalten der minimalen die clientseitige Anwendung | **Eignet sich besonders gut** | **Ausgangsstruktur** |
  | Anforderungen umfangreiche und komplexe an die Benutzeroberfläche | **Begrenzt** | **Eignet sich besonders gut** |

>[!div class="step-by-step"]
[Vorherigen] (Modern-Web-Anwendungen-characteristics.md) [weiter](architectural-principles.md)
