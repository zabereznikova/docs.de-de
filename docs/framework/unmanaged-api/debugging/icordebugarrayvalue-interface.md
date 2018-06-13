---
title: ICorDebugArrayValue Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a96f2b21e524f03ea3290be268244eaceeb5c7f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408176"
---
# <a name="icordebugarrayvalue-interface1"></a>ICorDebugArrayValue Schnittstelle1
Eine Unterklasse von ICorDebugHeapValue, das ein eindimensionales oder mehrdimensionales Array darstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBaseIndicies-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|Ruft den Basis Index jeder Dimension im Array ab.|  
|[GetCount-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|Ruft die Gesamtanzahl der Elemente im Array ab.|  
|[GetDimensions-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|Ruft die Dimensionen des Arrays ab.|  
|[GetElement-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|Ruft einen Wert, der das angegebene Element im Array darstellt.|  
|[GetElementAtPosition-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|Ruft das Element an der angegebenen Position, behandelt das Array als ein nullbasiertes, eindimensionales Array.|  
|[GetElementType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|Ruft den einfachen Typ der Elemente im Array ab.|  
|[GetRank-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|Ruft die Anzahl der Dimensionen im Array ab.|  
|[HasBaseIndicies-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|Bestimmt, ob das Array mit Basis Indizes aufweist.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugArrayValue` unterstützt eindimensionale und mehrdimensionale Arrays.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
