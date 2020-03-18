---
title: Warum wir gRPC für WCF-Entwickler empfehlen - gRPC für WCF-Entwickler
description: Eine Diskussion darüber, warum gRPC eine gute Passform für WCF-Entwickler ist, die zu modernen Architekturen und Plattformen migrieren möchten.
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147645"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>Darum empfehlen wir gRPC für WCF-Entwickler

Bevor wir uns eingehend mit der Sprache und den Techniken von gRPC befassen, sollten Wir diskutieren, warum gRPC die richtige Lösung für Windows Communication Foundation (WCF)-Entwickler ist, die zu .NET Core migrieren möchten.

## <a name="similarity-to-wcf"></a>Ähnlichkeit mit WCF

Obwohl die Implementierung und der Ansatz für gRPC unterschiedlich sind, sollte die Erfahrung bei der Entwicklung und Nutzung von Diensten mit gRPC für WCF-Entwickler intuitiv sein. Das zugrunde liegende Ziel ist das gleiche: Machen Sie es möglich, zu codieren, als ob sich Client und Server auf derselben Plattform befinden, ohne sich um die Vernetzung kümmern zu müssen.

Beide Plattformen haben das Prinzip, eine Schnittstelle zu deklarieren und dann zu implementieren, obwohl der Prozess zum Deklarieren dieser Schnittstelle unterschiedlich ist. Und wie Sie in Kapitel 5 sehen werden, ordnen die verschiedenen Arten von RPC-Aufrufen, die gRPC unterstützt, den Bindungen, die für WCF-Dienste verfügbar sind, gut zuzuordnen.

## <a name="benefits-of-grpc"></a>Vorteile von gRPC

gRPC steht aus folgenden Gründen über anderen Lösungen.

### <a name="performance"></a>Leistung

Die Verwendung von HTTP/2 anstelle von HTTP/1.1 entschärre die Anforderung für lesbare Nachrichten und verwende stattdessen das kleinere, schnellere Binärprotokoll. Dies ist für Computer effizienter zu analysieren. HTTP/2 unterstützt auch Multiplexing-Anforderungen über eine einzelne Verbindung. Mit dieser Unterstützung können Antworten gesendet werden, sobald sie bereit sind, ohne in einer Warteschlange warten zu müssen. (In HTTP/1.1 wird dieses Problem als "Head-of-Line (HOL)-Blockierung" bezeichnet." Sie benötigen weniger Ressourcen, wenn Sie gRPC verwenden, was es zu einer guten Lösung für mobile Geräte und über langsamere Netzwerke macht.

### <a name="interoperability"></a>Interoperabilität

Es gibt gRPC-Tools und Bibliotheken für alle gängigen Programmiersprachen und -plattformen, einschließlich .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby und PHP. Dank des Binärdrahtformats "Protokollpuffer" und der effizienten Codegenerierung für jede Plattform können Entwickler performante Apps erstellen und gleichzeitig die volle plattformübergreifende Unterstützung genießen.

### <a name="usability-and-productivity"></a>Nutzbarkeit und Produktivität

gRPC ist eine umfassende RPC-Lösung. Es funktioniert konsistent über mehrere Sprachen und Plattformen. Es bietet auch ausgezeichnete Werkzeuge, mit einem Großteil der notwendigen Boilerplate Code automatisch generiert. Daher wird mehr Entwicklerzeit frei, um sich auf die Geschäftslogik zu konzentrieren.

### <a name="streaming"></a>Streaming

gRPC verfügt über vollständiges bidirektionales Streaming, das ähnliche Funktionen wie die Vollduplexdienste von WCF bietet. gRPC-Streaming kann über normale Internetverbindungen, Load Balancer und Servicenetze betrieben werden.

### <a name="deadlinetimeouts-and-cancellation"></a>Deadline/Timeouts und Stornierung

mit gRPC können Clients eine maximale Zeit für den Abschluss eines RPC angeben. Wenn die angegebene Frist überschritten wird, kann der Server den Vorgang unabhängig vom Client abbrechen. Fristen und Stornierungen können durch weitere gRPC-Aufrufe weitergegeben werden, um Ressourcennutzungslimits durchzusetzen. Clients können den Betrieb auch beenden, wenn eine Frist überschritten wird, oder bei Bedarf früher (z. B. aufgrund einer Benutzerinteraktion).

### <a name="security"></a>Sicherheit

gRPC ist implizit sicher, wenn es HTTP/2 über eine ENDE-zu-Ende-verschlüsselte Verbindung verwendet. Die Unterstützung für die Clientzertifikatauthentifizierung (siehe [Kapitel 6](security.md)) erhöht die Sicherheit und das Vertrauen zwischen Client und Server weiter.

>[!div class="step-by-step"]
>[VorherigeS](network-protocols.md)
>[Weiter](protocol-buffers.md)
