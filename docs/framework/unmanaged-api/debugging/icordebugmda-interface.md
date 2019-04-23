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
ms.openlocfilehash: cea8f6827d3e361b3f6498e6612d8b11a2357285
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098656"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA-Schnittstelle
Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDescription-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Ruft eine Zeichenfolge, die mit einer Beschreibung dieses MDA.|  
|[GetFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Ruft die Flags, die mit diesem aktiven MDA ab.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Ruft eine Zeichenfolge, die mit dem Namen dieses MDA.|  
|[GetOSThreadId-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Ruft ab, der Betriebssystem-Thread-ID auf dem dieser MDA ausgeführt wird.|  
|[GetXML-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Ruft den vollständigen XML-Stream dieser MDA zugeordnet.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
