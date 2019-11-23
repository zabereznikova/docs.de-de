---
title: 'WCF-Bindungen und-Transporte: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie die verschiedenen WCF-Bindungen und-Transporte mit GrpC verglichen werden.
ms.date: 09/02/2019
ms.openlocfilehash: 233e3d030bc1f4450bd5cd6a7d7770486ca9e95a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966905"
---
# <a name="wcf-bindings-and-transports"></a>WCF-Bindungen und Transporte

WCF verfügt über viele verschiedene integrierte *Bindungen* , die verschiedene Netzwerkprotokolle, Wire-Formate und andere Implementierungsdetails angeben. GrpC verfügt praktisch nur über ein Netzwerkprotokoll und ein Wire-Format (technisch gesehen *kann* das Wire-Format angepasst werden, dies geht jedoch über den Rahmen dieses Buchs hinaus). Sie werden wahrscheinlich feststellen, dass GrpC in den meisten Fällen die beste Lösung bietet. Im folgenden finden Sie eine kurze Erläuterung der relevantesten WCF-Bindungen und der Art und Weise, wie Sie mit ihrer Entsprechung in GrpC verglichen werden.

## <a name="nettcp"></a>NetTCP

Die NetTcp-Bindung von WCF ermöglicht persistente Verbindungen, kleine Nachrichten und bidirektionales Messaging, funktioniert aber nur zwischen .NET-Clients und-Servern. GrpC ermöglicht die gleiche Funktionalität, wird aber über mehrere Programmiersprachen und Plattformen hinweg unterstützt. GrpC verfügt über viele Funktionen der WCF NetTcp-Bindung, die jedoch nicht immer auf die gleiche Weise implementiert werden. In WCF wird die Verschlüsselung z. b. durch Konfiguration gesteuert und im Framework behandelt. In GrpC wird die Verschlüsselung auf Verbindungs Ebene mithilfe von http/2 über TLS erreicht.

## <a name="http"></a>HTTP

BasicHttpBinding von WCF ist in der Regel Text basiert und verwendet SOAP als Wire-Format und ist im Vergleich zur NetTcp-Bindung langsam. Es wird im Allgemeinen verwendet, um plattformübergreifende Interoperabilität oder eine Verbindung über die Internetinfrastruktur bereitzustellen. Die Entsprechung in GrpC – da Sie http/2 als zugrunde liegende Transportschicht mit dem binären protobuf-Übertragungsformat für Nachrichten verwendet – kann die Leistungsstufe "NetTcp Service Level" bieten, aber mit vollständiger plattformübergreifender Interoperabilität mit allen modernen Programmiersprachen und-Frameworks.

## <a name="named-pipes"></a>Named Pipes

WCF hat eine Named Pipes-Bindung für die Kommunikation zwischen Prozessen auf demselben physischen Computer bereitgestellt. Named Pipes werden von der ersten Version von ASP.net Core GrpC nicht unterstützt. Das Hinzufügen von Client-und Serverunterstützung für Named Pipes (und UNIX-Domänen Sockets) ist ein Ziel für eine zukünftige Version.

## <a name="msmq"></a>MSMQ

MSMQ ist eine proprietäre Windows-Nachrichten Warteschlange. Die WCF-Bindung an MSMQ ermöglicht "Fire and Forget"-Anforderungen von Clients, die zu einem beliebigen Zeitpunkt in der Zukunft verarbeitet werden können. GrpC stellt keine Funktionen zur Nachrichten Warteschlange bereit. Die beste Alternative wäre, ein Messaging System wie Azure Service Bus, rabbitmq oder Kafka direkt zu verwenden. Dies kann durch den Client implementiert werden, der Nachrichten direkt in die Warteschlange platziert, oder einen GrpC-clientstreamingdienst, der die Nachrichten in die Warteschlange

## <a name="webhttpbinding"></a>WebHttpBinding

Die WebHttpBinding (auch als WCF Rest bezeichnet) mit den Attributen "`WebGet`" und "`WebInvoke`" ermöglicht Ihnen die Entwicklung von Rest-APIs, die JSON-Code zu einem Zeitpunkt haben, als dies weniger häufig war. Wenn Sie also über eine Rest-API verfügen, die mit WCF Rest erstellt wurde, sollten Sie Sie in eine reguläre ASP.net Core MVC-Web-API-Anwendung migrieren, die eine äquivalente Funktionalität bereitstellt, anstatt Sie in GrpC zu übernehmen

>[!div class="step-by-step"]
>[Zurück](wcf-endpoints-grpc-methods.md)
>[Weiter](rpc-types.md)
