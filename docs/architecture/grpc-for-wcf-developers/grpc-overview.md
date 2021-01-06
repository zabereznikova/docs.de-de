---
title: Übersicht über GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie mehr über die Prinzipien, die für die Entwicklung von GrpC entwickelt wurden.
ms.date: 12/15/2020
ms.openlocfilehash: 99e1bdb1f49469f444044027c3ac5d927f9cab13
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938402"
---
# <a name="grpc-overview"></a>Übersicht über GrpC

Nachdem wir uns die Windows Communication Foundation (WCF) und GrpC im letzten Kapitel angesehen haben, werden in diesem Kapitel einige der wichtigsten Features von GrpC und deren Vergleich mit WCF berücksichtigt.

ASP.net Core 3,0 ist die erste Version von ASP.net, die GrpC System intern als erstklassigen Bürger unterstützt, wobei Microsoft-Teams zur offiziellen .NET-Implementierung von GrpC beitragen. Es wird empfohlen, verteilte Anwendungen mit .net zu entwickeln, die mit allen anderen wichtigen Programmiersprachen und-Frameworks zusammenarbeiten können.

## <a name="key-principles"></a>Wichtige Prinzipien

Wie in Kapitel 1 erläutert, wollte Google die Einführung von http/2 verwenden, um Stubby, eine interne, allgemeine RPC-Infrastruktur, zu ersetzen. GrpC, basierend auf dem Stubby, kann jetzt die Standardisierung nutzen und seine Anwendbarkeit auf Mobile Computing, die Cloud und die Internet der Dinge ausweiten.

Um diese Standardisierung zu erreichen, hat die [Cloud Native Computing Foundation (cncf)](https://www.cncf.io/) eine Reihe von Prinzipien eingerichtet, die GrpC steuern würden. In der folgenden Liste sind die relevantesten Themen aufgeführt, die sich hauptsächlich mit der Maximierung der Barrierefreiheit und Benutzerfreundlichkeit beschäftigen:

- **Free und Open** – alle Artefakte sollten Open Source-Elemente mit Lizenzierung sein, die Entwicklern nicht die Übernahme von GrpC einschränkt.
- **Abdeckung und Einfachheit** – GrpC sollte auf allen gängigen Plattformen verfügbar und einfach genug sein, um auf jeder beliebigen Plattform zu erstellen.
- **Interoperabilität und Reichweite** – das Verwenden von GrpC in jedem Netzwerk, unabhängig von Bandbreite oder Latenz, mithilfe von allgemein verfügbaren Netzwerkstandards.
- **Universell und Leistungs** fähig – das Framework sollte von so vielen Anwendungsfällen wie möglich genutzt werden können, ohne die Leistung zu beeinträchtigen.
- **Streaming** – das Protokoll sollte Streamingsemantik für große Datasets oder asynchrones Messaging bereitstellen.
- **Metadatenaustausch** – das Protokoll ermöglicht, dass nicht-Geschäftsdaten, z. b. Authentifizierungs Token, getrennt von tatsächlichen Geschäftsdaten behandelt werden.
- **Standardisierte Statuscodes** – die Varianz der Fehlercodes sollte verringert werden, um die Fehler Behandlungsentscheidungen zu verdeutlichen. Wenn zusätzliche, umfangreichere Fehlerbehandlung erforderlich ist, sollte ein Mechanismus für die Verwaltung des Verhaltens innerhalb des Metadatenaustauschs bereitgestellt werden.

>[!div class="step-by-step"]
>[Zurück](introduction.md)
>[Weiter](approach.md)
