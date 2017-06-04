---
title: "AppDomainInfo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# AppDomainInfo
Anwendungsdomäneninformationen  
  
## Syntax  
  
```  
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## Methoden  
 Die AppDomainInfo\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die AppDomainInfo\-Klasse hat die folgenden Eigenschaften:  
  
### AppDomainId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die ID der Anwendungsdomäne.  
  
### IsDefault  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Anwendungsdomäne die Standardanwendungsdomäne ist.  
  
### LogMalformedMessages  
 Datentyp: Boolesch  
  
 Zugriffstyp: Lesen\/Schreiben  
  
 Ein Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden.  
  
### LogMessagesAtServiceLevel  
 Datentyp: Boolesch  
  
 Zugriffstyp: Lesen\/Schreiben  
  
 Ein Wert, der angibt, ob Nachrichten auf Dienstebene \(vor Verschlüsselung und transportbezogenen Transformationen\) verfolgt werden.  
  
### LogMessagesAtTransportLevel  
 Datentyp: Boolesch  
  
 Zugriffstyp: Lesen\/Schreiben  
  
 Ein Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden.  
  
### MessageLoggingTraceListeners  
 Datentyp: TraceListener\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Sammlungsablaufverfolgungslistener, die die Ablaufverfolgungsquelle System.Wmi.MessageLogging abhören.  
  
### Name  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Anwendungsdomäne.  
  
### PerformanceCounters  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Umfang der aktiven Leistungsindikatoren in der Anwendungsdomäne.  
  
### ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Prozess\-ID.  
  
### ServiceConfigPath  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Pfad zur Konfiguration des Dienstes.  
  
### TraceLevel  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Lesen\/Schreiben  
  
 Die Ablaufverfolgungsebene der Ablaufverfolgungsquelle System.Wmi.  
  
### ServiceModelTraceListeners  
 Datentyp: TraceListener\-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Listener\-Sammlung aus der Ablaufverfolgungsquelle System.ServiceModel.  
  
## Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof|  
|---------|------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|