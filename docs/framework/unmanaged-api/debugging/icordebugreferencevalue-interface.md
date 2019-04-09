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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206459"
---
# <a name="icordebugreferencevalue-interface"></a>ICorDebugReferenceValue-Schnittstelle
Enthält Methoden, die einen Wert zu verwalten, der einen Verweis auf ein Objekt ist. (D. h. diese Schnittstelle stellt Methoden bereit, die einen Zeiger zu verwalten.) Diese Schnittstelle implementiert "ICorDebugValue".  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Dereference-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Ruft das Objekt ab, auf die verwiesen wird.|  
|[DereferenceStrong-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Nicht implementiert. Rufen Sie diese Methode nicht.|  
|[GetValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Ruft die aktuelle Speicheradresse des referenzierten Objekts ab.|  
|[IsNull-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Ruft einen Wert, der angibt, ob dies `ICorDebugReferenceValue` ein null-Wert in diesem Fall wird die `ICorDebugReferenceValue` verweist nicht auf ein Objekt.|  
|[SetValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Legt die aktuelle Speicheradresse fest. D.h., diese Methode legt für diesen `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.|  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime (CLR) kann eine Garbagecollection für Objekte ausführen, wenn es sich bei der gedebuggte Prozess fortgesetzt wird. Die Garbagecollection kann Objekte im Arbeitsspeicher verschieben. Ein `ICorDebugReferenceValue` wird entweder zusammen mit der Garbagecollection, damit die Informationen nach der Garbagecollection aktualisiert, oder er wird implizit vor der Garbagecollection ungültig gemacht.  
  
 Die `ICorDebugReferenceValue` Objekt kann implizit ungültig werden, nachdem der gedebuggte Prozess fortgesetzt wurde. Der abgeleitete "ICorDebugHandleValue" ist nicht für ungültig erklärt, bis er explizit aufgehoben oder verfügbar gemacht wird.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
