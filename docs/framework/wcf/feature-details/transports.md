---
title: Transporte in Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9275f1812111365ed6b0fb3be6957cd9ca883fdf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="transports-in-windows-communication-foundation"></a>Transporte in Windows Communication Foundation
Die Transportschicht befindet sich auf der niedrigsten Ebene des Kanalstapels. Die in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendeten Haupttransporte sind HTTP, HTTPS, TCP und Named Pipes. Die Themen in diesem Abschnitt behandeln die Auswahl dieser Transporte, das Konfigurieren des Transports und das Festlegen von Optimierungseigenschaften.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] schließt zusätzliche Transporte ein. Weitere Informationen zu Message Queuing (auch bekannt als MSMQ)-Transport, finden Sie unter [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Informationen zu Peer-zu-Peer-Transport, finden Sie unter [Peer-zu-Peer-Netzwerken](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Wählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Beschreibt die drei Haupttransporte und die Überlegungen für die Auswahl.  
  
 [Auswählen eines Nachrichtenencoders](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Beschreibt Faktoren, die bei der Auswahl eines Nachrichtencodierung-Bindungselements zu berücksichtigen sind.  
  
 [Nachrichtenübertragung per Stream](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, um Streaming zu ermöglichen.  
  
 [Konfigurieren von HTTP und HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Beschreibt, wie HTTP- und HTTPS-Transportbindungselemente konfiguriert werden.  
  
 [Vorgehensweise: Ersetzen Sie die WCF URL-Reservierung durch eine eingeschränkte Reservierung](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Beschreibt, wie Reservierungen mit eingeschränkter URL in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]verwendet werden.  
  
 [Transportkontingente](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Beschreibt Überlegungen für das Festlegen von Kontingenten, die in der Transportschicht verfügbar sind.  
  
 [Arbeiten mit NATs und Firewalls](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, wenn Nachrichten hinter einer Firewall gesendet oder empfangen werden oder wenn NAT (Network Address Translation) vorhanden ist.  
  
 [Net.TCP-Portfreigabe](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Beschreibt, wie die Net.TCP Port Sharing-Komponente von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet wird.  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)
