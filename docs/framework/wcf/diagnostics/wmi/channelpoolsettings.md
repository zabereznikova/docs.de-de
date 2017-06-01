---
title: "ChannelPoolSettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ChannelPoolSettings
ChannelPoolSettings  
  
## Syntax  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## Methoden  
 Die ChannelPoolSettings\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die ChannelPoolSettings\-Klasse verfügt über die folgenden Eigenschaften:  
  
### IdleTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.  
  
### LeaseTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.  
  
### MaxOutboundChannelsPerEndpoint  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>