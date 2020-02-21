---
title: 'Grund für die Empfehlung von GrpC für WCF-Entwickler: GrpC für WCF-Entwickler'
description: Eine Erläuterung dazu, warum GrpC für WCF-Entwickler geeignet ist, die zu modernen Architekturen und Plattformen migrieren möchten.
ms.date: 09/02/2019
ms.openlocfilehash: fc93ca4c8f2a28dc4d3a0b0466d19c86273b40b8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503318"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>Grund für die Empfehlung von GrpC für WCF-Entwickler

Bevor wir uns ausführlich mit der Sprache und den Techniken von GrpC beschäftigen, sollte erläutert werden, warum GrpC die richtige Lösung für Windows Communication Foundation (WCF)-Entwickler ist, die zu .net Core migrieren möchten.

## <a name="similarity-to-wcf"></a>Ähnlichkeit mit WCF

Obwohl die Implementierung und der Ansatz für GrpC unterschiedlich sind, sollte das entwickeln und Nutzen von Diensten mit GrpC für WCF-Entwickler intuitiv sein. Das zugrunde liegende Ziel ist das gleiche: Sie können Code so codieren, als ob sich der Client und der Server auf derselben Plattform befinden, ohne sich Gedanken über Netzwerke machen zu müssen. 

Beide Plattformen verwenden das Prinzip der Deklaration und Implementierung einer Schnittstelle, obwohl der Prozess zum Deklarieren dieser Schnittstelle anders ist. Und wie Sie in Kapitel 5 sehen werden, werden die unterschiedlichen Arten von RPC-aufrufen, die von GrpC unterstützt werden, gut den für WCF-Dienste verfügbaren Bindungen zugeordnet.

## <a name="benefits-of-grpc"></a>Vorteile von GrpC

GrpC steht aus den folgenden Gründen vor anderen Lösungen.

### <a name="performance"></a>Leistung

Durch die Verwendung von http/2 anstelle von HTTP/1.1 entfällt die Anforderung für menschenlesbare Nachrichten, stattdessen wird das kleinere, schnellere binäre Protokoll verwendet. Dies ist effizienter für Computer, die analysiert werden können. HTTP/2 unterstützt auch das Multiplexing von Anforderungen über eine einzelne Verbindung. Diese Unterstützung ermöglicht das Senden von Antworten, sobald Sie bereit sind, ohne dass in einer Warteschlange gewartet werden muss. (In HTTP/1.1 wird dieses Problem als "Head-of-Line (Hol)-Blockierung" bezeichnet.) Bei der Verwendung von GrpC benötigen Sie weniger Ressourcen, sodass es eine gute Lösung für mobile Geräte und über langsamere Netzwerke ist.

### <a name="interoperability"></a>Interoperabilität

Es gibt GrpC-Tools und-Bibliotheken für alle wichtigen Programmiersprachen und Plattformen, einschließlich .net, Java, python C++, go,, Node. js, SWIFT, Dart, Ruby und PHP. Dank des binären Wire-Formats für Protokollpuffer und der effizienten Codegenerierung für die einzelnen Plattformen können Entwickler leistungsfähige Apps erstellen, während Sie trotzdem vollständige plattformübergreifende Unterstützung genießen.

### <a name="usability-and-productivity"></a>Nutzbarkeit und Produktivität

GrpC ist eine umfassende RPC-Lösung. Es funktioniert konsistent über mehrere Sprachen und Plattformen hinweg. Es bietet auch hervorragende Tools, bei denen ein Großteil des erforderlichen Code Bausteine automatisch generiert wird. Es wird also mehr Entwicklerzeit freigegeben, um sich auf die Geschäftslogik konzentrieren zu können.

### <a name="streaming"></a>Streaming

GrpC verfügt über ein vollständiges bidirektionales Streaming, das den vollständigen Duplex Diensten von WCF ähnliche Funktionen bietet. GrpC Streaming kann über reguläre Internetverbindungen, Lasten Ausgleichs Module und Dienst-Meshes betrieben werden.

### <a name="deadlinetimeouts-and-cancellation"></a>Stichtag/Timeouts und Abbruch

mit GrpC können Clients eine maximale Zeit für die Beendigung eines RPC angeben. Wenn die angegebene Frist überschritten wird, kann der Server den Vorgang unabhängig vom Client abbrechen. Termine und Stornierungen können über weitere GrpC-Aufrufe weitergegeben werden, um Ressourcen Verwendungs Limits zu erzwingen. Clients können Vorgänge auch beenden, wenn ein Stichtag überschritten wird, oder früher (z. b. aufgrund einer Benutzerinteraktion).

### <a name="security"></a>Sicherheit

GrpC ist implizit sicher, wenn http/2 über eine TLS-End-to-End-verschlüsselte Verbindung verwendet wird. Durch die Unterstützung der Client Zertifikat Authentifizierung (siehe [Kapitel 6](security.md)) wird die Sicherheit und Vertrauensstellung zwischen Client und Server weiter erhöht.

>[!div class="step-by-step"]
>[Zurück](network-protocols.md)
>[Weiter](protocol-buffers.md)
