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
ms.openlocfilehash: 8210e67f4bdd615ff65d9bd3474043fc45fd8883
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791260"
---
# <a name="icordebugtype-interface"></a>ICorDebugType-Schnittstelle
Stellt einen Typ dar, entweder "Basic" oder "Complex" (d. h. Benutzer definiert). Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateTypeParameters-Methode](icordebugtype-enumeratetypeparameters-method.md)|Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die auf die generischen <xref:System.Type> Parameter der Klasse verweist, auf die von diesem `ICorDebugType`verwiesen wird.|  
|[GetBase-Methode](icordebugtype-getbase-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` ab, der auf die Basisklasse der Klasse verweist, auf die von diesem `ICorDebugType`verwiesen wird, sofern vorhanden.|  
|[GetClass-Methode](icordebugtype-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die auf den typisierten Konstruktor dieses `ICorDebugType`verweist.|  
|[GetFirstTypeParameter-Methode](icordebugtype-getfirsttypeparameter-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` ab, der auf den ersten generischen <xref:System.Type> Parameter für den Konstruktor der Klasse verweist, auf die von diesem `ICorDebugType`verwiesen wird.|  
|[GetRank-Methode](icordebugtype-getrank-method.md)|Ruft die Anzahl der Dimensionen in einem Arraytyp ab.|  
|[GetStaticFieldValue-Methode](icordebugtype-getstaticfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebugValue ab, der den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.|  
|[GetType-Methode](icordebugtype-gettype-method.md)|Ruft einen korelementtype-Wert ab, der den systemeigenen Typ der Common Language Runtime <xref:System.Type> beschreibt, auf die von diesem `ICorDebugType`verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ generisch ist, `ICorDebugClass` den nicht instanziierten Typ darstellt. Die `ICorDebugType`-Schnittstelle stellt einen instanziierten generischen Typ dar. Beispielsweise würde das Hashtable-\<K, V > durch `ICorDebugClass`dargestellt werden, wohingegen Hash Table\<Int32, String > durch `ICorDebugType`dargestellt würde.  
  
 Nicht generische Typen werden durch `ICorDebugClass` und `ICorDebugType`dargestellt. Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
