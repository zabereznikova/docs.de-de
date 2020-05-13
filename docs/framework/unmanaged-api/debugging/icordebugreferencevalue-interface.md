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
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378351"
---
# <a name="icordebugreferencevalue-interface"></a>ICorDebugReferenceValue-Schnittstelle
Stellt Methoden bereit, die einen-Wert verwalten, der ein Verweis auf ein-Objekt ist. (Das heißt, diese Schnittstelle stellt Methoden bereit, die einen-Zeiger verwalten.) Diese Schnittstelle implementiert "ICorDebug Value".  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Dereference-Methode](icordebugreferencevalue-dereference-method.md)|Ruft das Objekt ab, auf das verwiesen wird.|  
|[DereferenceStrong-Methode](icordebugreferencevalue-dereferencestrong-method.md)|Nicht implementiert. Rufen Sie diese Methode nicht auf.|  
|[GetValue-Methode](icordebugreferencevalue-getvalue-method.md)|Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.|  
|[IsNull-Methode](icordebugreferencevalue-isnull-method.md)|Ruft einen Wert ab, der angibt `ICorDebugReferenceValue` , ob es sich um einen NULL-Wert handelt. in diesem Fall verweist der `ICorDebugReferenceValue` nicht auf ein-Objekt.|  
|[SetValue-Methode](icordebugreferencevalue-setvalue-method.md)|Legt die aktuelle Speicheradresse fest. Das heißt, diese Methode legt diese fest, `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Common Language Runtime (CLR) kann eine Garbage Collection für Objekte ausführen, wenn der Debugprozess fortgesetzt wird. Der Garbage Collection kann Objekte im Arbeitsspeicher verschieben. Eine `ICorDebugReferenceValue` wird entweder mit der Garbage Collection zusammenarbeiten, damit die Informationen nach der Garbage Collection aktualisiert werden, oder Sie wird vor dem Garbage Collection implizit für ungültig erklärt.  
  
 Das `ICorDebugReferenceValue` Objekt kann nach dem Fortsetzen des debuggten Prozesses implizit ungültig gemacht werden. Der abgeleitete "ICorDebugHandleValue" wird erst ungültig, wenn er explizit freigegeben oder verfügbar gemacht wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
