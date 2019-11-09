---
title: 'Warum GrpC für WCF-Entwickler empfohlen wird: GrpC für WCF-Entwickler'
description: Eine Erläuterung dazu, warum GrpC für WCF-Entwickler geeignet ist, die zu modernen Architekturen und Plattformen migrieren möchten.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: f96e9a059dc9f12a13c9eb5bb7184ee75d602458
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841306"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a>Gründe für die Empfehlung von gRPC für WCF-Entwickler

Bevor wir uns eingehend mit der Sprache und den Techniken von GrpC beschäftigen, sollte erläutert werden, warum GrpC die richtige Lösung für WCF-Entwickler ist, die zu .net Core migrieren möchten, wenn es Alternativen gibt.

## <a name="similarity-to-wcf"></a>Ähnlichkeit mit WCF

Obwohl die Implementierung und der Ansatz unterschiedlich sind, sollte die tatsächliche Umgebung für die Entwicklung und Nutzung von Diensten mit GrpC für WCF-Entwickler sehr intuitiv sein. Das zugrunde liegende Ziel, den Code so zu gestalten, als ob sich der Client und der Server auf derselben Plattform befinden, ohne sich Gedanken über Netzwerke machen zu müssen, ist gleich. Beide Plattformen verwenden das Prinzip der Deklaration und Implementierung einer Schnittstelle, obwohl der Prozess zum Deklarieren dieser Schnittstelle anders ist. Und wie Sie in Kapitel 5 sehen werden, sind die unterschiedlichen Arten von RPC-aufrufen, die von GrpC unterstützt werden, sehr gut für die verschiedenen für WCF-Dienste verfügbaren Bindungen verfügbar.

## <a name="benefits-of-grpc"></a>Vorteile von GrpC

Weitere Gründe, warum GrpC über anderen Lösungen steht, sind:

### <a name="performance"></a>Leistung

Wie bereits erläutert, wird durch die Verwendung von http/2 anstelle von HTTP/1.1 die Anforderung für menschenlesbare Nachrichten entfernt und stattdessen das kleinere schnellere binäre Protokoll verwendet. Dies ist effizienter für Computer, die analysiert werden können. HTTP/2 unterstützt auch das Multiplexing von Anforderungen über eine einzelne Verbindung, sodass Antworten gesendet werden können, sobald Sie bereit sind, ohne dass in einer Warteschlange gewartet werden muss (ein Problem in HTTP/1.1, das als "Head-of-Line (Hol)-Blockierung" bezeichnet wird). Bei der Verwendung von GrpC werden weniger Ressourcen benötigt. Dies ist eine gute Lösung für mobile Geräte und über langsamere Netzwerke.

### <a name="interoperability"></a>Interoperabilität

Es gibt GrpC-Tools und-Bibliotheken für alle wichtigen Programmiersprachen und Plattformen, einschließlich .net, Java, python C++, go,, Node. js, SWIFT, Dart, Ruby und PHP. Dank des binären Wire-Formats für Protokollpuffer und der effizienten Codegenerierung für die einzelnen Plattformen können Entwickler leistungsfähige Apps erstellen, während Sie trotzdem vollständige plattformübergreifende Unterstützung genießen.

### <a name="usability-and-productivity"></a>Nutzbarkeit und Produktivität

GrpC ist eine umfassende RPC-Lösung. Es funktioniert konsistent über mehrere Sprachen und Plattformen hinweg und bietet hervorragende Tools, bei denen ein Großteil des benötigten Code Bausteine automatisch generiert wird, sodass mehr Entwicklerzeit für den Schwerpunkt auf Geschäftslogik freigegeben wird.

### <a name="streaming"></a>Streaming

GrpC verfügt über ein vollständiges bidirektionales Streaming, das den vollständigen Duplex Diensten von WCF eine sehr ähnliche Funktionalität bietet. GrpC Streaming kann über reguläre Internetverbindungen, Lasten Ausgleichs Module und Dienst-Meshes betrieben werden.

### <a name="deadlinetimeouts-and-cancellation"></a>Stichtag/Timeouts und Abbruch

mit GrpC können Clients eine maximale Zeit für den Abschluss eines RPC angeben. Wenn die angegebene Frist überschritten wird, kann der Server den Vorgang unabhängig vom Client abbrechen. Termine und Stornierungen können über weitere GrpC-Aufrufe weitergegeben werden, um Ressourcen Verwendungs Limits zu erzwingen. Clients können auch Vorgänge abbrechen, wenn ein Stichtag überschritten wird, oder früher, wenn erforderlich (z. b. aufgrund einer Benutzerinteraktion).

### <a name="security"></a>Sicherheit

GrpC ist implizit sicher, wenn http/2 über eine TLS-End-to-End-verschlüsselte Verbindung verwendet wird. Durch die Unterstützung der Client Zertifikat Authentifizierung (siehe Kapitel 6) wird die Sicherheit und Vertrauensstellung zwischen Client und Server weiter erhöht.

>[!div class="step-by-step"]
>[Zurück](network-protocols.md)
>[Weiter](protocol-buffers.md)
