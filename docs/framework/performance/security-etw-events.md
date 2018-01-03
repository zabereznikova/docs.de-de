---
title: ETW-Sicherheitsereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abf6e6896267b6d1c8449b020230381923f38f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-etw-events"></a>ETW-Sicherheitsereignisse
<a name="top"></a> Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.  
  
 Diese Kategorie umfasst die folgenden Ereignisse:  
  
-   [StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a>StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0 x 400)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|Beginn der Überprüfung mit starkem Namen.|  
|`StrongNameVerificationStop_V1`|182|Ende der Überprüfung mit starkem Namen.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Die Überprüfungsflags.|  
|ErrorCode|win:UInt32|Der HResult-Fehlercode.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Der vollqualifizierte Assemblyname.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück zum Anfang](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a>AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0 x 400)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Beginn der Authenticodeüberprüfung.|  
|`AuthenticodeVerificationStop_V1`|184|Ende der Authenticodeüberprüfung.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Die Überprüfungsflags.|  
|ErrorCode|win:UInt32|Der HResult-Fehlercode.|  
|ModulePath|win:UnicodeString|Der Modulpfad.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
