---
title: Vorgehensweise von GrpC bei RPC-GrpC für WCF-Entwickler
description: Vergleichen der wichtigsten Features von WCF mit GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: b924d2f20b54de2d6476a0b27626d5dd7fd0986f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711481"
---
# <a name="how-grpc-approaches-rpc"></a>So nähert sich gRPC RPC

Windows Communication Foundation (WCF) und GrpC sind beide Implementierungen des *Remote Prozedur Aufruf* (RPC)-Musters. Dieses Muster zielt darauf ab, Dienste zu erstellen, die auf einem anderen Computer oder in einem anderen Prozess ausgeführt werden und nahtlos funktionieren, wie Methodenaufrufe in der Client Anwendung. Obwohl die Ziele von WCF und GrpC identisch sind, unterscheiden sich die Details der Implementierung erheblich.

In der folgenden Tabelle wird erläutert, wie sich die wichtigsten Features von WCF auf GrpC beziehen, und wo Ausführlichere Erläuterungen zu finden sind.

| Features | WCF | gRPC |
| -------- | --- | ---- |
| Ziel | Trennen Sie den Geschäfts Code von der Netzwerk Implementierung. | Trennen Sie den Geschäfts Code von der Schnittstellen Definition und der Netzwerk Implementierung. |
| Definieren von Diensten und Nachrichten (Kapitel 3-4)  | Dienstvertrag, Vorgangs Vertrag und Datenvertrag. | Verwendet die Proto-Datei, um Dienste und Meldungen zu deklarieren. |
| Sprache (Kapitel 3-5) | Verträge, die C# in oder Visual Basic geschrieben wurden. | Sprache des Protokoll Puffers. |
| Wire-Format (Kapitel 3) | Konfigurierbar, einschließlich SOAP/XML, Plain XML, JSON und .NET Binary. | Binärformat für Protokollpuffer (auch wenn es möglich ist, andere Formate zu verwenden).
| Interoperabilität (Kapitel 4) | Wenn SOAP über HTTP verwendet wird. | Offizieller Support: .net, Java, Python, JavaScript, C/C++, go, Rust, Ruby, SWIFT, Dart, PHP. Inoffizielle Unterstützung für andere Sprachen der Community. |
| Netzwerk (Kapitel 4) | Konfiguriert zur Laufzeit. Wechseln Sie zwischen NetTcp, http und MSMQ. | HTTP/2, derzeit nur über TCP mit ASP.net Core GrpC. |
| Ansatz (Kapitel 4) | Lauf Zeit Generierung von Serialisierung, Deserialisierung und Netzwerkcode in Basisklassen. | Erstellungszeit Generierung von Serialisierung, Deserialisierung und Netzwerkcode in Basisklassen. |
| Sicherheit (Kapitel 6) | Authentifizierung, WS-Sicherheit, Nachrichten Verschlüsselung. | Anmelde Informationen, ASP.net Core Sicherheit, TLS-Netzwerke. |

>[!div class="step-by-step"]
>[Zurück](grpc-overview.md)
>[Weiter](interface-definition-language.md)
