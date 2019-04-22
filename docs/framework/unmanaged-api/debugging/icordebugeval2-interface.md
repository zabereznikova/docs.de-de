---
title: ICorDebugEval2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3767368c9da8c97cd081787c0945a15552a1da46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092668"
---
# <a name="icordebugeval2-interface"></a>ICorDebugEval2-Schnittstelle

Erweitert "ICorDebugEval", um Unterstützung für generische Typen bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CallParameterizedFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|Richtet einen Aufruf der angegebenen "ICorDebugFunction", die innerhalb eines Typs, dessen Konstruktor Parameter vom Typ annimmt, oder kann selbst Parameter vom Typ, geschachtelt werden können.|  
|[CreateValueForType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|Ruft einen Zeiger auf einen neuen "ICorDebugValue" des angegebenen Typs mit einem Anfangswert von 0 oder NULL ab.|  
|[NewParameterizedArray-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.|  
|[NewParameterizedObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|Instanziiert ein neues Objekt für den parametrisierten Typ und die Konstruktormethode des Objekts aufgerufen.|  
|[NewParameterizedObjectNoConstructor-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Instanziiert ein neues parametrisierten Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen|  
|[NewStringWithLength-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|Erstellt eine neue Zeichenfolge mit der angegebenen Länge mit dem angegebenen Inhalt.|  
|[RudeAbort-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|Bricht ab, der Berechnung, die dieses `ICorDebugEval2` wird derzeit ausgeführt.|  
  
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
