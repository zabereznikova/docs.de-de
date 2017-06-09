---
title: "LocalServiceSecuritySettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# LocalServiceSecuritySettings
LocalServiceSecuritySettings  
  
## Syntax  
  
```  
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## Methoden  
 Die LocalServiceSecuritySettings\-Klasse definiert keine Methoden.  
  
## Eigenschaften  
 Die LocalServiceSecuritySettings\-Klasse verfügt über die folgenden Eigenschaften:  
  
### DetectReplays  
 Datentyp: boolean \(boolescher Wert\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob Replay\-Angriffe auf den Kanal automatisch erkannt und behandelt werden.  
  
### InactivityTimeout  
 Datentyp: datetime \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender Sicherheitssitzungen, die vom Dienst unterstützt wird.  
  
### IssuedCookieLifetime  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die die für alle neuen Sicherheitscookies ausgestellte Lebensdauer angibt.  
  
### MaxCachedCookies  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von Cookies, die zwischengespeichert werden kann.  
  
### MaxClockSkew  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die den maximal zulässigen Zeitunterschied zwischen den Systemuhren der beiden Kommunikationspartner angibt.  
  
### MaxPendingSessions  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender Verbindungen für den Dienst.  
  
### MaxStatefulNegotiations  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anzahl von Sicherheitsaushandlungen, die gleichzeitig aktiv sein können.  
  
### NegotiationTimeout  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die die maximale Dauer der Sicherheitsaushandlungsphase zwischen Server und Client angibt.  
  
### ReconnectTransportOnFailure  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob mit zuverlässigem WS\-Messaging hergestellte Verbindungen nach Transportfehlern erneut versuchen, eine Verbindung herzustellen.  
  
### ReplayCacheSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anzahl von zwischengespeicherten Nonces für die Replay\-Erkennung.  
  
### ReplayWindow  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die angibt, wie lange individuelle Nachrichtennonces gültig sind.  
  
### SessionKeyRenewalInterval  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die die Dauer angibt, nach der der Initiator den Schlüssel für die Sicherheitssitzung erneuert.  
  
### SessionKeyRolloverInterval  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die das Zeitintervall angibt, in dem ein alter Sitzungsschlüssel während der Schlüsselerneuerung für eingehende Nachrichten gültig ist.  
  
### TimestampValidityDuration  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die angibt, wie lange ein Zeitstempel gültig ist.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof|  
|---------|------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>