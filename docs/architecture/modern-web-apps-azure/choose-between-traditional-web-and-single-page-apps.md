---
title: Auswählen zwischen herkömmlichen Webanwendungen und Single-Page-Webanwendungen (SPAs)
description: In diesem Artikel erfahren Sie, wie Sie beim Erstellen von Webanwendungen zwischen herkömmlichen Web-Apps und Single-Page-Webanwendungen (Single Page Application, SPAs) auswählen.
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 9ede64249705aba3f22a9663b8a258e41f030aca
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739456"
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Auswählen zwischen herkömmlichen Webanwendungen und Single-Page-Webanwendungen (SPAs)

> „Atwoods Gesetz: Alle Anwendungen, die in JavaScript geschrieben werden können, werden früher oder später in JavaScript geschrieben.“  
> _\- Jeff Atwood_

Heutzutage gibt es zwei allgemeine Ansätze für das Erstellen von Webanwendungen: herkömmliche Webanwendungen, die einen Großteil der Anwendungslogik auf dem Server ausführen, und Single-Page-Webanwendungen (SPAs), die einen Großteil der Logik der Benutzeroberfläche in einem Webbrowser ausführen und mit dem Webserver überwiegend über Web-APIs kommunizieren. Ein hybrider Ansatz ist ebenfalls möglich, am einfachsten ist das Hosten von mindestens einer umfangreichen SPA-ähnlichen Unteranwendung in einer größeren herkömmlichen Webanwendung.

Sie sollten herkömmliche Webanwendungen in folgenden Szenarios verwenden:

- Die clientseitigen Anforderungen Ihrer Anwendung sind einfach oder schreibgeschützt.

- Ihre Anwendung muss in Browsern ohne Unterstützung für JavaScript funktionieren.

- Ihr Team ist nicht mit Entwicklungstechniken mit JavaScript oder TypeScript vertraut.

In folgenden Szenarios sollten Sie eine Single-Page-Webanwendung verwenden:

- Ihre Anwendung muss eine umfangreiche Benutzeroberfläche mit vielen Features zur Verfügung stellen.

- Ihr Team ist mit der Entwicklung mit JavaScript und bzw. oder TypeScript vertraut.

- Ihre Anwendung muss bereits eine API für andere (interne oder öffentliche) Clients zur Verfügung stellen.

Darüber hinaus erfordern SPA-Frameworks ausführlichere Kenntnisse zur Architektur und Sicherheit. Aufgrund von regelmäßigen Aktualisierungen und neuen Frameworks erfordern sie einen größeren Änderungsumfang als herkömmliche Webanwendungen. Das Konfigurieren von automatisierten Build- und Bereitstellungsprozessen und die Verwendung von Bereitstellungsoptionen, z.B. Container, ist mit Single-Page-Webanwendungen schwieriger als mit herkömmlichen Webanwendungen.

Die Verbesserungen der Benutzerfreundlichkeit durch das SPA-Modell sollten mit diesen Eigenschaften verglichen werden.

## <a name="blazor"></a>Blazor

ASP.NET Core 3.0 führt mit Blazor ein neues Modell zur Erstellung umfassender interaktiver und zusammensetzbarer Benutzeroberflächen ein. Blazor ermöglicht Entwicklern das Erstellen von Benutzeroberflächen mit Razor auf dem Server sowie das Senden des Codes an den Browser und seine clientseitige Ausführung mithilfe der [WebAssembly](https://webassembly.org/). ASP.NET Core 3.0 befindet sich noch in der Entwicklung, in der Updateversion 3.0 dieses E-Books können Sie jedoch mehr über diese Technologie erfahren. Weitere Informationen zu Blazor finden Sie unter [Einführung in Blazor](https://blazor.net/docs/get-started.html).

## <a name="when-to-choose-traditional-web-apps"></a>Fälle für die Verwendung von herkömmlichen Webanwendungen

Im Folgenden werden die zuvor genannten Gründe für die Entscheidung für herkömmliche Webanwendungen ausführlicher erläutert.

**Ihre Anwendung verfügt über einfache, möglicherweise schreibgeschützte, clientseitige Anforderungen**

Viele Webanwendungen werden von einem Großteil ihrer Benutzer hauptsächlich schreibgeschützt verwendet. Schreibgeschützte (oder überwiegend schreibgeschützte) Anwendungen sind tendenziell viel einfacher zu verwalten, und sie bearbeiten eine große Menge von Zuständen. Eine Suchmaschine kann beispielsweise aus einem einzelnen Einstiegspunkt mit einem Textfeld und einer zweiten Seite für die Anzeige von Suchergebnissen bestehen. Anonyme Benutzer können problemlos Anforderungen ausführen, und es besteht kaum Bedarf für clientseitige Logik. Ebenso bestehen Blogs oder öffentliche Anwendungen von Inhaltsverwaltungssystemen üblicherweise aus Inhalt mit wenig clientseitigem Verhalten. Solche Anwendungen können einfach als herkömmliche serverbasierte Webanwendungen erstellt werden, die Logik auf dem Webserver anwenden und HTML für die Anzeige im Browser rendern. Die Tatsache, dass jede eindeutige Seite der Website über eine eigene URL verfügt, die mit einem Lesezeichen versehen und von Suchmaschinen indiziert werden kann (standardmäßig ohne der Webanwendung ein separates Feature hinzufügen zu müssen), ist in solchen Szenarios ein weiterer klarer Vorteil.

**Ihre Anwendung muss in Browsern ohne Unterstützung für JavaScript funktionieren**

Webanwendungen, die in Browsern mit eingeschränkter oder ohne Unterstützung von JavaScript funktionieren müssen, sollten mithilfe von Workflows für herkömmliche Webanwendungen geschrieben werden (oder zumindest dazu fähig sein, auf ein solches Verhalten ausweichen zu können). Single-Page-Webanwendungen erfordern clientseitiges JavaScript, um zu funktionieren. Wenn dies nicht verfügbar ist, sind SPAs nicht empfehlenswert.

**Ihr Team ist nicht mit Entwicklungstechniken mit JavaScript oder TypeScript vertraut**

Wenn Ihr Team sich nicht mit JavaScript oder TypeScript auskennt, aber mit der Entwicklung von serverseitigen Webanwendungen vertraut ist, ist es wahrscheinlich, dass Ihr Team eine herkömmliche Webanwendung schneller als eine SPA bereitstellen kann. Sofern es nicht das Ziel ist, das Programmieren von SPAs zu lernen, oder wenn die Benutzerfreundlichkeit einer SPA nicht erforderlich ist, sind herkömmliche Webanwendungen eine produktivere Wahl für Teams, die mit dem Erstellen von diesen vertraut sind.

## <a name="when-to-choose-spas"></a>Fälle für die Verwendung von Single-Page-Webanwendungen

Im Folgenden finden Sie eine ausführlichere Erläuterung dazu, wann Sie den Entwicklungsstil von Single-Page-Webanwendungen für Ihre Webanwendung verwenden sollten.

**Ihre Anwendung muss eine umfangreiche Benutzeroberfläche mit vielen Features zur Verfügung stellen**

SPAs können umfangreiche clientseitige Funktionalitäten unterstützen, die das erneute Laden der Seite nicht erfordern, wenn Benutzer Aktionen ausführen oder zwischen Bereichen der App navigieren. SPAs können schneller geladen werden, und individuelle Benutzeraktionen reagieren besser, da das erneute Laden von vollständigen Seiten selten ist und Daten im Hintergrund abgerufen werden. SPAs können inkrementelle Updates unterstützen, wodurch teilweise abgeschlossene Formulare oder Dokumente gespeichert werden, ohne dass der Benutzer auf eine Schaltfläche zum Senden eines Formulars klicken muss. SPAs können umfangreiches clientseitiges Verhalten (z.B. Drag & Drop) viel schneller unterstützen als herkömmliche Anwendungen. SPAs können dafür entworfen sein, in einem getrennten Modus ausgeführt zu werden, dabei werden Updates an einem clientseitigen Modell vorgenommen, die schließlich mit dem Server synchronisiert werden, sobald die Verbindung wiederhergestellt wurde. Sie sollten sich für eine Single-Page-Webanwendung entscheiden, wenn die Anforderungen Ihrer App umfangreiche Funktionalitäten beinhalten, die die Grenzen von gewöhnlichen HTML-Formularen übersteigen.

Beachten Sie, dass für SPAs regelmäßig Features implementiert werden müssen, die in herkömmlichen Webanwendungen integriert sind, z.B. das Anzeigen einer aussagekräftige URL in der Adressleiste, die den aktuellen Vorgang angibt (und Benutzern erlaubt, ein Lesezeichen zu setzen oder einen Deep-Link zu dieser URL zu erstellen, um zu einem späteren Zeitpunkt auf diese Seite zurückzukehren). SPAs sollten Benutzern ebenfalls ermöglichen, die Schaltflächen „Zurück“ und „Weiter“ des Browsers zu verwenden, ohne dabei auf überraschende Ergebnisse zu stoßen.

**Ihr Team ist mit der Entwicklung mit JavaScript und bzw. oder TypeScript vertraut**

Das Schreiben von SPAs erfordert Erfahrung mit JavaScript und bzw. oder TypeScript und clientseitigen Programmiertechniken sowie Bibliotheken. Ihr Team sollte dazu in der Lage sein, modernes JavaScript mit einem SPA-Framework wie „Angular“ zu schreiben.

> ### <a name="references--spa-frameworks"></a>Ressourcen: SPA-Frameworks
>
> - **Angular**  
>   <https://angular.io>
> - **Vergleich von JavaScript-Frameworks**  
>   <https://jsreport.io/the-ultimate-guide-to-javascript-frameworks/>

**Ihre Anwendung muss bereits eine API für andere (interne oder öffentliche) Clients zur Verfügung stellen**

Wenn Sie bereits eine Web-API für die Verwendung durch andere Clients unterstützen, erfordert es möglicherweise weniger Aufwand, eine SPA-Implementierung zu erstellen, die diese APIs nutzt, anstatt die Logik im serverseitigen Format zu reproduzieren. SPAs machen umfangreichen Gebrauch von Web-APIs, um Daten abzufragen und zu aktualisieren, während Benutzer mit der Anwendung interagieren.

## <a name="decision-table--traditional-web-or-spa"></a>Entscheidungstabelle – Herkömmliche Webanwendung oder SPA

In der folgenden Entscheidungstabelle werden einige der grundlegenden Faktoren zusammengefasst, die bei der Auswahl zwischen einer herkömmlichen Webanwendung und einer SPA beachtet werden sollten.

| **Aspekt**                                           | **Herkömmliche Webanwendung** | **Einzelseitenanwendung** |
| ---------------------------------------------------- | ----------------------- | --------------------------- |
| Erforderliche Vertrautheit des Teams mit JavaScript oder TypeScript | **Minimal**             | **Erforderlich**                |
| Unterstützt Browser ohne Skript                   | **Unterstützt**           | **Nicht unterstützt**           |
| Minimales clientseitiges Anwendungsverhalten             | **Gut geeignet**         | **Zu viel Aufwand**                |
| Umfangreiche und komplexe Anforderungen für die Benutzeroberfläche            | **Eingeschränkt**             | **Gut geeignet**             |

>[!div class="step-by-step"]
>[Zurück](modern-web-applications-characteristics.md)
>[Weiter](architectural-principles.md)
