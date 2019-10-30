---
title: ICorDebugType-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 4f3f553ed5dc93433610365e0dae5bee54863de5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129628"
---
# <a name="icordebugtype-interface"></a>ICorDebugType-Schnittstelle
Stellt einen Typ dar, entweder "Basic" oder "Complex" (d. h. Benutzer definiert). Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateTypeParameters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die auf die generischen <xref:System.Type> Parameter der Klasse verweist, auf die von diesem `ICorDebugType`verwiesen wird.|  
|[GetBase-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` ab, der auf die Basisklasse der Klasse verweist, auf die von diesem `ICorDebugType`verwiesen wird, sofern vorhanden.|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die auf den typisierten Konstruktor dieses `ICorDebugType`verweist.|  
|[GetFirstTypeParameter-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` ab, der auf den ersten generischen <xref:System.Type> Parameter für den Konstruktor der Klasse verweist, auf die von diesem `ICorDebugType`verwiesen wird.|  
|[GetRank-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ruft die Anzahl der Dimensionen in einem Arraytyp ab.|  
|[GetStaticFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebugValue ab, der den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ruft einen korelementtype-Wert ab, der den systemeigenen Typ der Common Language Runtime <xref:System.Type> beschreibt, auf die von diesem `ICorDebugType`verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ generisch ist, `ICorDebugClass` den nicht instanziierten Typ darstellt. Die `ICorDebugType`-Schnittstelle stellt einen instanziierten generischen Typ dar. Beispielsweise würde das Hashtable-\<K, V > durch `ICorDebugClass`dargestellt werden, wohingegen Hash Table\<Int32, String > durch `ICorDebugType`dargestellt würde.  
  
 Nicht generische Typen werden durch `ICorDebugClass` und `ICorDebugType`dargestellt. Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
