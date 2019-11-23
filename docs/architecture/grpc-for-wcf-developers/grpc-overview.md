---
title: Übersicht über GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie mehr über die Prinzipien, die für die Entwicklung von GrpC entwickelt wurden.
ms.date: 09/02/2019
ms.openlocfilehash: a92fe7ca2f8e17126025362fcc3c190024ebf7d3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967767"
---
# <a name="grpc-overview"></a>Übersicht über GrpC

Nachdem Sie sich im letzten Kapitel mit der Verwendung von WCF und GrpC beschäftigt haben, werden in diesem Kapitel einige der wichtigsten Features von GrpC und Ihre Vergleiche mit WCF berücksichtigt.

ASP.net Core 3,0 ist die erste Version von ASP.net, die GrpC System intern als erstklassigen Bürger unterstützt, wobei Microsoft-Teams zur offiziellen .NET-Implementierung von GrpC beitragen. Es wird empfohlen, die beste Vorgehensweise zum entwickeln verteilter Anwendungen mit .net zu verwenden, die mit allen anderen wichtigen Programmiersprachen und-Frameworks zusammenarbeiten kann.

## <a name="key-principles"></a>Wichtige Prinzipien

Wie in Kapitel 1 erläutert, wollte Google die Einführung von http/2 verwenden, um Stubby, eine interne, allgemeine RPC-Infrastruktur, zu ersetzen. GrpC, basierend auf dem Stubby, könnte nun die Standardisierung nutzen und seine Anwendbarkeit auf Mobile Computing, die Cloud und die Internet der Dinge ausweiten.

Um dies zu erreichen, hat die [Cloud Native Computing Foundation (cncf)](https://www.cncf.io/) eine Reihe von Prinzipien geschaffen, die GrpC steuern würden. In der folgenden Liste werden die relevantesten Themen angezeigt, die sich hauptsächlich auf die Maximierung der Barrierefreiheit und die Benutzerfreundlichkeit beziehen:

- **Kostenlos und offen** – alle Artefakte sollten eine Open Source-Version mit Lizenzierung sein, die Entwicklern nicht die Übernahme von GrpC einschränkt.
- **Abdeckung und Einfachheit** – GrpC sollte auf allen gängigen Plattformen verfügbar und einfach genug sein, um auf jeder beliebigen Plattform zu erstellen.
- **Interoperabilität und Reichweite** – es sollte möglich sein, GrpC in jedem Netzwerk zu verwenden, unabhängig von Bandbreite oder Latenz, mithilfe von allgemein verfügbaren Netzwerkstandards.
- **Universell und Leistungs** fähig – das Framework sollte von so vielen Anwendungsfällen wie möglich genutzt werden können, ohne die Leistung zu beeinträchtigen.
- **Streaming** – das Protokoll sollte Streamingsemantik für große Datenmengen oder asynchrones Messaging bereitstellen.
- **Metadatenaustausch** – das Protokoll ermöglicht, dass nicht-Geschäftsdaten, z. b. Authentifizierungs Token, getrennt von tatsächlichen Geschäftsdaten behandelt werden.
- **Standardisierte Statuscodes** – die Varianz von Fehlercodes sollte verringert werden, um die Entscheidungen zur Fehlerbehandlung zu verdeutlichen, und wenn zusätzliche Fehlerbehandlung erforderlich ist, sollte ein Mechanismus für die Verwaltung innerhalb des Metadatenaustauschs bereitgestellt werden.

>[!div class="step-by-step"]
>[Zurück](introduction.md)
>[Weiter](approach.md)
