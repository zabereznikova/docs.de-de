---
title: "ReliableSessionBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# ReliableSessionBindingElement
ReliableSessionBindingElement  
  
## Syntax  
  
```  
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## Methoden  
 Mit der ReliableSessionBindingElement\-Klasse werden keine Methoden definiert.  
  
## Eigenschaften  
 Die ReliableSessionBindingElement\-Klasse verfügt über die folgenden Eigenschaften:  
  
### AcknowledgementInterval  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, in dem ein Ziel wartet, bevor eine Bestätigung an die Nachrichtenquelle in zuverlässigen Kanälen gesendet wird, die von der Factory erstellt werden.  
  
### FlowControlEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob die Flusssteuerung aktiviert ist.  
  
### InactivityTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die maximale Dauer an, die der Kanal dem anderen Kommunikationsteilnehmer für das ausbleibende Senden von Nachrichten zugesteht, bevor im Kanal ein Fehler ausgelöst wird.  
  
### MaxPendingChannels  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von Kanälen, die auf dem Listener akzeptiert werden sollen.  
  
### MaxRetryCount  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Maximale Anzahl der Versuche eines zuverlässigen Kanals, eine Nachricht, für die keine Bestätigung empfangen wurde, erneut zu übertragen \(durch Aufrufen von `Send` im zugrunde liegenden Kanal\).  
  
### MaxTransferWindowSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Übertragungsfenstergröße für die zuverlässige Sitzung.  
  
### Testreihe  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob Nachrichten auf jeden Fall in der Reihenfolge ihres Versands eintreffen.  
  
### ReliableMessagingVersion  
 Datentyp: Ganzzahl  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine ganze Zahl, die die in der zuverlässigen Sitzung verwendete WS\-ReliableMessaging Protokollversion angibt.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>