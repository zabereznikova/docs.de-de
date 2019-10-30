---
title: ICorDebugMDA-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: 4201fe23bf54388510088e21471edce91809e94c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129797"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA-Schnittstelle
Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDescription-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Ruft eine Zeichenfolge ab, die eine Beschreibung dieses MDA enthält.|  
|[GetFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Ruft die diesem MDA zugeordneten Flags ab.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Ruft eine Zeichenfolge ab, die den Namen dieses MDA enthält.|  
|[GetOSThreadId-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Ruft den Thread Bezeichner des Betriebssystems ab, auf dem dieser MDA ausgeführt wird.|  
|[GetXML-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Ruft den vollständigen XML-Stream ab, der diesem MDA zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
