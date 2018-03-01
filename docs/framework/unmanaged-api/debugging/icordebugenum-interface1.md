---
title: ICorDebugEnum Schnittstelle1
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
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 751cca87962473501ef29a4deb99d9d24be33396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenum-interface1"></a>ICorDebugEnum Schnittstelle1
Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer Debuganwendung verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|Erstellt eine Kopie dieser `ICorDebugEnum` Objekt.|  
|[GetCount-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|Ruft die Anzahl der Elemente in der Enumeration.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|Verschiebt den Cursor auf den Anfang der Enumeration.|  
|[Skip-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Enumeratoren leiten sich von `ICorDebugEnum`:  
  
-   "ICorDebugAppDomainEnum"  
  
-   "ICorDebugAssemblyEnum"  
  
-   [ICorDebugBlockingObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   "ICorDebugBreakpointEnum"  
  
-   "ICorDebugChainEnum"  
  
-   "ICorDebugCodeEnum"  
  
-   "ICorDebugErrorInfoEnum"  
  
-   [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   "ICorDebugFrameEnum"  
  
-   [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   "ICorDebugModuleEnum"  
  
-   "ICorDebugObjectEnum"  
  
-   "ICorDebugProcessEnum"  
  
-   "ICorDebugStepperEnum"  
  
-   "ICorDebugThreadEnum"  
  
-   "ICorDebugTypeEnum"  
  
-   "ICorDebugValueEnum"  
  
-   [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
