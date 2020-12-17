---
title: Auswählen zwischen herkömmlichen Webanwendungen und Single-Page-Webanwendungen (SPAs)
description: In diesem Artikel erfahren Sie, wie Sie beim Erstellen von Webanwendungen zwischen herkömmlichen Web-Apps und Single-Page-Webanwendungen (Single Page Application, SPAs) auswählen.
author: ardalis
ms.author: wiwagn
no-loc:
- Blazor
- WebAssembly
ms.date: 12/01/2020
ms.openlocfilehash: c29e58fb4c748d6025b7c2fbe62a54a85cc71fba
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851652"
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

- Ihr Team ist mit der Entwicklung mit JavaScript, TypeScript oder Blazor WebAssembly vertraut

- Ihre Anwendung muss bereits eine API für andere (interne oder öffentliche) Clients zur Verfügung stellen.

Darüber hinaus erfordern SPA-Frameworks ausführlichere Kenntnisse zur Architektur und Sicherheit. Aufgrund von regelmäßigen Aktualisierungen und neuen Frameworks erfordern sie einen größeren Änderungsumfang als herkömmliche Webanwendungen. Das Konfigurieren automatisierter Build- und Bereitstellungsprozesse und das Verwenden von Bereitstellungsoptionen wie Containern ist bei Single-Page-Webanwendungen schwieriger als bei herkömmlichen Webanwendungen.

Die durch den SPA-Ansatz ermöglichte Verbesserung der Benutzererfahrung muss mit diesen Aspekten abgewogen werden.

## Blazor

ASP.NET Core enthält ein neues Modell namens Blazor zur Erstellung umfassender, interaktiver und zusammensetzbarer Benutzeroberflächen. Blazor auf Serverseite ermöglicht Entwicklern, eine Benutzeroberfläche mit C# und Razor auf dem Server zu erstellen. Die Benutzeroberfläche kann über eine ständige SignalR-Verbindung in Echtzeit interaktiv mit dem Browser verbunden werden. Blazor WebAssembly führt eine weitere Option für Blazor-Apps ein, die es ermöglicht, sie mit WebAssembly im Browser auszuführen. Da es sich um echten .NET-Code handelt, der in WebAssembly ausgeführt wird, können Sie Code und Bibliotheken aus serverseitigen Teilen Ihrer Anwendung wiederverwenden.

Blazor bietet eine neue, dritte Option, die bei der Beurteilung der Frage, ob eine rein auf dem Server gerenderte Webanwendung oder eine SPA entwickelt werden soll, zu berücksichtigen ist. Mit Blazor können Sie komplexe, SPA-ähnliche clientseitige Verhaltensweisen entwickeln, ohne dass eine nennenswerte JavaScript-Entwicklung erforderlich ist. Blazor-Anwendungen können APIs aufrufen, um Daten anzufordern oder serverseitige Vorgänge auszuführen. Sie können bei Bedarf mit JavaScript interagieren, um die Vorteile von JavaScript-Bibliotheken und -Frameworks zu nutzen.

Erwägen Sie die Entwicklung Ihrer Webanwendung mit Blazor in folgenden Fällen:

- Ihre Anwendung muss eine komplexe Benutzeroberfläche zur Verfügung stellen.

- Ihr Team ist mit der .NET-Entwicklung besser vertraut als mit der JavaScript- oder TypeScript-Entwicklung.

Wenn Sie über eine vorhandene Web Forms-Anwendung verfügen, die Sie zu .NET Core oder zur neuesten Version von .NET migrieren möchten, sollten Sie das kostenlose E-Book [Blazor für ASP.NET Web Forms-Entwickler](../blazor-for-web-forms-developers/index.md) lesen, um herauszufinden, ob eine Migration der Anwendung zu Blazor sinnvoll ist.

Weitere Informationen zu Blazorfinden Sie unter [Erste Schritte mit Blazor](https://blazor.net/docs/get-started.html).

## <a name="when-to-choose-traditional-web-apps"></a>Fälle für die Verwendung von herkömmlichen Webanwendungen

Im folgenden Abschnitt werden die zuvor genannten Gründe für die Entscheidung zur Auswahl herkömmlicher Webanwendungen ausführlicher erläutert.

**Ihre Anwendung verfügt über einfache, möglicherweise schreibgeschützte, clientseitige Anforderungen**

Viele Webanwendungen werden von einem Großteil ihrer Benutzer hauptsächlich schreibgeschützt verwendet. Schreibgeschützte (oder überwiegend schreibgeschützte) Anwendungen sind tendenziell viel einfacher als Anwendungen, die eine große Menge von Zuständen verwalten und bearbeiten. Eine Suchmaschine kann beispielsweise aus einem einzelnen Einstiegspunkt mit einem Textfeld und einer zweiten Seite für die Anzeige von Suchergebnissen bestehen. Anonyme Benutzer können problemlos Anforderungen ausführen, und es besteht kaum Bedarf für clientseitige Logik. Ebenso bestehen Blogs oder öffentliche Anwendungen von Inhaltsverwaltungssystemen üblicherweise aus Inhalt mit wenig clientseitigem Verhalten. Solche Anwendungen können einfach als herkömmliche serverbasierte Webanwendungen erstellt werden, die Logik auf dem Webserver anwenden und HTML für die Anzeige im Browser rendern. Die Tatsache, dass jede eindeutige Seite der Website über eine eigene URL verfügt, die mit einem Lesezeichen versehen und von Suchmaschinen indiziert werden kann (standardmäßig ohne der Webanwendung ein separates Feature hinzufügen zu müssen), ist in solchen Szenarios ein weiterer klarer Vorteil.

**Ihre Anwendung muss in Browsern ohne Unterstützung für JavaScript funktionieren**

Webanwendungen, die in Browsern mit eingeschränkter oder ohne Unterstützung von JavaScript funktionieren müssen, sollten mithilfe von Workflows für herkömmliche Webanwendungen geschrieben werden (oder zumindest dazu fähig sein, auf ein solches Verhalten ausweichen zu können). Single-Page-Webanwendungen erfordern clientseitiges JavaScript, um zu funktionieren. Wenn dies nicht verfügbar ist, sind SPAs nicht empfehlenswert.

**Ihr Team ist nicht mit Entwicklungstechniken mit JavaScript oder TypeScript vertraut**

Wenn Ihr Team sich nicht mit JavaScript oder TypeScript auskennt, aber mit der Entwicklung von serverseitigen Webanwendungen vertraut ist, ist es wahrscheinlich, dass Ihr Team eine herkömmliche Webanwendung schneller als eine SPA bereitstellen kann. Sofern es nicht das Ziel ist, das Programmieren von SPAs zu lernen, oder wenn die Benutzerfreundlichkeit einer SPA nicht erforderlich ist, sind herkömmliche Webanwendungen eine produktivere Wahl für Teams, die mit dem Erstellen von diesen vertraut sind.

## <a name="when-to-choose-spas"></a>Fälle für die Verwendung von Single-Page-Webanwendungen

Im folgenden Abschnitt finden Sie eine ausführlichere Erläuterung dazu, wann Sie den Entwicklungsstil von Single-Page-Webanwendungen für Ihre Webanwendung verwenden sollten.

**Ihre Anwendung muss eine umfangreiche Benutzeroberfläche mit vielen Features zur Verfügung stellen**

SPAs können umfangreiche clientseitige Funktionalitäten unterstützen, die das erneute Laden der Seite nicht erfordern, wenn Benutzer Aktionen ausführen oder zwischen Bereichen der App navigieren. SPAs können schneller geladen werden, und individuelle Benutzeraktionen reagieren besser, da das erneute Laden von vollständigen Seiten selten ist und Daten im Hintergrund abgerufen werden. SPAs können inkrementelle Updates unterstützen, wodurch teilweise abgeschlossene Formulare oder Dokumente gespeichert werden, ohne dass der Benutzer auf eine Schaltfläche zum Senden eines Formulars klicken muss. SPAs können umfangreiches clientseitiges Verhalten (z.B. Drag & Drop) viel schneller unterstützen als herkömmliche Anwendungen. SPAs können dafür entworfen sein, in einem getrennten Modus ausgeführt zu werden, dabei werden Updates an einem clientseitigen Modell vorgenommen, die schließlich mit dem Server synchronisiert werden, sobald die Verbindung wiederhergestellt wurde. Entscheiden Sie sich für eine Single-Page-Webanwendung, wenn die Anforderungen Ihrer App komplexe Funktionalität umfassen, die die Grenzen von gewöhnlichen HTML-Formularen übersteigt.

Für SPAs müssen regelmäßig Features implementiert werden, die in herkömmlichen Webanwendungen integriert sind, z. B. das Anzeigen einer aussagekräftigen URL in der Adressleiste, die den aktuellen Vorgang angibt (und Benutzern erlaubt, ein Lesezeichen zu setzen oder einen Deep-Link zu dieser URL zu erstellen, um zu einem späteren Zeitpunkt zurückzukehren). SPAs sollten Benutzern ebenfalls ermöglichen, die Schaltflächen „Zurück“ und „Weiter“ des Browsers zu verwenden, ohne dabei auf überraschende Ergebnisse zu stoßen.

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

## <a name="when-to-choose-no-locblazor"></a>Fälle für die Verwendung von Blazor

Im folgenden Abschnitt finden Sie eine ausführlichere Erläuterung der Vorteile von Blazor für Ihre Webanwendung.

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
