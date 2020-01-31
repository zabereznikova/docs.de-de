---
title: ICorDebugReferenceValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792132"
---
# <a name="icordebugreferencevalue-interface"></a>ICorDebugReferenceValue-Schnittstelle
Stellt Methoden bereit, die einen-Wert verwalten, der ein Verweis auf ein-Objekt ist. (Das heißt, diese Schnittstelle stellt Methoden bereit, die einen-Zeiger verwalten.) Diese Schnittstelle implementiert "ICorDebug Value".  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Dereference-Methode](icordebugreferencevalue-dereference-method.md)|Ruft das Objekt ab, auf das verwiesen wird.|  
|[DereferenceStrong-Methode](icordebugreferencevalue-dereferencestrong-method.md)|Nicht implementiert. Diese Methode nicht aufzurufen.|  
|[GetValue-Methode](icordebugreferencevalue-getvalue-method.md)|Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.|  
|[IsNull-Methode](icordebugreferencevalue-isnull-method.md)|Ruft einen Wert ab, der angibt, ob dieses `ICorDebugReferenceValue` ein NULL-Wert ist. in diesem Fall zeigt der `ICorDebugReferenceValue` nicht auf ein Objekt.|  
|[SetValue-Methode](icordebugreferencevalue-setvalue-method.md)|Legt die aktuelle Speicheradresse fest. Das heißt, diese Methode legt diese `ICorDebugReferenceValue` fest, um auf ein Objekt zu verweisen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Common Language Runtime (CLR) kann eine Garbage Collection für Objekte ausführen, wenn der Debugprozess fortgesetzt wird. Der Garbage Collection kann Objekte im Arbeitsspeicher verschieben. Eine `ICorDebugReferenceValue` wird entweder mit der Garbage Collection zusammenarbeiten, damit die Informationen nach dem Garbage Collection aktualisiert werden, oder Sie wird vor der Garbage Collection implizit für ungültig erklärt.  
  
 Das `ICorDebugReferenceValue`-Objekt kann nach dem Fortsetzen des debuggten Prozesses implizit ungültig gemacht werden. Der abgeleitete "ICorDebugHandleValue" wird erst ungültig, wenn er explizit freigegeben oder verfügbar gemacht wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
