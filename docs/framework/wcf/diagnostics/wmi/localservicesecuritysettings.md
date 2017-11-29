---
title: LocalServiceSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 74eff3a6193e6507c1049accf4c43c3ecc8d30a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings
LocalServiceSecuritySettings  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="methods"></a>Methoden  
 Die LocalServiceSecuritySettings-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die LocalServiceSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="detectreplays"></a>DetectReplays  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob Replay-Angriffe auf den Kanal automatisch erkannt und behandelt werden.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von ausstehenden Sicherheitssitzungen, die der Dienst unterstützt.  
  
### <a name="issuedcookielifetime"></a>IssuedCookieLifetime  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die die für alle neuen Sicherheitscookies ausgestellte Lebensdauer angibt.  
  
### <a name="maxcachedcookies"></a>MaxCachedCookies  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von Cookies, die zwischengespeichert werden können.  
  
### <a name="maxclockskew"></a>MaxClockSkew  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die den maximal zulässigen Zeitunterschied zwischen den Systemuhren der beiden Kommunikationspartner angibt.  
  
### <a name="maxpendingsessions"></a>MaxPendingSessions  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender Verbindungen für den Dienst.  
  
### <a name="maxstatefulnegotiations"></a>MaxStatefulNegotiations  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anzahl von Sicherheitsverhandlungen, die gleichzeitig aktiv sein können.  
  
### <a name="negotiationtimeout"></a>NegotiationTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die die maximale Dauer der Sicherheitsaushandlungsphase zwischen Server und Client angibt.  
  
### <a name="reconnecttransportonfailure"></a>ReconnectTransportOnFailure  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob mit zuverlässigem WS-Messaging hergestellte Verbindungen nach Transportfehlern erneut versuchen, eine Verbindung herzustellen.  
  
### <a name="replaycachesize"></a>ReplayCacheSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anzahl zwischengespeicherter Nonces, die für die Wiedergabeerkennung verwendet werden.  
  
### <a name="replaywindow"></a>ReplayWindow  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die angibt, wie lange individuelle Nachrichtennonces gültig sind.  
  
### <a name="sessionkeyrenewalinterval"></a>SessionKeyRenewalInterval  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die die Dauer angibt, nach der der Initiator den Schlüssel für die Sicherheitssitzung erneuert.  
  
### <a name="sessionkeyrolloverinterval"></a>SessionKeyRolloverInterval  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die das Zeitintervall angibt, in dem ein alter Sitzungsschlüssel während der Schlüsselerneuerung für eingehende Nachrichten gültig ist.  
  
### <a name="timestampvalidityduration"></a>TimestampValidityDuration  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeitspanne, die angibt, wie lange ein Zeitstempel gültig ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
