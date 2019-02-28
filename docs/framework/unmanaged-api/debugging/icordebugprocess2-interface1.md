---
title: ICorDebugProcess2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3009ee6a2ba22771a2132032744f76ca527c422
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965682"
---
# <a name="icordebugprocess2-interface"></a>ICorDebugProcess2-Schnittstelle
Eine logische Erweiterung der ICorDebugProcess-Schnittstelle, die eine ausgeführten Prozess für verwalteten Code darstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Entfernt einen Haltepunkt am angegebenen Offset, die von einem früheren Aufruf festgelegt wurde `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[GetDesiredNGENCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Ruft die Flags ab, die für die common Language Runtime (CLR) festgelegt werden müssen, um das Image in den Prozess, der auf die dieses laden `ICorDebugProcess2`.|  
|[GetReferenceValueFromGCHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Ruft einen Verweiszeiger auf das angegebene verwaltete Objekt, das eine Garbagecollection verarbeitet hat.|  
|[GetThreadForTaskID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Ruft den Thread, der auf dem die Aufgabe mit der angegebenen ID ausgeführt wird.|  
|[GetVersion-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Ruft die Version der CLR auf dem die zu debuggende Prozess ausgeführt wird.|  
|[SetDesiredNGENCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Legt die Flags, die für den just-in-Time (JIT)-Compiler zum Laden eines Bilds in der gedebuggte Prozess erforderlich sind.|  
|[SetUnmanagedBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Legt einen nicht verwaltete Haltepunkt am Offset angegebene systemeigene Image fest.|  
  
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
