---
title: WCF-Bindungen und -Transporte - gRPC für WCF-Entwickler
description: Erfahren Sie, wie sich die verschiedenen WCF-Bindungen und -Transporte mit gRPC vergleichen.
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147723"
---
# <a name="wcf-bindings-and-transports"></a>WCF-Bindungen und Transporte

Windows Communication Foundation (WCF) verfügt über integrierte Bindungen, die verschiedene Netzwerkprotokolle, Drahtformate und andere *Implementierungsdetails* angeben. gRPC hat effektiv nur ein Netzwerkprotokoll und ein Drahtformat. (Technisch *können* Sie das Drahtformat anpassen, aber das geht über den Rahmen dieses Buches hinaus.) Sie werden wahrscheinlich feststellen, dass gRPC in den meisten Fällen die beste Lösung bietet.

Was folgt, ist eine kurze Diskussion über die relevantesten WCF-Bindungen und wie sie mit ihren Äquivalenten in gRPC verglichen werden.

## <a name="nettcp"></a>Nettcp

Die NetTCP-Bindung von WCF ermöglicht dauerhafte Verbindungen, kleine Nachrichten und zweiwegige Nachrichten. Es funktioniert jedoch nur zwischen .NET-Clients und Servern. gRPC ermöglicht die gleiche Funktionalität, wird aber über mehrere Programmiersprachen und Plattformen hinweg unterstützt.

gRPC verfügt über viele Funktionen der WCF-NetTCP-Bindung, die jedoch nicht immer auf die gleiche Weise implementiert werden. In WCF wird die Verschlüsselung beispielsweise über die Konfiguration gesteuert und im Framework behandelt. In gRPC wird die Verschlüsselung auf Verbindungsebene über HTTP/2 über TLS erreicht.

## <a name="http"></a>HTTP

Die WCF-Bindung namens BasicHttpBinding ist in der Regel textbasiert und verwendet SOAP als Drahtformat. Es ist langsam im Vergleich zur NetTCP-Bindung. Es wird im Allgemeinen verwendet, um plattformübergreifende Interoperabilität oder Verbindung über Internet-Infrastruktur bereitzustellen.

Das Äquivalent in gRPC verwendet HTTP/2 als zugrunde liegende Transportschicht mit dem binären Protobuf-Drahtformat für Nachrichten. So kann es Leistung auf NetTCP-Service-Ebene und vollständige plattformübergreifende Interoperabilität mit allen modernen Programmiersprachen und Frameworks bieten.

## <a name="named-pipes"></a>Named Pipes

WCF stellte eine *Named Pipes-Bindung* für die Kommunikation zwischen Prozessen auf derselben physischen Maschine zur Verfügung. Die erste Version von ASP.NET Core gRPC unterstützt keine Named Pipes. Das Hinzufügen von Client- und Serverunterstützung für Named Pipes (und Unix-Domänensockets) ist ein Ziel für eine zukünftige Version.

## <a name="msmq"></a>MSMQ

MSMQ ist eine proprietäre Windows-Nachrichtenwarteschlange. Die Bindung von WCF an MSMQ ermöglicht "Fire and Forget"-Anforderungen von Clients, die jederzeit in der Zukunft verarbeitet werden können. gRPC bietet keine Nachrichtenwarteschlangenfunktionalität.

Die beste Alternative besteht darin, ein Messagingsystem wie Azure Service Bus, RabbitMQ oder Kafka direkt zu verwenden. Sie können dies implementieren, indem der Client Nachrichten direkt in die Warteschlange platziert, oder mit einem gRPC-Client-Streamingdienst, der die Nachrichten in die Warteschlange stellt.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (auch bekannt als WCF `WebGet` `WebInvoke` REST) mit den Attributen ermöglichte es Ihnen, RESTful-APIs zu entwickeln, die JSON zu einem Zeitpunkt sprechen konnten, zu dem dies weniger häufig war. Wenn Sie eine RESTful-API mit WCF REST erstellt haben, sollten Sie sie zu einer regulären ASP.NET Core MVC Web API-Anwendung migrieren. Diese Migration würde die gleiche Funktionalität wie eine Konvertierung in gRPC bieten.

>[!div class="step-by-step"]
>[VorherigeS](wcf-endpoints-grpc-methods.md)
>[Weiter](rpc-types.md)
