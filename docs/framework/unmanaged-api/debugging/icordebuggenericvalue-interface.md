---
title: ICorDebugGenericValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: 312b8b005998da44feb5ae24ab4a0a17bb948a3f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138575"
---
# <a name="icordebuggenericvalue-interface"></a>ICorDebugGenericValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die für alle Werte gilt. Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|Kopiert den Wert in den angegebenen Puffer.|  
|[SetValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|Kopiert einen neuen Wert aus dem angegebenen Puffer.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugGenericValue` ist eine Unterschnittstelle, da Sie nicht Remote fähig ist.  
  
 Bei Verweis Typen ist der Wert der Verweis und nicht der Inhalt des Verweises.  
  
 Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
