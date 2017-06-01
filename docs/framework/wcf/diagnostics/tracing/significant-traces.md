---
title: "Bedeutende Ablaufverfolgungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Bedeutende Ablaufverfolgungen
Dieses Thema führt einige der Hauptablaufverfolgungen auf, die von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ausgegeben werden.  
  
## Bedeutende Ablaufverfolgungen  
  
|Ablaufverfolgung|Beschreibung|  
|----------------------|------------------|  
|Nachrichtenablaufverfolgung|Die Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachricht von der Nachrichtenprotokollierungsfunktion bei Aktivierung der `System.ServiceModel.MessageLogging`\-Ablaufverfolgungsquelle protokolliert wird.Durch  Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt.Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, die auch vom Attribut "Message Source" in der Nachrichtenprotokoll\-Ablaufverfolgung angegeben werden.|  
|"Nachricht empfangen"\-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachricht bei Aktivierung der `System.ServiceModel`\-Ablaufverfolgungsquelle auf Informations\- oder Verbose\-Ebene empfangen wird.Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|"Nachricht gesendet"\-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachricht gesendet wird, wenn die `System.ServiceModel`\-Ablaufverfolgungsquelle auf Informations\- oder Verbose\-Ebene aktiviert ist.Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsgraphenansicht zu sehen.|  
|Abrufen von ChannelEndpointElement|Diese Ablaufverfolgung wird in einer Construct\-Channel\-Factory auf Informationsebene ausgegeben.Die Verfolgung beinhaltet eine Beschreibung des Endpunkts, mit dem der Client kommuniziert \(Remoteadresse, Bindung, Vertragsname\).|  
|Abrufen des ServiceElement|Diese Ablaufverfolgung wird im Construct\-Diensthost auf Informationsebene ausgegeben.Sie liefert eine Beschreibung des Dienstvertrags und der Bindung.|  
|SocketConnection erstellen|Diese Ablaufverfolgung wird in der ersten "Verarbeiten"\-Aktion, die vom Client durchgeführt wird, und in der "Bytes erhalten"\-Aktivität im Dienst ausgegeben.Sie liefert die lokalen und Remote\-IP\-Adressen.Sie wird auf Informationsebene ausgegeben.|