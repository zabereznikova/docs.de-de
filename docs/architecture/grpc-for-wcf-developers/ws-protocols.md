---
title: WS-*-Protokolle-GrpC für WCF-Entwickler
description: Überprüfen der von WCF unterstützten WS-*-Protokolle und Alternativen, die mit GrpC verfügbar sind
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 4e7b80df182fb69cc51e14738e59ad87efaf5dd2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841312"
---
# <a name="ws--protocols"></a>WS-\* Protokolle

Einer der wirklichen Vorteile bei der Arbeit mit Windows Communication Foundation (WCF) war, dass viele der vorhandenen _WS-\*_ Standardprotokolle unterstützt wurden. In diesem Abschnitt wird kurz erläutert, wie GrpC dieselben WS-\* Protokolle verwaltet und erläutert, welche Optionen verfügbar sind, wenn es keine Alternative gibt.

## <a name="metadata-exchange---ws-policy-ws-discovery-and-so-on"></a>Metadatenaustausch-WS-Policy, WS-Discovery usw.

SOAP-Dienste machen Web Services Description Language Schema Dokumente (WSDL) mit Informationen wie Datenformaten, Vorgängen oder Kommunikationsoptionen verfügbar. Dieses Schema kann verwendet werden, um den Client Code zu generieren.

GrpC funktioniert am besten, wenn Server und Clients aus denselben `.proto` Dateien generiert werden, aber eine optionale Erweiterung zur Server Reflektion bietet eine Möglichkeit, dynamische Informationen von einem laufenden Server verfügbar zu machen. Weitere Informationen finden Sie im nuget-Paket " [GrpC. Reflection](https://nuget.org/packages/Grpc.Reflection) " und im Artikel zur [GrpC C# -Server Reflektion](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) .

Das WS-Discovery-Protokoll wird verwendet, um Dienste in einem lokalen Netzwerk zu suchen. GrpC-Dienste befinden sich in der Regel mithilfe von DNS oder einer Dienst Registrierung, wie z. b. Konsul oder Zookeeper.

## <a name="security--ws-security-ws-federation-xml-encryption-and-so-on"></a>Sicherheit – WS-Sicherheit, WS-Verbund, XML-Verschlüsselung usw.

Sicherheit, Authentifizierung und Autorisierung werden in [Kapitel 6](security.md)ausführlicher behandelt. Es ist jedoch erwähnenswert, dass GrpC im Gegensatz zu WCF WS-Sicherheit, WS-Verbund oder XML-Verschlüsselung nicht unterstützt. Auch hier bietet GrpC hervorragende Sicherheitseinstellungen. der gesamte GrpC-Netzwerk Datenverkehr wird bei Verwendung von http/2 über TLS automatisch verschlüsselt, und für die gegenseitige Client-/Serverauthentifizierung können X509-Zertifikate verwendet werden.

## <a name="ws-reliablemessaging"></a>WS-ReliableMessaging

GrpC bietet kein Äquivalent zu WS-ReliableMessaging. Wiederholungs Semantik sollte im Code behandelt werden, möglicherweise mit einer Bibliothek wie [Polly](https://github.com/App-vNext/Polly). Wenn Sie in Kubernetes oder ähnlichen Orchestrierungs Umgebungen ausgeführt werden, können [Dienst-Netzen](service-mesh.md) auch zum Bereitstellen von zuverlässigem Messaging zwischen Diensten beitragen.

## <a name="ws-transaction-ws-coordination"></a>WS-Transaction, WS-Koordination

Die WCF-Implementierung verteilter Transaktionen verwendet Windows ' Microsoft Distributed Transaction Coordinator oder MSDTC. Sie funktioniert mit Ressourcen-Managern, die diese speziell unterstützen, wie SQL Server, MSMQ oder Windows-Dateisystemen. In der modernen Welt der weltweiten Umgebungen gibt es in der Praxis noch keine Entsprechung. Eine Erläuterung der Transaktionen finden Sie in [Anhang a](appendix.md).

>[!div class="step-by-step"]
>[Zurück](error-handling.md)
>[Weiter](migrate-wcf-to-grpc.md)
