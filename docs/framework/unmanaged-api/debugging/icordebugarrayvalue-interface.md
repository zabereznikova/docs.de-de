---
title: ICorDebugArrayValue-Schnittstelle
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
ms.openlocfilehash: 90688132b98f8316a4b08988c08b2f7cc7ce0fd8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725047"
---
# <a name="icordebugarrayvalue-interface"></a>ICorDebugArrayValue-Schnittstelle

Eine Unterklasse von ICorDebugHeapValue, die ein eindimensionales oder mehrdimensionales Array darstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetBaseIndicies-Methode](icordebugarrayvalue-getbaseindicies-method.md)|Ruft den Basis Index jeder Dimension im Array ab.|  
|[GetCount-Methode](icordebugarrayvalue-getcount-method.md)|Ruft die Gesamtzahl der Elemente im Array ab.|  
|[GetDimensions-Methode](icordebugarrayvalue-getdimensions-method.md)|Ruft die Dimensionen des Arrays ab.|  
|[GetElement-Methode](icordebugarrayvalue-getelement-method.md)|Ruft einen Wert ab, der das angegebene Element im Array darstellt.|  
|[GetElementAtPosition-Methode](icordebugarrayvalue-getelementatposition-method.md)|Ruft das Element an der angegebenen Position ab, wobei das Array als NULL basiertes, eindimensionales Array behandelt wird.|  
|[GetElementType-Methode](icordebugarrayvalue-getelementtype-method.md)|Ruft den einfachen Typ der Elemente im Array ab.|  
|[GetRank-Methode](icordebugarrayvalue-getrank-method.md)|Ruft die Anzahl der Dimensionen im Array ab.|  
|[HasBaseIndicies-Methode](icordebugarrayvalue-hasbaseindicies-method.md)|Bestimmt, ob das Array über Basis Indizes verfügt.|  
  
## <a name="remarks"></a>Hinweise  

 `ICorDebugArrayValue` unterstützt sowohl eindimensionale als auch mehrdimensionale Arrays.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
