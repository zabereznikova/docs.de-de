---
title: "Transporte in Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Transporte [WCF]"
  - "WCF, Transporte"
  - "Windows Communication Foundation, Transporte"
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Transporte in Windows Communication Foundation
Die Transportschicht befindet sich auf der niedrigsten Ebene des Kanalstapels.Die in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendeten Haupttransporte sind HTTP, HTTPS, TCP und Named Pipes.Die Themen in diesem Abschnitt behandeln die Auswahl dieser Transporte, das Konfigurieren des Transports und das Festlegen von Optimierungseigenschaften.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] schließt zusätzliche Transporte ein.Informationen über Message Queuing \(auch bekannt als MSMQ\-Transport\) finden Sie unter [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).Informationen zum Peer\-to\-Peer\-Transport finden Sie unter [Peer\-to\-Peer\-Netzwerke](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## In diesem Abschnitt  
 [Wählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Beschreibt die drei Haupttransporte und die Überlegungen für die Auswahl.  
  
 [Auswählen eines Nachrichtenencoders](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Beschreibt Faktoren, die bei der Auswahl eines Nachrichtencodierung\-Bindungselements zu berücksichtigen sind.  
  
 [Nachrichtenübertragung per Stream](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, um Streaming zu ermöglichen.  
  
 [Konfigurieren von HTTP und HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Beschreibt, wie HTTP\- und HTTPS\-Transportbindungselemente konfiguriert werden.  
  
 [Vorgehensweise: Ersetzen der WCF URL\-Reservierung durch eine eingeschränkte Reservierung](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Beschreibt, wie Reservierungen mit eingeschränkter URL in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]verwendet werden.  
  
 [Transportkontingente](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Beschreibt Überlegungen für das Festlegen von Kontingenten, die in der Transportschicht verfügbar sind.  
  
 [Arbeiten mit NATs und Firewalls](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Beschreibt, wie die Transportschicht konfiguriert wird, wenn Nachrichten hinter einer Firewall gesendet oder empfangen werden oder wenn NAT \(Network Address Translation\) vorhanden ist.  
  
 [Net.TCP\-Anschlussfreigabe](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Beschreibt, wie die Net.TCP Port Sharing\-Komponente von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet wird.  
  
## Referenz  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## Verwandte Abschnitte  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)