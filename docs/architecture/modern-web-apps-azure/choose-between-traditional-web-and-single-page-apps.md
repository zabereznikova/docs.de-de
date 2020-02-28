---
title: Auswählen zwischen herkömmlichen Webanwendungen und Single-Page-Webanwendungen (SPAs)
description: In diesem Artikel erfahren Sie, wie Sie beim Erstellen von Webanwendungen zwischen herkömmlichen Web-Apps und Single-Page-Webanwendungen (Single Page Application, SPAs) auswählen.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: d4ed76455001c1a0b8e2e2f1bb90ce8715dd0052
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450107"
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Auswählen zwischen herkömmlichen Webanwendungen und Single-Page-Webanwendungen (SPAs)

> „Atwoods Gesetz: Alle Anwendungen, die in JavaScript geschrieben werden können, werden früher oder später in JavaScript geschrieben.“  
> _\- Jeff Atwood_

Heutzutage gibt es zwei allgemeine Ansätze für das Erstellen von Webanwendungen: herkömmliche Webanwendungen, die einen Großteil der Anwendungslogik auf dem Server ausführen, und Single-Page-Webanwendungen (SPAs), die einen Großteil der Logik der Benutzeroberfläche in einem Webbrowser ausführen und mit dem Webserver überwiegend über Web-APIs kommunizieren. Ein hybrider Ansatz ist ebenfalls möglich. Am einfachsten ist das Hosten von mindestens einer umfangreichen SPA-ähnlichen Unteranwendung in einer größeren herkömmlichen Webanwendung.

Verwenden Sie herkömmliche Webanwendungen in folgenden Szenarien:

- Die clientseitigen Anforderungen Ihrer Anwendung sind einfach oder schreibgeschützt.

- Ihre Anwendung muss in Browsern ohne Unterstützung für JavaScript funktionieren.

- Ihr Team ist nicht mit Entwicklungstechniken mit JavaScript oder TypeScript vertraut.

Verwenden Sie eine Single-Page-Webanwendung in folgenden Szenarien:

- Ihre Anwendung muss eine umfangreiche Benutzeroberfläche mit vielen Features zur Verfügung stellen.

- Ihr Team ist mit der Entwicklung mit JavaScript und bzw. oder TypeScript vertraut.

- Ihre Anwendung muss bereits eine API für andere (interne oder öffentliche) Clients zur Verfügung stellen.

Darüber hinaus erfordern SPA-Frameworks ausführlichere Kenntnisse zur Architektur und Sicherheit. Aufgrund von regelmäßigen Aktualisierungen und neuen Frameworks erfordern sie einen größeren Änderungsumfang als herkömmliche Webanwendungen. Das Konfigurieren automatisierter Build- und Bereitstellungsprozesse und das Verwenden von Bereitstellungsoptionen wie Containern ist bei Single-Page-Webanwendungen schwieriger als bei herkömmlichen Webanwendungen.

Die durch den SPA-Ansatz ermöglichte Verbesserung der Benutzererfahrung muss mit diesen Aspekten abgewogen werden.

## <a name="blazor"></a>Blazor

ASP.NET Core 3.0 führt mit Blazor ein neues Modell zur Erstellung umfassender interaktiver und zusammensetzbarer Benutzeroberflächen ein. Blazor ermöglicht Entwicklern das Erstellen von Benutzeroberflächen mit Razor auf dem Server sowie das Senden des Codes an den Browser und seine clientseitige Ausführung mithilfe der [WebAssembly](https://webassembly.org/). Serverseitiges Blazor ist nun ab ASP.NET Core 3.0 verfügbar. Clientseitiges Blazor soll 2020 zur Verfügung stehen.

Blazor bietet eine neue, dritte Option, die bei der Beurteilung der Frage, ob eine rein auf dem Server gerenderte Webanwendung oder eine SPA entwickelt werden soll, zu berücksichtigen ist. Mit Blazor können Sie komplexe, SPA-ähnliche Verhaltensweisen auf Clientseite entwickeln, ohne dass eine nennenswerte JavaScript-Entwicklung erforderlich ist. Blazor-Anwendungen können APIs aufrufen, um Daten anzufordern oder serverseitige Vorgänge auszuführen.

Erwägen Sie die Entwicklung Ihrer Webanwendung mit Blazor in folgenden Fällen:

- Ihre Anwendung muss eine komplexe Benutzeroberfläche zur Verfügung stellen.

- Ihr Team ist mit der .NET-Entwicklung besser vertraut als mit der JavaScript- oder TypeScript-Entwicklung.

Weitere Informationen zu Blazor finden Sie unter [Einführung in Blazor](https://blazor.net/docs/get-started.html).

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

SPAs können umfangreiche clientseitige Funktionalitäten unterstützen, die das erneute Laden der Seite nicht erfordern, wenn Benutzer Aktionen ausführen oder zwischen Bereichen der App navigieren. SPAs können schneller geladen werden, und individuelle Benutzeraktionen reagieren besser, da das erneute Laden von vollständigen Seiten selten ist und Daten im Hintergrund abgerufen werden. SPAs können inkrementelle Updates unterstützen, wodurch teilweise abgeschlossene Formulare oder Dokumente gespeichert werden, ohne dass der Benutzer auf eine Schaltfläche zum Senden eines Formulars klicken muss. SPAs können umfangreiches clientseitiges Verhalten (z.B. Drag & Drop) viel schneller unterstützen als herkömmliche Anwendungen. SPAs können dafür entworfen sein, in einem getrennten Modus ausgeführt zu werden, dabei werden Updates an einem clientseitigen Modell vorgenommen, die schließlich mit dem Server synchronisiert werden, sobald die Verbindung wiederhergestellt wurde. Entscheiden Sie sich für eine Single-Page-Webanwendung, wenn die Anforderungen Ihrer App komplexe Funktionalität umfassen, die die Grenzen von gewöhnlichen HTML-Formularen übersteigt.

Für SPAs müssen regelmäßig Features implementiert werden, die in herkömmlichen Webanwendungen integriert sind, z. B. das Anzeigen einer aussagekräftigen URL in der Adressleiste, die den aktuellen Vorgang angibt (und Benutzern erlaubt, ein Lesezeichen zu setzen oder einen Deep-Link zu dieser URL zu erstellen, um zu einem späteren Zeitpunkt zu dieser Seite zurückzukehren). SPAs sollten Benutzern ebenfalls ermöglichen, die Schaltflächen „Zurück“ und „Weiter“ des Browsers zu verwenden, ohne dabei auf überraschende Ergebnisse zu stoßen.

**Ihr Team ist mit der Entwicklung mit JavaScript und bzw. oder TypeScript vertraut**

Das Schreiben von SPAs erfordert Erfahrung mit JavaScript und bzw. oder TypeScript und clientseitigen Programmiertechniken sowie Bibliotheken. Ihr Team sollte dazu in der Lage sein, modernes JavaScript mit einem SPA-Framework wie „Angular“ zu schreiben.

> ### <a name="references--spa-frameworks"></a>Ressourcen: SPA-Frameworks
>
> - **Angular**  
>   <https://angular.io>
> - **React**
>   <https://reactjs.org/>
> - **Vergleich von JavaScript-Frameworks**  
>   <https://jsreport.io/the-ultimate-guide-to-javascript-frameworks/>

**Ihre Anwendung muss bereits eine API für andere (interne oder öffentliche) Clients zur Verfügung stellen**

Wenn Sie bereits eine Web-API für die Verwendung durch andere Clients unterstützen, erfordert es möglicherweise weniger Aufwand, eine SPA-Implementierung zu erstellen, die diese APIs nutzt, anstatt die Logik im serverseitigen Format zu reproduzieren. SPAs machen umfangreichen Gebrauch von Web-APIs, um Daten abzufragen und zu aktualisieren, während Benutzer mit der Anwendung interagieren.

## <a name="when-to-choose-blazor"></a>In welchen Fällen sollte Blazor verwendet werden?

Im Folgenden finden Sie eine ausführlichere Erläuterung der Vorteile von Blazor für Ihre Webanwendung.

**Ihre Anwendung muss eine komplexe Benutzeroberfläche zur Verfügung stellen**

Wie JavaScript-basierte SPAs können Blazor-Anwendungen Rich-Client-Verhalten unterstützen, ohne dass Seiten neu geladen werden müssen. Diese Anwendungen reagieren besser auf Benutzer, indem sie nur die Daten (oder HTML) abrufen, die für die Reaktion auf eine bestimmte Benutzerinteraktion erforderlich sind. Bei entsprechendem Entwurf können serverseitige Blazor-Apps so konfiguriert werden, dass sie mit minimalen Änderungen als clientseitige Blazor-Apps ausgeführt werden können, sobald dieses Feature unterstützt wird.

**Ihr Team ist mit der .NET-Entwicklung besser vertraut als mit der JavaScript- oder TypeScript-Entwicklung**

Viele Entwickler sind mit .NET und Razor produktiver als mit clientseitigen Sprachen wie JavaScript oder TypeScript. Da die Serverseite der Anwendung bereits mit .NET entwickelt wird, stellt die Verwendung von Blazor sicher, dass jeder .NET-Entwickler im Team das Verhalten des Front-Ends der Anwendung verstehen und möglicherweise entwickeln kann.

## <a name="decision-table"></a>Entscheidungstabelle

In der folgenden Entscheidungstabelle werden einige der grundlegenden Faktoren zusammengefasst, die bei der Wahl zwischen einer herkömmlichen Webanwendung, einer SPA und einer Blazor-App beachtet werden sollten.

| **Aspekt**                                           | **Herkömmliche Webanwendung** | **Einzelseitenanwendung** | **Blazor-App**  |
| ---------------------------------------------------- | ----------------------- | --------------------------- | --------------- |
| Erforderliche Vertrautheit des Teams mit JavaScript oder TypeScript | **Minimal**             | **Erforderlich**                | **Minimal**     |
| Unterstützt Browser ohne Skript                   | **Unterstützt**           | **Nicht unterstützt**           | **Unterstützt**   |
| Minimales clientseitiges Anwendungsverhalten             | **Gut geeignet**         | **Zu viel Aufwand**                | **Viable**      |
| Umfangreiche und komplexe Anforderungen für die Benutzeroberfläche            | **Eingeschränkt**             | **Gut geeignet**             | **Gut geeignet** |

>[!div class="step-by-step"]
>[Zurück](modern-web-applications-characteristics.md)
>[Weiter](architectural-principles.md)
