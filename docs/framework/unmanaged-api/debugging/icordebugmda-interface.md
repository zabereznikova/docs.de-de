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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a662185bb84e9a66573b43b26ffcd256ecb943f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909854"
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
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
