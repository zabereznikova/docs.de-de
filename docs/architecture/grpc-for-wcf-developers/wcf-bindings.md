---
title: 'WCF-Bindungen und-Transporte: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie die verschiedenen WCF-Bindungen und-Transporte mit GrpC verglichen werden.
ms.date: 12/15/2020
ms.openlocfilehash: 7a50e3e4468d86a6140066502a765818119642d4
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938506"
---
# <a name="wcf-bindings-and-transports"></a>WCF-Bindungen und Transporte

Windows Communication Foundation (WCF) verfügt über integrierte *Bindungen* , die verschiedene Netzwerkprotokolle, Wire-Formate und andere Implementierungsdetails angeben. GrpC hat praktisch nur ein Netzwerkprotokoll und ein Wire-Format. (Technisch gesehen *können* Sie das Wire-Format anpassen, aber das geht über den Rahmen dieses Buchs hinaus.) Sie werden wahrscheinlich feststellen, dass GrpC in den meisten Fällen die beste Lösung bietet.

Im folgenden finden Sie eine kurze Erläuterung der relevantesten WCF-Bindungen und der Art und Weise, wie Sie mit ihren Entsprechungen in GrpC verglichen werden.

## <a name="nettcp"></a>NetTCP

Die NetTcp-Bindung von WCF ermöglicht persistente Verbindungen, kleine Nachrichten und bidirektionales Messaging. Dies funktioniert jedoch nur zwischen .NET-Clients und-Servern. GrpC ermöglicht die gleiche Funktionalität, wird aber über mehrere Programmiersprachen und Plattformen hinweg unterstützt.

GrpC verfügt über viele Features der NetTcp-Bindung von WCF, aber Sie werden nicht immer auf die gleiche Weise implementiert. In WCF wird die Verschlüsselung z. b. durch Konfiguration gesteuert und im Framework behandelt. In GrpC wird die Verschlüsselung auf der Verbindungs Ebene über http/2 über TLS erreicht.

## <a name="http"></a>HTTP

Die WCF-Bindung namens BasicHttpBinding ist in der Regel Text basiert und verwendet SOAP als Wire-Format. Er ist langsam im Vergleich zur NetTcp-Bindung. Sie wird verwendet, um eine plattformübergreifende Interoperabilität oder eine Verbindung über die Internetinfrastruktur bereitzustellen.

Das Äquivalent in GrpC verwendet http/2 als zugrunde liegende Transportschicht mit dem binären protobuf-Wire-Format für Nachrichten. Damit kann die Leistung auf der NetTcp-Dienst Ebene und die vollständige plattformübergreifende Interoperabilität mit allen modernen Programmiersprachen und-Frameworks erzielt werden.

## <a name="named-pipes"></a>Named Pipes

WCF hat eine *Named Pipes* -Bindung für die Kommunikation zwischen Prozessen auf demselben physischen Computer bereitgestellt. Named Pipes werden von der ersten Version von ASP.net Core GrpC nicht unterstützt. Das Hinzufügen von Client-und Serverunterstützung für Named Pipes (und UNIX-Domänen Sockets) ist ein Ziel für eine zukünftige Version.

## <a name="msmq"></a>MSMQ

MSMQ ist eine proprietäre Windows-Nachrichten Warteschlange. Die WCF-Bindung an MSMQ ermöglicht "Fire and Forget"-Anforderungen von Clients, die zu einem beliebigen Zeitpunkt in der Zukunft verarbeitet werden können. GrpC stellt keine Funktionen zur Nachrichten Warteschlange bereit.

Die beste Alternative besteht darin, ein Messaging System wie Azure Service Bus, rabbitmq oder Kafka direkt zu verwenden. Sie können diese Funktion implementieren, damit der Client Nachrichten direkt in die Warteschlange eingereiht, oder einen GrpC-clientstreamingdienst, der die Nachrichten in die Warteschlange stellt

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (auch als WCF Rest bezeichnet) mit den `WebGet` Attributen und `WebInvoke` ermöglicht Ihnen die Entwicklung von Rest-APIs, die JSON zu einem Zeitpunkt sprechen, als dieses Verhalten weniger häufig war. Wenn Sie über eine Rest-API verfügen, die mit WCF Rest erstellt wurde, sollten Sie Sie in eine reguläre ASP.net Core MVC-Web-API-Anwendung migrieren Diese Migration bietet die gleiche Funktionalität wie eine Konvertierung in GrpC.

>[!div class="step-by-step"]
>[Zurück](wcf-endpoints-grpc-methods.md)
>[Weiter](rpc-types.md)
