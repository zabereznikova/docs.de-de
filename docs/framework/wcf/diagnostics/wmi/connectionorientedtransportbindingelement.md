---
title: "ConnectionOrientedTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## Syntax  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## Methoden  
 Die ConnectionOrientedTransportBindingElement\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die ConnectionOrientedTransportBindingElement\-Klasse verfügt über die folgenden Eigenschaften:  
  
### ChannelInitializationTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zeitraum, der angibt, wie viel Zeit für die Durchführung der Kanalinitialisierung aufgewendet werden kann, bevor eine Zeitüberschreitung vorliegt.  
  
### ConnectionBufferSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Puffergröße, die zum Übertragen eines Teils der serialisierten Meldung vom Client oder Dienst verwendet wird.  
  
### HostNameComparisonMode  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob der Hostname zum Erreichen des Dienstes bei übereinstimmendem URI verwendet wird.  
  
### MaxBufferSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Größe des zu verwendenden Puffers.  
  
### MaxOutputDelay  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das maximale Zeitintervall, das als Teil einer Nachricht oder vollständigen Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.  
  
### MaxPendingAccepts  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender asynchroner Annahmethreads, die für die Verarbeitung eingehender Verbindungen beim Dienst zur Verfügung stehen.  
  
### MaxPendingConnections  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender Verbindungen.  
  
### TransferMode  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>