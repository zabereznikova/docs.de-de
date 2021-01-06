---
title: WS-*-Protokolle-GrpC für WCF-Entwickler
description: Überprüfen der von WCF unterstützten WS-*-Protokolle und Alternativen, die mit GrpC verfügbar sind
author: markrendle
ms.date: 12/15/2020
ms.openlocfilehash: d6fffdd5153c799c78ad949a3b16fa72e9612e43
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938480"
---
# <a name="ws--protocols"></a>WS- \* Protokolle

Einer der wirklichen Vorteile bei der Arbeit mit Windows Communication Foundation (WCF) war, dass viele der vorhandenen _WS- \*_ Standard-Protokolle unterstützt wurden. In diesem Abschnitt wird kurz erläutert, wie GrpC dieselben WS- \* Protokolle verwaltet und erläutert, welche Optionen verfügbar sind, wenn es keine Alternative gibt.

## <a name="metadata-exchange-ws-policy-ws-discovery-and-so-on"></a>Metadatenaustausch: WS-Policy, WS-Discovery usw.

SOAP-Dienste machen Web Services Description Language Schema Dokumente (WSDL) mit Informationen wie Datenformaten, Vorgängen oder Kommunikationsoptionen verfügbar. Sie können dieses Schema verwenden, um den Client Code zu generieren.

GrpC funktioniert am besten, wenn Server und Clients aus denselben Dateien generiert werden `.proto` , aber eine optionale Erweiterung zur Server Reflektion bietet eine Möglichkeit, dynamische Informationen von einem laufenden Server verfügbar zu machen. Weitere Informationen finden Sie im nuget-Paket " [GrpC. Reflection](https://nuget.org/packages/Grpc.Reflection) " und im Artikel zum [GrpC c#-Server Reflektion](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) .

Das WS-Discovery-Protokoll wird verwendet, um Dienste in einem lokalen Netzwerk zu suchen. GrpC-Dienste befinden sich über DNS oder eine Dienst Registrierung, wie z. b. Konsul oder Zookeeper.

## <a name="security-ws-security-ws-federation-xml-encryption-and-so-on"></a>Sicherheit: WS-Sicherheit, WS-Verbund, XML-Verschlüsselung usw.

Sicherheit, Authentifizierung und Autorisierung werden in [Kapitel 6](security.md)ausführlicher behandelt. Es ist jedoch erwähnenswert, dass GrpC im Gegensatz zu WCF WS-Sicherheit, WS-Verbund oder XML-Verschlüsselung nicht unterstützt. Auch hier bietet GrpC eine ausgezeichnete Sicherheit. Bei Verwendung von http/2 über TLS wird der gesamte Netzwerk Datenverkehr von GrpC automatisch verschlüsselt. Sie können X509-Zertifikate für die gegenseitige Client/Server-Authentifizierung verwenden.

## <a name="ws-reliablemessaging"></a>WS-ReliableMessaging

GrpC bietet kein Äquivalent zu WS-ReliableMessaging. Wiederholungs Semantik sollte im Code behandelt werden, möglicherweise mit einer Bibliothek wie [Polly](https://github.com/App-vNext/Polly). Wenn Sie in Kubernetes oder ähnlichen Orchestrierungs Umgebungen ausführen, können Sie auch [Dienst-Netzen](service-mesh.md) bei der Bereitstellung von zuverlässigem Messaging zwischen Diensten unterstützen.

## <a name="ws-transaction-ws-coordination"></a>WS-Transaction, WS-Coordination

Die WCF-Implementierung verteilter Transaktionen verwendet Microsoft Distributed Transaction Coordinator (MSDTC). Sie funktioniert mit Ressourcen-Managern, die diese speziell unterstützen, wie SQL Server, MSMQ oder Windows-Dateisystemen. Es gibt noch keine Entsprechung in der modernen Welt der weltweiten Umgebungen, was wiederum auf die größere Anzahl von verwendeten Technologien zurückzuführen ist. Eine Erläuterung der Transaktionen finden Sie in [Anhang a](appendix.md).

>[!div class="step-by-step"]
>[Zurück](error-handling.md)
>[Weiter](migrate-wcf-to-grpc.md)
