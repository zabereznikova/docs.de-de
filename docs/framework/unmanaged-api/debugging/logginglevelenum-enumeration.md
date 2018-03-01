---
title: LoggingLevelEnum-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1f8bb53d53593073df7ef7aa095eeb3b9f8c632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="logginglevelenum-enumeration"></a>LoggingLevelEnum-Enumeration
Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`LTraceLevel0`|Die Nachricht ist eine andere Ablaufverfolgungsebene 0.|  
|`LTraceLevel1`|Die Nachricht ist eine andere Ablaufverfolgungsebene 1.|  
|`LTraceLevel2`|Die Nachricht ist eine andere Ablaufverfolgungsebene 2.|  
|`LTraceLevel3`|Die Nachricht ist eine andere Ablaufverfolgungsebene 3.|  
|`LTraceLevel4`|Die Nachricht ist eine andere Ablaufverfolgungsebene 4.|  
|`LStatusLevel0`|Die Nachricht ist, den Status der Ebene 0.|  
|`LStatusLevel1`|Die Nachricht ist, den Status der Ebene 1.|  
|`LStatusLevel2`|Die Nachricht ist, den Status der Ebene 2.|  
|`LStatusLevel3`|Die Nachricht ist, den Status der Ebene 3.|  
|`LStatusLevel4`|Die Nachricht ist, den Status der Ebene 4.|  
|`LWarningLevel`|Die Meldung ist eine Warnstufe erreicht.|  
|`LErrorLevel`|Die Meldung ist eine Fehlerstufe erreicht.|  
|`LPanicLevel`|Die Meldung ist ein panic auf.|  
  
## <a name="remarks"></a>Hinweise  
 Ruft die common Language Runtime (CLR) die [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) Methode, um den Debugger zu benachrichtigen, dass ein verwalteter Thread ein Ereignis protokolliert hat. Die CLR übergibt einen Wert, der die `LoggingLevelEnum` Enumeration an, den Schweregrad der Meldung, die der verwaltete Thread in das Ereignisprotokoll geschrieben hat.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.EventLog>  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
