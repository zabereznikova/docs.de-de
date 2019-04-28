---
title: LoggingLevelEnum-Enumeration
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe8e1355382273a681e927897f4a8ff5814b8de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765426"
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
|`LTraceLevel0`|Die Meldung ist ein Trace-Ebene-0.|  
|`LTraceLevel1`|Die Meldung ist ein Trace-Ebene-1.|  
|`LTraceLevel2`|Die Meldung ist ein Trace-Ebene-2.|  
|`LTraceLevel3`|Die Meldung ist ein 3-Ablaufverfolgungsebene.|  
|`LTraceLevel4`|Die Meldung ist ein 4-Ablaufverfolgungsebene.|  
|`LStatusLevel0`|Die Nachricht ist, den Status der Ebene 0.|  
|`LStatusLevel1`|Die Nachricht ist, den Status der Ebene 1.|  
|`LStatusLevel2`|Die Nachricht ist, den Status der Ebene 2.|  
|`LStatusLevel3`|Die Nachricht ist, den Status der Ebene 3.|  
|`LStatusLevel4`|Die Nachricht ist, den Status der Ebene 4.|  
|`LWarningLevel`|Die Meldung ist eine Warnstufe erreicht.|  
|`LErrorLevel`|Die Meldung ist ein Fehler auf.|  
|`LPanicLevel`|Die Meldung ist eine panic Ebene.|  
  
## <a name="remarks"></a>Hinweise  
 Ruft die common Language Runtime (CLR) die [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) Methode, um den Debugger zu benachrichtigen, dass ein verwalteter Thread ein Ereignis protokolliert hat. Die CLR übergibt den Wert der `LoggingLevelEnum` Enumeration an, dass der Schweregrad der Meldung, die der verwaltete Thread in das Ereignisprotokoll geschrieben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.EventLog>
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
