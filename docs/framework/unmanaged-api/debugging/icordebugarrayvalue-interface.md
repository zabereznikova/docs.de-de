---
title: ICorDebugArrayValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
 `ICorDebugArrayValue`unterstützt eindimensionale und mehrdimensionale Arrays.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
