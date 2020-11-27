---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: c5c44f4d8f6d93443802d5e1950c4d850976c5b6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291127"
---
# <a name="appdomaininfo"></a>AppDomainInfo

Anwendungsdomäneninformationen  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
  
## <a name="methods"></a>Methoden  

 Die AppDomainInfo-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die AppDomainInfo-Klasse hat die folgenden Eigenschaften:  
  
### <a name="appdomainid"></a>AppDomainId  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die ID der Anwendungsdomäne.  
  
### <a name="isdefault"></a>IsDefault  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Anwendungsdomäne die Standardanwendungsdomäne ist.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  

 Datentyp: Boolesch  
  
 Zugriffstyp: Lesen/Schreiben  
  
 Ein Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  

 Datentyp: Boolesch  
  
 Zugriffstyp: Lesen/Schreiben  
  
 Ein Wert, der angibt, ob Nachrichten auf Dienstebene (vor Verschlüsselung und transportbezogenen Transformationen) verfolgt werden.  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  

 Datentyp: Boolesch  
  
 Zugriffstyp: Lesen/Schreiben  
  
 Ein Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  

 Datentyp: TraceListener-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Sammlungsablaufverfolgungslistener, die die Ablaufverfolgungsquelle System.Wmi.MessageLogging abhören.  
  
### <a name="name"></a>Name  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Anwendungsdomäne.  
  
### <a name="performancecounters"></a>PerformanceCounters  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Umfang der aktiven Leistungsindikatoren in der Anwendungsdomäne.  
  
### <a name="processid"></a>ProcessId  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Prozess-ID.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Pfad zur Konfiguration des Dienstes.  
  
### <a name="tracelevel"></a>TraceLevel  

 Datentyp: String  
  
 Zugriffstyp: Lesen/Schreiben  
  
 Die Ablaufverfolgungsebene der Ablaufverfolgungsquelle System.Wmi.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  

 Datentyp: TraceListener-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Listener-Sammlung aus der Ablaufverfolgungsquelle System.ServiceModel.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
