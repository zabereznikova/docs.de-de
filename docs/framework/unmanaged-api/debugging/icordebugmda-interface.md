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
ms.openlocfilehash: 550b39445dfe4d97e712e9a4c73aa0f497b3fce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420965"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA-Schnittstelle
Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDescription-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Ruft eine Zeichenfolge, enthält eine Beschreibung dieses MDA.|  
|[GetFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Ruft die Flags, die dieser MDA zugeordnet.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Ruft eine Zeichenfolge mit dem Namen dieses MDA.|  
|[GetOSThreadId-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Ruft die Betriebssystem-Thread-ID auf dem dieser MDA ausgeführt wird.|  
|[GetXML-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Ruft den vollständigen XML-Stream dieser MDA zugeordnet.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
