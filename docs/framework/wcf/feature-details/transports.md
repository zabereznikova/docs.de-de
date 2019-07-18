---
title: Transporte in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933730"
---
# <a name="transports-in-windows-communication-foundation"></a>Transporte in Windows Communication Foundation
Die Transportschicht befindet sich auf der niedrigsten Ebene des Kanalstapels. Hauptsächlich in Windows Communication Foundation (WCF) verwendeten Transportprotokolle sind HTTP, HTTPS, TCP und named Pipes. Die Themen in diesem Abschnitt behandeln die Auswahl dieser Transporte, das Konfigurieren des Transports und das Festlegen von Optimierungseigenschaften.  
  
 WCF schließt zusätzliche Transporte ein. Weitere Informationen zu Message Queuing (auch bekannt als MSMQ)-Transport, finden Sie unter [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Weitere Informationen zu-Peer-zu-Peer-Transport, finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Auswählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Beschreibt die drei Haupttransporte und die Überlegungen für die Auswahl.  
  
 [Auswählen eines Nachrichtenencoders](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Beschreibt Faktoren, die bei der Auswahl eines Nachrichtencodierung-Bindungselements zu berücksichtigen sind.  
  
 [Streamen der Nachrichtenübertragung](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, um Streaming zu ermöglichen.  
  
 [Konfigurieren von HTTP und HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Beschreibt, wie HTTP- und HTTPS-Transportbindungselemente konfiguriert werden.  
  
 [Vorgehensweise: Ersetzen Sie die WCF URL-Reservierung durch eine eingeschränkte Reservierung](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Beschreibt, wie Reservierungen für WCFURL eingeschränkt.  
  
 [Transportkontingente](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Beschreibt Überlegungen für das Festlegen von Kontingenten, die in der Transportschicht verfügbar sind.  
  
 [Arbeiten mit NATs und Firewalls](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, wenn Nachrichten hinter einer Firewall gesendet oder empfangen werden oder wenn NAT (Network Address Translation) vorhanden ist.  
  
 [Net.TCP-Portfreigabe](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Beschreibt, wie die Net.TCP Port Sharing-Komponente von WCF verwenden.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)
