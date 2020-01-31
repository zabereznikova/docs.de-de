---
title: ICorDebugEnum-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: cc5598f9cbec4b97bb75f83fb18ccf8742904272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783008"
---
# <a name="icordebugenum-interface"></a>ICorDebugEnum-Schnittstelle

Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer debugginganwendung verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](icordebugenum-clone-method.md)|Erstellt eine Kopie dieses `ICorDebugEnum` Objekts.|  
|[GetCount-Methode](icordebugenum-getcount-method.md)|Ruft die Anzahl der Elemente in der-Enumeration ab.|  
|[Reset-Methode](icordebugenum-reset-method.md)|Verschiebt den Cursor an den Anfang der Enumeration.|  
|[Skip-Methode](icordebugenum-skip-method.md)|Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Enumeratoren werden von `ICorDebugEnum`abgeleitet:  
  
- "ICorDebugAppDomainEnum"  
  
- "ICorDebugAssemblyEnum"  
  
- [ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)  
  
- "ICorDebugBreakpointEnum"  
  
- ICorDebugChainEnum  
  
- "ICorDebugCodeEnum"  
  
- ICorDebugErrorInfoEnum  
  
- [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)  
  
- "ICorDebugFrameEnum"  
  
- [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)  
  
- [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)  
  
- [ICorDebugHeapEnum](icordebugheapenum-interface.md)  
  
- [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)  
  
- ICorDebugModuleEnum  
  
- "ICorDebugObjectEnum"  
  
- "ICorDebugProcessEnum"  
  
- "ICorDebugStepperEnum"  
  
- "ICorDebugThreadEnum"  
  
- "ICorDebugTypeEnum"  
  
- ICorDebugValueEnum  
  
- [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
