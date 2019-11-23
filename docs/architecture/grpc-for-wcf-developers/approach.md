---
title: Vorgehensweise von GrpC bei RPC-GrpC für WCF-Entwickler
description: Vergleichen der wichtigsten Features von WCF mit GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: 1ebfd102217c9685c5ff5200386c642b2017e98f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968120"
---
# <a name="how-grpc-approaches-rpc"></a>So nähert sich gRPC RPC

Windows Communication Foundation (WCF) und GrpC sind beide Implementierungen des *Remote Prozedur Aufruf* (RPC)-Musters, das auf Aufrufe an Dienste abzielt, die auf einem anderen Computer oder in einem anderen Prozess ausgeführt werden. Sie funktionieren nahtlos so, als wären Sie nur Methodenaufrufe in der Client Anwendung. Obwohl die Ziele von WCF und GrpC identisch sind, unterscheiden sich die Details der Implementierung erheblich.

In der folgenden Tabelle wird erläutert, wie sich die wichtigsten Features von WCF auf GrpC beziehen, und wo Sie ausführlichere Erläuterungen im restlichen Buch finden können.

| Features | WCF | gRPC |
| -------- | --- | ---- |
| Ziel | Separaten Geschäfts Code von der Netzwerk Implementierung | Separaten Geschäfts Code von der Schnittstellen Definition und der Netzwerk Implementierung |
| Definieren von Diensten und Nachrichten (Kapitel 3-4)  | Dienstvertrag, Vorgangs Vertrag und Datenvertrag | Verwendet "Proto file" zum Deklarieren von Diensten und Meldungen |
| Sprache (Kapitel 3-5) | In C# oder Visual Basic geschriebene Verträge | Protokollpuffer Sprache |
| Wire-Format (Kapitel 3) | Konfigurierbar, einschließlich SOAP/XML, Plain XML, JSON, .NET Binary usw. | Binärformat für Protokollpuffer (auch wenn es möglich ist, andere Formate zu verwenden).
| Interoperabilität (Kapitel 4) | Bei Verwendung von SOAP über http | Offizieller Support: .net, Java, Python, JavaScript, C/C++, go, Rust, Ruby, SWIFT, Dart, PHP. Inoffizielle Unterstützung für andere Sprachen der Community. |
| Netzwerk (Kapitel 4) | Konfiguriert zur Laufzeit. Wechseln Sie zwischen NetTcp, http, MSMQ usw. | HTTP/2, derzeit nur über TCP mit ASP.net Core GrpC. |
| Ansatz (Kapitel 4) | Lauf Zeit Generierung von Serialisierungs-/Deserialization und Netzwerkcode in Basisklassen | Generierung von Serialisierungs-/Deserialization und Netzwerkcode in Basisklassen |
| Sicherheit (Kapitel 6) | Authentifizierung, WS-Sicherheit, Nachrichten Verschlüsselung | Anmelde Informationen, ASP.net Core Sicherheit, TLS-Netzwerk |

>[!div class="step-by-step"]
>[Zurück](grpc-overview.md)
>[Weiter](interface-definition-language.md)
