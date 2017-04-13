---
title: "Zuverl&#228;ssige Sitzungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Windows Communication Foundation, sessions and instances"
  - "WCF, sessions and instances"
  - "sessions and instances [WCF]"
helpviewer_keywords: 
  - "Instanzen [WCF]"
  - "Sitzungen [WCF]"
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Zuverl&#228;ssige Sitzungen
In diesem Abschnitt wird beschrieben, was unter einer zuverlässigen Sitzung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verstanden wird, zu welchem Zweck, wie und wann eine solche Sitzung verwendet wird und welche Bindungskonfiguration hierfür erforderlich ist. Zudem enthält der Abschnitt Verweise auf Best Practices.In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.  
  
 Mithilfe der von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten zuverlässigen Sitzung wird sichergestellt, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder Transportvermittler übertragen und nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden, übermittelt werden.  
  
 Um eine zuverlässige Sitzung mit einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung zu verwenden, nutzen Sie entweder eine der vom System bereitgestellten Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die diese Sitzung unterstützt.  
  
## In diesem Abschnitt  
 [Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 Beschreibt zuverlässige Sitzungen, wann diese verwendet werden sollten, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und deren Funktionsweise.  
  
 [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)  
 Beschreibt, wie eine zuverlässige Sitzung über HTTP mit einer benutzerdefinierten in der Konfiguration angegebenen Bindung erstellt wird.  
  
 [Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)  
 Beschreibt, wie eine zuverlässige Sitzung geschützt wird.  
  
 [Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)  
 Beschreibt, wie eine zuverlässige Sitzung über HTTPS erstellt wird.  
  
 [Empfohlene Vorgehensweisen für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)  
 Beschreibt einige der Best Practices in Verbindung mit der Verwendung einer zuverlässigen Sitzung.  
  
## Referenz  
 <xref:System.ServiceModel.ReliableSession>  
  
## Siehe auch  
 [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
 [Sitzungen, Instanziierung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)