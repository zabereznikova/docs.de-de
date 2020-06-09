---
title: Transporte in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 077d63d8038b245a68083611897c1e6c68971071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598670"
---
# <a name="transports-in-windows-communication-foundation"></a>Transporte in Windows Communication Foundation
Die Transportschicht befindet sich auf der niedrigsten Ebene des Kanalstapels. Die in Windows Communication Foundation (WCF) verwendeten Haupt Transporte sind http, HTTPS, TCP und Named Pipes. Die Themen in diesem Abschnitt behandeln die Auswahl dieser Transporte, das Konfigurieren des Transports und das Festlegen von Optimierungseigenschaften.  
  
 WCF umfasst weitere Transporte. Weitere Informationen zu Message Queuing (auch als MSMQ bezeichnet)-Transport finden Sie unter [Warteschlangen und zuverlässige Sitzungen](queues-and-reliable-sessions.md). Weitere Informationen zum Peer-to-Peer-Transport finden Sie unter [Peer-to-Peer-Netzwerke](peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Wählen eines Transports](choosing-a-transport.md)  
 Beschreibt die drei Haupttransporte und die Überlegungen für die Auswahl.  
  
 [Auswählen eines Nachrichtenencoders](choosing-a-message-encoder.md)  
 Beschreibt Faktoren, die bei der Auswahl eines Nachrichtencodierung-Bindungselements zu berücksichtigen sind.  
  
 [Nachrichtenübertragung per Stream](streaming-message-transfer.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, um Streaming zu ermöglichen.  
  
 [Konfigurieren von HTTP und HTTPS](configuring-http-and-https.md)  
 Beschreibt, wie HTTP- und HTTPS-Transportbindungselemente konfiguriert werden.  
  
 [Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Hier wird beschrieben, wie eingeschränkte wcfurl-Reservierungen verwendet werden.  
  
 [Transportkontingente](transport-quotas.md)  
 Beschreibt Überlegungen für das Festlegen von Kontingenten, die in der Transportschicht verfügbar sind.  
  
 [Arbeiten mit NATs und Firewalls](working-with-nats-and-firewalls.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, wenn Nachrichten hinter einer Firewall gesendet oder empfangen werden oder wenn NAT (Network Address Translation) vorhanden ist.  
  
 [Net.TCP-Anschlussfreigabe](net-tcp-port-sharing.md)  
 Beschreibt, wie die net. TCP-Port Freigabe Komponente von WCF verwendet wird.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Bindungen](bindings.md)  
  
 [Erweitern von Bindungen](../extending/extending-bindings.md)
